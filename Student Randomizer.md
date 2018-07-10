##This was a problem I chose to solve at DevMountain.
DevMountain students often work in pairs which are supposed to be random. The randomizing code the school was using did not take
into consideration who the students had worked with in the past, so it was very common for students to end up being matched with the
same people often, and never matched with a large number of their peers. I decided to solve this so students would have the opportunity
of working with most if not all of their peers before working with the same person again.

I used a database to store student objects, each student was assigned an array that contained all IDs of students they had already worked with.
Another thing that needed to be accounted for was only matching up students who were present for the day. Additionally, if the number of students 
was odd for the day the mentors would need to be paired with one of the students. Below are the functions I created to solve the problems.


###An http request to set all students in the cohort to state to map over and display.
getStudents() {
axios.get('/api/getstudents').then(res => {
    this.setState({ today: res.data })
})
}

###A function to remove students that aren't present for the day.
removeStudentToday(id) {
let copy = this.state.today.slice()
for(let i = 0; i < copy.length; i++) {
  if(copy[i].id === id) {
  copy.splice(i, 1)
  break;
  }
}
this.setState({today: copy})
}

###A function that randomly rearranges the elements of an array.
function shuffle(array) {
  var currentIndex = array.length, temporaryValue, randomIndex;
  while (0 !== currentIndex) {
      randomIndex = Math.floor(Math.random() * currentIndex);
      currentIndex -= 1;
      temporaryValue = array[currentIndex];
      array[currentIndex] = array[randomIndex];
      array[randomIndex] = temporaryValue;
  }
  return array
}

###The main function solving the problem.
function getPairs() {
  ###A variable created as a copy of data from state to mutate, because state should be immutable.
  ###this.state.today is an array of objects, each object represents a student.
  let today = [...this.state.today]
  ###Randomly shuffle the students into a different order within the today array.
  shuffle(today)
  ###stores all the pairs to be displayed.
  let pairs = []
  ###stores all the updated student objects.
  let updatedYesArrays = []

  ###A nested for loop to compare and check the 'yes' key in each student object (which is an array of ids) against the 'id' key of other student objects.
  ###If the id of the student being compared against doesn't exist within the 'yes' array of the student currently being compared to, each student's id will be
  ###added into eachother's 'yes' array. Each student object then will be pushed into the updatedYesArrays. Their name will then be pushed into the pairs array. 
  ###They then will be removed from the today array so that the students in the today array are only students that haven't been assigned a pair yet.
  for (let i = 0; i < today.length; i++) {
    for (let j = i + 1; j < today.length; j++) {
      if (today[i].yes.indexOf(today[j].id) === -1) {
        today[i].yes.push(today[j].id)
        today[j].yes.push(today[i].id)
        updatedYesArrays.push(today[i], today[j])
        pairs.push([today[i].name, today[j].name])
        today.splice(i, 1)
        today.splice(j - 1, 1)
        i--
        break;
      }
    }
  }
  ###If students were left in the array because they have already worked with eachother, the code below will pair them together for the day.
  ###If only one student is left in the array, meaning that the number of students for the day was odd, they would be paired with the mentors. 
  if (today.length !== 0) {
    for (let i = 0; i < today.length; i++) {
      if (today.length % 2 === 0) {
        pairs.push([today[i].name, today[i + 1].name])
        updatedYesArrays.push(today[i], today[i + 1])
        today.splice(i, 2)
        i--
      } else {
        today.push({ id: 1337, name: 'Mentors' })
        i--
      }
    }
  }
  this.setState({ pairs })
  ###This call sends the updated student objects to the database to be stored.
  axios.put('/api/updateyes', { student: updatedYesArrays })
  }