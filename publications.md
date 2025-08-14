
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publications - Translucent GIF with Background</title>
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

        /* Navbar styling */
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

        /* Container for the GIF */
        .gif-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1; /* GIF stays above content, below navbar */
            opacity: 0; /* Initially hidden */
            transition: opacity 1s ease-in-out; /* Smooth fade effect */
        }

        /* Style the GIF */
        img {
            width: 100vw;
            height: 100vh;
            object-fit: cover; /* Ensures GIF covers the entire viewport */
            display: block; /* Removes default spacing */
            opacity: 0.3; /* Subtle transparency */
        }

        /* Class to show the GIF */
        .gif-container.visible {
            opacity: 1;
        }

        /* Content behind the GIF */
        .content {
            position: relative;
            z-index: 0; /* Content stays below the GIF */
            padding: 20px;
            margin-top: 60px; /* Offset for navbar */
            color: #fff; /* White text for contrast */
            text-align: center;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7); /* Text shadow for readability */
        }

        /* Fallback message if GIF fails to load */
        .fallback {
            display: none;
            color: red;
            font-size: 18px;
            text-align: center;
            padding: 20px;
            position: fixed;
            top: 60px; /* Below navbar */
            left: 0;
            width: 100%;
            z-index: 2;
            background: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="publications.html">Publications</a></li>
        </ul>
    </nav>

    <!-- GIF container -->
    <div class="gif-container" id="gifContainer">
        <img src="assets/intro.gif" alt="Intro GIF" id="introGif">
    </div>

    <!-- Fallback message -->
    <div class="fallback" id="fallbackMessage">
        Failed to load GIF. Please check the file path: assets/intro.gif
    </div>

    <!-- Sample content behind the GIF -->
    <div class="content">
        <h1>Publications</h1>
        <p>This is the publications page with a translucent GIF that appears and vanishes.</p>
    </div>

    <script>
        // JavaScript to toggle GIF visibility
        const gifContainer = document.getElementById('gifContainer');
        const introGif = document.getElementById('introGif');
        const fallbackMessage = document.getElementById('fallbackMessage');

        // Log file paths for debugging
        console.log('GIF path:', introGif.src);
        console.log('Background path:', getComputedStyle(document.body).backgroundImage);

        // Check if GIF loads successfully
        introGif.onerror = () => {
            console.error('Error: GIF failed to load at assets/intro.gif');
            fallbackMessage.style.display = 'block'; // Show fallback if GIF fails
        };

        introGif.onload = () => {
            console.log('GIF loaded successfully');
            fallbackMessage.style.display = 'none'; // Hide fallback if GIF loads
        };

        function toggleGif() {
            gifContainer.classList.toggle('visible');
        }

        // Show GIF for 5 seconds, hide for 5 seconds, repeat
        setInterval(toggleGif, 5000);

        // Start with the GIF visible
        toggleGif();
    </script>
</body>
</html>
