# Project
Online quiz format
###INDEX.HTML
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Student Login</title>
 <link rel="stylesheet" href="styles.css">
</head>
<body>
 <div class="login-container">
 <h2>Student Login</h2>
 <form id="loginForm">
 <label for="email">Email ID</label>
 <input type="email" id="email" name="email" placeholder="Enter your email"
required>

 <label for="password">Password</label>
 <input type="password" id="password" name="password" placeholder="Enter your
password" required>

 <button type="submit">Login</button>
 </form>
 <p id="error-message" class="error-message"></p>
 </div>
 <script src="script.js"></script>
</body>
</html>
###INDEX1.HTML
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Subject Quiz</title>
 <link rel="stylesheet" href="styles1.css">
</head>
<body>
 <div class="quiz-container">
 <h2>Choose a Subject for Quiz</h2>
 <select id="subject" onchange="loadQuiz()">
 <option value="">Select Subject</option>
 <option value="math">VERSION CONTROLLER</option>
 <option value="science">DSA</option>
 <option value="history">JAVA</option>
 </select>
 <div id="quiz-section" style="display: none;">
 <h3>Quiz Questions</h3>
 <form id="quiz-form">
 <!-- Quiz Questions will be dynamically inserted here -->
 </form>
 <button type="button" id="submit-btn">Submit Quiz</button>
 </div>
 <div id="result" style="display: none;">
 <h3>Your Result</h3>
 <p id="score"></p>
 <p id="message"></p>
 <ul id="incorrect-answers">
 <!-- Incorrect answers and the correct answers will be displayed here -->
 </ul>
 </div>
 </div>
 <script src="script1.js"></script>
</body>
</html>
###SCRIPT.JS
document.getElementById("loginForm").addEventListener("submit", function(event) {
 event.preventDefault();

 const email = document.getElementById("email").value;
 const password = document.getElementById("password").value;
 const validCredentials = {
 "pratiksha@123.com": "password123",
 "priya@123.com": "password222",
 "rakshita@123.com":"password111",
 "shrusti@123.com":"password333"
 };
 if (validCredentials[email] && validCredentials[email] === password) {

 window.location.href = "index1.html";
 } else {
 document.getElementById("error-message").textContent = "Invalid email or
password.";
 } }
);
###SCRIPT1.JS
const subjects = {
 math: [
 {
 question: "What command is used to initialize a new Git repository?",
 options: ["git start", "git create", "git init", "git new"],
 correct: "git init"
 },
 {
 question: "Which command is used to check the status of the Git repository?",
 options: ["git status", "git check", "git info", "git repo-status"],
 correct: "git status"
 },
 {
 question: "What does the command 'git commit -m' do?",
 options: ["Adds a new file to the repository", "Commits changes with a message",
"Creates a new branch", "Pushes changes to the remote repository"],
 correct: "Commits changes with a message"
 },
 {
 question: "Which Git command is used to stage changes for commit?",
 options: ["git add", "git commit", "git push", "git stage"],
 correct: "git add"
 },
 {
 question: "What does 'git clone' do?",
 options: ["Creates a new repository", "Copies an existing repository", "Commits
changes to the repository", "Deletes a repository"],
 correct: "Copies an existing repository"
 },
 {
 question: "What is the purpose of 'git pull'?",
 options: ["Fetches and merges changes from the remote repository", "Pushes local
changes to the remote repository", "Clones a repository from the remote", "Creates a new
branch in the repository"],
 correct: "Fetches and merges changes from the remote repository"
 },
 {
 question: "What is the purpose of 'git push'?",
 options: ["Uploads local changes to the remote repository", "Fetches changes from the
remote repository", "Creates a new branch", "Commits changes locally"],
 correct: "Uploads local changes to the remote repository"
 },
 {
 question: "What does 'git merge' do?",
 options: ["Merges two branches into one", "Deletes a branch", "Creates a new
branch", "Pushes changes to the remote repository"],
 correct: "Merges two branches into one"
 },
 {
 question: "What command is used to check the commit history in Git?",
 options: ["git history", "git log", "git commits", "git show"],
 correct: "git log"
 },
 {
 question: "Which command is used to create a new branch in Git?",
 options: ["git create branch", "git new branch", "git branch", "git make branch"],
 correct: "git branch"
 }
 ],
 science: [
 {
 question: "What is the time complexity of accessing an element in an array by
index?",
 options: ["O(1)", "O(log n)", "O(n)", "O(n^2)"],
 correct: "O(1)"
 },
 {
 question: "Which of the following data structures is used in breadth-first search
(BFS)?",
 options: ["Stack", "Queue", "Linked List", "Tree"],
 correct: "Queue"
 },
 {
 question: "What is the space complexity of the recursive solution for calculating
Fibonacci numbers?",
 options: ["O(1)", "O(n)", "O(n^2)", "O(log n)"],
 correct: "O(n)"
 },
 {
 question: "What is the worst-case time complexity of quicksort?",
 options: ["O(n log n)", "O(n^2)", "O(log n)", "O(n)"],
 correct: "O(n^2)"
 },
 {
 question: "In a binary search tree (BST), which traversal will give nodes in sorted
order?",
 options: ["In-order traversal", "Pre-order traversal", "Post-order traversal", "Levelorder traversal"],
 correct: "In-order traversal"
 },
 {
 question: "Which of the following sorting algorithms is stable?",
 options: ["Quick sort", "Merge sort", "Heap sort", "Selection sort"],
 correct: "Merge sort"
 },
 {
 question: "Which data structure is used to implement a depth-first search (DFS)?",
 options: ["Queue", "Stack", "Linked List", "Array"],
 correct: "Stack"
 },
 {
 question: "Which of the following is the best time complexity for a binary search on a
sorted array?",
 options: ["O(n)", "O(log n)", "O(n log n)", "O(1)"],
 correct: "O(log n)"
 },
 {
 question: "What is the space complexity of a binary tree?",
 options: ["O(1)", "O(n)", "O(log n)", "O(n^2)"],
 correct: "O(n)"
 },
 {
 question: "What is the worst-case time complexity of bubble sort?",
 options: ["O(n log n)", "O(n^2)", "O(n)", "O(log n)"],
 correct: "O(n^2)"
 }
 ],
 history: [
 {
 question: "Which of the following is a primitive data type in Java?",
 options: ["String", "int", "ArrayList", "System"],
 correct: "int"
 },
 {
 question: "What is the default value of a boolean variable in Java?",
 options: ["true", "false", "null", "undefined"],
 correct: "false"
 },
 {
 question: "Which keyword is used to prevent a class from being subclassed in Java?",
 options: ["static", "final", "abstract", "private"],
 correct: "final"
 },
 {
 question: "Which of the following is the correct syntax for a 'for' loop in Java?",
 options: ["for(int i = 0; i < 10; i++)", "for i = 0; i < 10; i++", "for(int i = 0, i < 10;
i++)", "loop for(int i = 0; i < 10; i++)"],
 correct: "for(int i = 0; i < 10; i++)"
 },
 {
 question: "Which of the following statements is true about an abstract class in Java?",
 options: ["An abstract class can be instantiated", "An abstract class cannot have any
methods", "An abstract class can have both abstract and non-abstract methods", "An abstract
class can only have abstract methods"],
 correct: "An abstract class can have both abstract and non-abstract methods"
 },
 {
 question: "Which method is used to start a thread in Java?",
 options: ["start()", "run()", "execute()", "init()"],
 correct: "start()"
 },
 {
 question: "Which collection class is part of Java’s collection framework and allows
duplicates?",
 options: ["HashSet", "TreeSet", "ArrayList", "HashMap"],
 correct: "ArrayList"
 },
 {
 question: "What does the 'this' keyword refer to in a method or constructor?",
 options: ["The method or constructor itself", "The instance of the current class", "The
parent class", "A static variable"],
 correct: "The instance of the current class"
 },
 {
 question: "Which method is used to compare two strings lexicographically in Java?",
 options: ["compareTo()", "equals()", "compare()", "isEqual()"],
 correct: "compareTo()"
 },
 {
 question: "Which of the following is the correct way to declare a 2D array in Java?",
 options: ["int arr[][];", "int[] arr[];", "int arr[2][2];", "int[] arr[2][2];"],
 correct: "int arr[][];"
 }
 ]
};
let selectedSubject = '';
let userAnswers = [];
function loadQuiz() {
 selectedSubject = document.getElementById("subject").value;
 const quizSection = document.getElementById("quiz-section");
 const quizForm = document.getElementById("quiz-form");
 const resultSection = document.getElementById("result");
 if (selectedSubject === "") {
 quizSection.style.display = "none";
 resultSection.style.display = "none";
 return;
 }
 quizSection.style.display = "block";
 resultSection.style.display = "none";
 // Clear previous questions
 quizForm.innerHTML = '';
 // Load new quiz questions
 const questions = subjects[selectedSubject];
 questions.forEach((q, index) => {
 const questionHTML = `
 <fieldset>
 <legend>${q.question}</legend>
 ${q.options.map((option, i) => `
 <label>
 <input type="radio" name="question${index}" value="${option}">
 ${option}
 </label><br>
 `).join('')}
 </fieldset>
 `;
 quizForm.innerHTML += questionHTML;
 });
}
function submitQuiz(event) {
 event.preventDefault(); // Prevent form from refreshing the page
 const form = document.getElementById("quiz-form");
 const resultSection = document.getElementById("result");
 const scoreElement = document.getElementById("score");
 const messageElement = document.getElementById("message");
 const incorrectAnswersElement = document.getElementById("incorrect-answers");
 // Collect user answers
 userAnswers = [];
 let score = 0;
 let totalQuestions = 0;
 let incorrectAnswers = [];
 const questions = subjects[selectedSubject];
 questions.forEach((q, index) => {
 const selectedOption =
form.querySelector(`input[name="question${index}"]:checked`);
 const userAnswer = selectedOption ? selectedOption.value : null;
 userAnswers.push(userAnswer);
 if (userAnswer === q.correct) {
 score++;
 } else {
 incorrectAnswers.push({ question: q.question, correctAnswer: q.correct, userAnswer:
userAnswer });
 }
 totalQuestions++;
 });
 // Calculate score
 const percentage = (score / totalQuestions) * 100;
 scoreElement.textContent = `Your Score: ${percentage}%`;
 // Provide feedback based on the score
 if (percentage >= 60) {
 messageElement.textContent = "Congratulations! You passed the test!";
 } else {
 messageElement.textContent = "Sorry, you did not pass the test.";
 }
 // Show incorrect answers with the correct answers
 incorrectAnswersElement.innerHTML = '';
 incorrectAnswers.forEach(answer => {
 const li = document.createElement("li");
 li.textContent = `${answer.question} Your answer: ${answer.userAnswer || 'None'},
Correct answer: ${answer.correctAnswer}`;
 incorrectAnswersElement.appendChild(li);
 });
 resultSection.style.display = "block";
}
// Bind event listener to submit button
document.getElementById("submit-btn").addEventListener("click", submitQuiz);
###STYLES.CSS
body {
 font-family: Arial, sans-serif;
 background-color: #f0f4f8;
 margin: 0;
 padding: 0;
}
.login-container {
 width: 100%;
 max-width: 400px;
 margin: 100px auto;
 padding: 30px;
 background-color: #fff;
 border-radius: 8px;
 box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
h2 {
 text-align: center;
 color: #333;
}
label {
 display: block;
 margin: 10px 0 5px;
 font-size: 14px;
 color: #333;
}
input {
 width: 100%;
 padding: 10px;
 margin-bottom: 20px;
 border: 1px solid #ccc;
 border-radius: 4px;
 font-size: 14px;
}
button {
 width: 100%;
 padding: 10px;
 background-color: #4CAF50;
 color: white;
 border: none;
 border-radius: 4px;
 font-size: 16px;
 cursor: pointer;
}
button:hover {
 background-color: #45a049;
}
.error-message {
 color: red;
 font-size: 14px;
 text-align: center;
 margin-top: 20px;
}
###STYLES1.CSS
body {
 font-family: Arial, sans-serif;
 background-color: #f4f4f4;
 padding: 20px;
}
.quiz-container {
 max-width: 600px;
 margin: 0 auto;
 padding: 20px;
 background-color: #fff;
 border-radius: 10px;
 box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
h2, h3 {
 text-align: center;
 color: #333;
}
select, button {
 display: block;
 width: 100%;
 padding: 10px;
 margin: 10px 0;
 font-size: 16px;
}
button {
 background-color: #28a745;
 color: #fff;
 border: none;
 cursor: pointer;
}
button:hover {
 background-color: #218838;
}
fieldset {
 border: 1px solid #ccc;
 padding: 10px;
 margin-bottom: 10px;
 border-radius: 5px;
}
legend {
 font-weight: bold;
}
label {
 display: block;
 margin-bottom: 5px;
}
#result {
 margin-top: 20px;
 text-align: center;
}
ul {
 list-style-type: none;
 padding-left: 0;
}
ul li {
 margin-bottom: 10px;
}
