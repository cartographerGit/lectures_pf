<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple Flashcard</title>
</head>
<body>

    <div id="flashcard" style="border:1px solid black; padding:20px; width:300px; text-align:center;">
        <div id="question">What is the capital of France?</div>
        <div id="answer" style="display:none;">Paris</div>
    </div>
    
    <button onclick="toggleAnswer()">Show Answer</button>

    <script>
        function toggleAnswer() {
            var answerDiv = document.getElementById('answer');
            var button = document.querySelector('button');

            if (answerDiv.style.display === 'none') {
                answerDiv.style.display = 'block';
                button.textContent = 'Hide Answer';
            } else {
                answerDiv.style.display = 'none';
                button.textContent = 'Show Answer';
            }
        }
    </script>

</body>
</html>
