<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: url('https://cf.bstatic.com/xdata/images/hotel/max1024x768/537436913.jpg?k=16f6a3b7517fe1d02fbbfe478d435e3a67544e9cc580632e341544103990ecf1&o=&hp=1') no-repeat center center fixed; /* Ваш URL изображения */
            background-size: cover; /* Растягивает изображение на весь экран */
            color: white;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .welcome-text {
            font-size: 24px;
            text-align: center;
            margin-bottom: 20px;
        }
        .continue-btn {
            padding: 10px 20px;
            font-size: 18px;
            background-color: #007BFF;
            border: none;
            color: white;
            cursor: pointer;
            border-radius: 5px;
        }
        .continue-btn:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div id="welcome-screen">
        <div class="welcome-text">
            <h1>Welcome to our hotel!</h1>
            <p>We will do everything possible to ensure that your stay is as comfortable and enjoyable as possible. Thank you for choosing our hotel. If you need any assistance, please feel free to reach out to us.</p>
        </div>
        <button class="continue-btn" onclick="exitToTV()">Continue</button>
    </div>

    <script>
        function exitToTV() {
            // Using the built-in WebOS API to switch to TV channel
            if (typeof webOS !== "undefined" && webOS.platform.tv) {
                webOS.service.request("luna://com.webos.applicationManager", {
                    method: "launch",
                    parameters: {
                        id: "com.webos.app.livetv"
                    },
                    onSuccess: function () {
                        console.log("Successfully switched to Live TV.");
                    },
                    onFailure: function (error) {
                        console.error("Failed to switch to Live TV:", error);
                    }
                });
            } else {
                alert("This feature is only available on LG webOS TVs.");
            }
        }
    </script>
</body>
</html>
