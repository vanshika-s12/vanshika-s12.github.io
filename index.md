<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Full-Screen Translucent Video with Background</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-image: url('assets/my-background.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            min-height: 100vh;
            font-family: Arial, sans-serif;
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 3;
            padding: 10px 0;
        }

        .navbar ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        .navbar li {
            margin: 0 20px;
        }

        .navbar a {
            color: #fff;
            text-decoration: none;
            font-size: 18px;
            transition: color 0.3s;
        }

        .navbar a:hover {
            color: #ddd;
        }

        .video-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        video {
            width: 100vw;
            height: 100vh;
            object-fit: cover;
            display: block;
            opacity: 0.3;
        }

        .video-container.visible {
            opacity: 1;
        }

        .content {
            position: relative;
            z-index: 0;
            padding: 20px;
            margin-top: 60px;
            color: #fff;
            text-align: center;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
        }

        .fallback {
            display: none;
            color: red;
            font-size: 18px;
            text-align: center;
            padding: 20px;
            position: fixed;
            top: 60px;
            left: 0;
            width: 100%;
            z-index: 2;
            background: rgba(0, 0, 0, 0.5);
        }

        .view-counter {
            margin-top: 20px;
        }

        .view-counter img {
            vertical-align: middle;
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="publications.html">Publications</a></li>
        </ul>
    </nav>

    <div class="video-container" id="videoContainer">
        <video id="introVideo" autoplay muted loop>
            <source src="assets/intro.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>

    <div class="fallback" id="fallbackMessage">
        Failed to load video. Please check the file path: assets/intro.mp4
    </div>

    <div class="content">
        <h1>Welcome to My Page</h1>
        <p>This is some content behind the translucent video that appears and vanishes.</p>
        <div class="view-counter">
            <img src="https://hitscounter.dev/api/hit?url=https%3A%2F%2Fvanshika-s12.github.io%2F&label=&icon=github&color=%23198754&message=&style=flat&tz=Indian%2FMauritius" alt="Page Views">
        </div>
    </div>

    <script>
        const videoContainer = document.getElementById('videoContainer');
        const introVideo = document.getElementById('introVideo');
        const fallbackMessage = document.getElementById('fallbackMessage');

        console.log('Video path:', introVideo.src);
        console.log('Background path:', getComputedStyle(document.body).backgroundImage);

        introVideo.onerror = () => {
            console.error('Error: Video failed to load at assets/intro.mp4');
            fallbackMessage.style.display = 'block';
        };

        introVideo.onloadeddata = () => {
            console.log('Video loaded successfully');
            fallbackMessage.style.display = 'none';
        };

        function toggleVideo() {
            videoContainer.classList.toggle('visible');
        }

        setInterval(toggleVideo, 5000);
        toggleVideo();
    </script>
</body>
</html>
