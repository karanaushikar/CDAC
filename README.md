https://drive.google.com/drive/folders/1F70TteDaITHMWfPMuCejq1BfRqsiSFK3?usp=drive_link
const readline = require('readline-sync');

// Capitalize first letter of each word
function capitalize(name) {
  return name
    .split(' ')
    .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join(' ');
}

class Student {
  constructor(name, rollNo, grades, attendance) {
    this.name = capitalize(name);
    this.rollNo = rollNo;
    this.grades = grades;
    this.attendance = attendance;
  }

  calculateAverage() {
    const sum = this.grades.reduce((a, b) => a + b, 0);
    return this.grades.length ? (sum / this.grades.length).toFixed(2) : 0;
  }

  getGrade() {
    const avg = this.calculateAverage();
    if (avg >= 90) return 'A';
    else if (avg >= 75) return 'B';
    else if (avg >= 60) return 'C';
    else return 'F';
  }

  isRegular() {
    return this.attendance >= 24;
  }

  getDetails() {
    return `
Student Report:
---------------
Name       : ${this.name}
Roll No.   : ${this.rollNo}
Average    : ${this.calculateAverage()}
Final Grade: ${this.getGrade()}
Attendance : ${this.attendance}/30 (${this.isRegular() ? 'Regular' : 'Irregular'})
`;
  }
}

// ✅ Part 3: Create multiple students
const students = [
  new Student("alice johnson", 101, [85, 78, 92], 28),
  new Student("bob smith", 102, [65, 70, 72], 22),
  new Student("charlie brown", 103, [90, 95, 93], 30),
];

// ✅ Print report for each student
students.forEach(student => {
  console.log(student.getDetails());
});

// ✅ Bonus: Accept input from user
console.log("\nEnter new student details:");
const name = readline.question("Name: ");
const rollNo = parseInt(readline.question("Roll No: "));
const gradesInput = readline.question("Enter grades separated by commas: ");
const grades = gradesInput.split(',').map(Number);
const attendance = parseInt(readline.question("Attendance (0–30): "));

const newStudent = new Student(name, rollNo, grades, attendance);
console.log(newStudent.getDetails());
