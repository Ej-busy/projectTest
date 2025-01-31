<html>
<head>
    <title>Simple 2D Game</title>
    <style>
        canvas {
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <canvas id="gameCanvas" width="500" height="500"></canvas>
    <script>
        var canvas = document.getElementById("gameCanvas");
        var ctx = canvas.getContext("2d");

        var rect = {
            x: 50,
            y: 50,
            width: 50,
            height: 50,
            speed: 5
        };

        document.addEventListener("keydown", function(event) {
            switch (event.key) {
                case "ArrowUp":
                    rect.y -= rect.speed;
                    break;
                case "ArrowDown":
                    rect.y += rect.speed;
                    break;
                case "ArrowLeft":
                    rect.x -= rect.speed;
                    break;
                case "ArrowRight":
                    rect.x += rect.speed;
                    break;
            }
            draw();
        });

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = "blue";
            ctx.fillRect(rect.x, rect.y, rect.width, rect.height);
        }

        draw();
    </script>
</body>
