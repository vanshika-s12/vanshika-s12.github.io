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

        /* Video container for full-screen coverage */
        .video-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1; /* Video stays above content */
            opacity: 0; /* Initially hidden */
            transition: opacity 1s ease-in-out; /* Smooth fade effect */
        }

        /* Style the video element */
        video {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Ensures GIF covers the entire area */
            opacity: 0.5; /* Translucency when visible */
        }

        /* Class to show the video */
        .video-container.visible {
            opacity: 1;
        }

        /* Content behind the video */
        .content {
            position: relative;
            z-index: 0; /* Content stays below the video */
            padding: 20px;
            color: #fff; /* White text for contrast */
            text-align: center;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7); /* Text shadow for readability */
        }
    </style>
</head>
<body>
    <!-- Video container -->
    <div class="video-container" id="videoContainer">
        <video autoplay muted loop>
            <source src="assets/intro.gif" type="image/gif">
            Your browser does not support the video tag.
        </video>
    </div>

    <!-- Sample content behind the video -->
    <div class="content">
        <h1>Welcome to My Page</h1>
        <p>This is some content behind the translucent GIF that appears and vanishes.</p>
    </div>

    <script>
        // JavaScript to toggle video visibility
        const videoContainer = document.getElementById('videoContainer');
        
        function toggleVideo() {
            videoContainer.classList.toggle('visible');
        }

        // Show video for 5 seconds, hide for 5 seconds, repeat
        setInterval(toggleVideo, 5000);
        
        // Optionally, start with the video visible
        toggleVideo();
    </script>
</body>
</html>
