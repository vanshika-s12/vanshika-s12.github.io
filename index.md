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

        /* Container for the video */
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

        /* Style the video */
        video {
            width: 100vw;
            height: 100vh;
            object-fit: cover; /* Ensures video covers the entire viewport */
            display: block; /* Removes default spacing */
            opacity: 0.3; /* Subtle transparency */
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

        /* Fallback message if video fails to load */
        .fallback {
            display: none;
            color: red;
            font-size: 18px;
            text-align: center;
            padding: 20px;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 2;
            background: rgba(0, 0, 0, 0.5); /* Semi-transparent background for visibility */
        }
    </style>
</head>
<body>
    <!-- Video container -->
    <div class="video-container" id="videoContainer">
        <video id="introVideo" autoplay muted loop>
            <source src="assets/intro.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>

    <!-- Fallback message -->
    <div class="fallback" id="fallbackMessage">
        Failed to load video. Please check the file path: assets/intro.mp4
    </div>

    <!-- Sample content behind the video -->
    <div class="content">
        <h1>Welcome to My Page</h1>
        <p>This is some content behind the translucent video that appears and vanishes.</p>
    </div>

    <script>
        // JavaScript to toggle video visibility
        const videoContainer = document.getElementById('videoContainer');
        const introVideo = document.getElementById('introVideo');
        const fallbackMessage = document.getElementById('fallbackMessage');

        // Log file paths for debugging
        console.log('Video path:', introVideo.src);
        console.log('Background path:', getComputedStyle(document.body).backgroundImage);

        // Check if video loads successfully
        introVideo.onerror = () => {
            console.error('Error: Video failed to load at assets/intro.mp4');
            fallbackMessage.style.display = 'block'; // Show fallback if video fails
        };

        introVideo.onloadeddata = () => {
            console.log('Video loaded successfully');
            fallbackMessage.style.display = 'none'; // Hide fallback if video loads
        };

        function toggleVideo() {
            videoContainer.classList.toggle('visible');
        }

        // Show video for 5 seconds, hide for 5 seconds, repeat
        setInterval(toggleVideo, 5000);

        // Start with the video visible
        toggleVideo();
    </script>
</body>
</html>
