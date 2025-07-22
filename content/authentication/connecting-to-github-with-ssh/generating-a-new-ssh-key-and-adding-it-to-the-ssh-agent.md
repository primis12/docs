const questions = [
  {
    question: "What is the capital of India?",
    options: ["Delhi", "Mumbai", "Kolkata", "Chennai"],
    answer: "Delhi"
  },
  {
    question: "2 + 2 = ?",
    options: ["3", "4", "5", "22"],
    answer: "4"
  },
  {
    question: "What is the boiling point of water?",
    options: ["50°C", "90°C", "100°C", "120°C"],
    answer: "100°C"
  }
];

let current = 0;
let score = 0;

function loadQuestion() {
  const q = questions[current];
  document.getElementById("question").innerText = q.question;
  const optionsDiv = document.getElementById("options");
  optionsDiv.innerHTML = "";

  q.options.forEach(opt => {
    const btn = document.createElement("button");
    btn.innerText = opt;
    btn.onclick = () => {
      if (opt === q.answer) score++;
      nextQuestion();
    };
    optionsDiv.appendChild(btn);
  });
}

function nextQuestion() {
  current++;
  if (current < questions.length) {
    loadQuestion();
  } else {
    document.getElementById("quiz").innerHTML = `
      <h2>Your Score: ${score}/${questions.length}</h2>
      <p>Thank you for playing!</p>
    `;
  }
}

loadQuestion();
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>EduQuiz App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="app">
    <h1>EduQuiz - Test Your Knowledge</h1>
    <div id="quiz">
      <div id="question">Loading...</div>
      <div id="options"></div>
      <button id="nextBtn" onclick="nextQuestion()">Next</button>
      <div id="result"></div>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>EduQuiz App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="app">
    <h1>EduQuiz - Test Your Knowledge</h1>
    <div id="quiz">
      <div id="question">Loading...</div>
      <div id="options"></div>
      <button id="nextBtn" onclick="nextQuestion()">Next</button>
      <div id="result"></div>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>

btn.onclick
