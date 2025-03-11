<!DOCTYPE html>
<html>
<head>
    <title>Countdown Timer</title>
</head>
<body>
    <h1>Countdown: <span id="countdown">10</span> seconds</h1>
    <script>
        let count = 10;
        let timer = setInterval(() => {
            count--;
            document.getElementById("countdown").innerText = count;
            if (count <= 0) {
                clearInterval(timer);
                alert("Time's up!");
            }
        }, 1000);
    </script>
</body>
</html>
