<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
            .background-dark {
      background-color: #262626;
    }
    .center {
        display:flex;
        justify-content: center;
    }
    .margin-top {
        margin-top: 100px;
    }
    .timer {
        font-size: 100px;
        color: white;
        font-family: 'Roboto', sans-serif;
    }
    </style>

    <script>
        let comp = new Audio(`comp.mp3`);
        let timerStarted = false;

        function startTimer () {
            if(!timerStarted){
            let startTime = new Date().getTime();
            let fiveMinutes = 1000 * 60 * 5
            let endTime = startTime + fiveMinutes;
       


            setInterval(function()  {
                let timeLeft = endTime - new Date().getTime();

                if(timeLeft > 0) {
                let minutes = timeLeft / (1000 * 60);
                minutes = Math.floor (minutes);
                let seconds = (timeLeft / 1000) % 60;
                seconds = Math.round(seconds);
                seconds = (`0` + seconds).slice(-2)
                let text = `0` + minutes + ` : ` +seconds;
                timer.innerHTML = text;
                } else {
                    timer.innerHTML = "00 : 00";
                    comp.play()
                    
                }
                },1000);
            }
        }
    </script>
</head>
<body class ="background-dark">
    </div>
    <div class="center margin-top">
        <img src="img/lava_eimer.png">
    </div>
    <div class="center margin-top timer" id="timer">
        05 : 00
    </div>
    <div class="center margin-top">
        <img onclick="startTimer()" src= "img/btn.png"> 
    </div>
</body>
</html>
