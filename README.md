<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>A Few Questions...</title>

<style>
    body {
        font-family: Arial, sans-serif;
        background: #111;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        margin: 0;
        text-align: center;
        padding: 20px;
    }

    .container {
        max-width: 700px;
    }

    h1 {
        margin-bottom: 30px;
    }

    button {
        padding: 12px 24px;
        margin: 10px;
        font-size: 18px;
        cursor: pointer;
        border: none;
        border-radius: 10px;
    }

    .hidden {
        display: none;
    }

    #result {
        font-size: 28px;
    }
</style>
</head>
<body>

<div class="container">
    <h1 id="question"></h1>

    <div id="buttons">
        <button id="option1"></button>
        <button id="option2"></button>
    </div>

    <div id="result" class="hidden"></div>
</div>

<script>
const questions = [
{
    text: "1. I have a few questions, take time to sit down and get comfy. Would you like to continue?",
    options: ["(yea)", "(nah)"]
},
{
    text: "2. Thanks, I appreciate your time. You ready?",
    options: ["(yurrrp)", "(nurrrp)"]
},
{
    text: "3. Okay first off, I was wondering about your opinion on Charlie. No, i wont tell him. trust.",
    options: ["(slightly normal)", "(mentally retarded)"]
},
{
    text: "4. would you ever consider this person as more than a friend?",
    options: ["(u cringe)", "(shut the fuck up bruh)"]
},
{
    text: "5. Github Pages are annoying. Do you agree?",
    options: ["(fuck yeah)", "(well actually, i find github-)"]
},
{
    text: "6. This may catch you off guard, but take the hints and youll see where this goes. Got it?",
    options: ["(aight)", "(im scared)"]
},
{
    text: "7. Photos printed?",
    options: ["(bogos binted?)", "(what?)"]
},
{
    text: "8. will you date me?",
    options: ["(yes)", "(yes but im making you sweat first)"]
}

];
    
let currentQuestion = 0;

const questionEl = document.getElementById("question");
const option1 = document.getElementById("option1");
const option2 = document.getElementById("option2");
const result = document.getElementById("result");

function showQuestion() {
    questionEl.textContent = questions[currentQuestion].text;
    option1.textContent = questions[currentQuestion].options[0];
    option2.textContent = questions[currentQuestion].options[1];
}

function nextQuestion() {
    currentQuestion++;

    if (currentQuestion >= questions.length) {
        document.getElementById("buttons").classList.add("hidden");
        questionEl.classList.add("hidden");

        result.classList.remove("hidden");
        result.innerHTML = `
            <p>Thanks for answering ❤️</p>
            <p>You can screenshot this and send your answer back to Charlie 😭</p>
        `;
        return;
    }

    showQuestion();
}

option1.addEventListener("click", nextQuestion);
option2.addEventListener("click", nextQuestion);

showQuestion();
</script>

</body>
</html>
