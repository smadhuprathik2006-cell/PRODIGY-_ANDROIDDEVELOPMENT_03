# PRODIGY-_ANDROIDDEVELOPMENT_03
<!DOCTYPE html>
<html>
<head>
 <title>Stopwatch App</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 background: #f4f4f4;
 display: flex;
 justify-content: center;
 align-items: center;
 height: 100vh;
 }
 .container {
 background: white;
 padding: 30px;
 border-radius: 10px;
 text-align: center;
 box-shadow: 0 0 10px rgba(0,0,0,0.2);
 }
 h1 {
 margin-bottom: 20px;
 }
 #display {
 font-size: 40px;
 margin-bottom: 20px;
 }
 button {
 padding: 10px 15px;
 margin: 5px;
 border: none;
 border-radius: 5px;
 cursor: pointer;
 font-size: 16px;
 }
 .start {
 background: green;
 color: white;
 }
 .pause {
 background: orange;
 color: white;
 }
 .reset {
 background: red;
 color: white;
 }
 </style>
</head>
<body>
<div class="container">
 <h1>Stopwatch</h1>
 <div id="display">00 : 00 : 00</div>
 <button class="start" onclick="startTimer()">Start</button>
 <button class="pause" onclick="pauseTimer()">Pause</button>
 <button class="reset" onclick="resetTimer()">Reset</button>
</div>
<script>
 let minutes = 0;
 let seconds = 0;
 let milliseconds = 0;
 let timer;
 function updateDisplay() {
 document.getElementById("display").innerText =
 (minutes < 10 ? "0" : "") + minutes + " : " +
 (seconds < 10 ? "0" : "") + seconds + " : " +
 (milliseconds < 10 ? "0" : "") + milliseconds;
 }
 function startTimer() {
 if (!timer) {
 timer = setInterval(() => {
 milliseconds++;
 if (milliseconds == 100) {
 milliseconds = 0;
 seconds++;
 }
 if (seconds == 60) {
 seconds = 0;
 minutes++;
 }
 updateDisplay();
 }, 10);
 }
 }
 function pauseTimer() {
 clearInterval(timer);
 timer = null;
 }
 function resetTimer() {
 clearInterval(timer);
 timer = null;
 minutes = 0;
 seconds = 0;
 milliseconds = 0;
 updateDisplay();
 }
</script>
</body>
</html>
