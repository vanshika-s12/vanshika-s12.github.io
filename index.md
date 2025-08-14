title: Homelayout: default

  html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: url('assets/my-background.jpg') no-repeat center center fixed;
    background-size: cover;
    color: #fff;
    overflow: hidden;
  }

  .navbar {
    width: 100%;
    padding: 15px 30px;
    background-color: #1a1a1a;
    display: flex;
    justify-content: center;
    gap: 40px;
    font-size: 16px;
    position: fixed;
    top: 0;
    z-index: 101;
  }
  .navbar a {
    color: #2d2d2d;
    text-decoration: none;
    cursor: pointer;
    padding: 8px 20px;
    border-radius: 7px;
    transition: box-shadow 0.2s;
    box-shadow: none;
    font-weight: 500;
    background: none;
  }
  .navbar a:hover,
  .navbar a:focus {
    color: #2d2d2d;
    box-shadow: 0 4px 18px 0 rgba(0, 0, 0, 0.22), 0 1.5px 4px 0 rgba(0,255,195, 0.25);
    background: none;
    outline: none;
  }

  .main-container {
    display: flex;
    align-items: stretch;
    padding: 0 40px 0 40px;
    gap: 40px;
    box-sizing: border-box;
    height: calc(100vh - 80px);
    margin-top: 80px;
    overflow: hidden;
    margin-left: 290px;
  }

  .sidebar {
    width: 250px;
    min-width: 250px;
    max-width: 250px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    position: fixed;
    top: 80px;
    left: 40px;
    z-index: 20;
    height: calc(100vh - 80px);
    background: transparent;
    pointer-events: auto;
    padding: 0;
    gap: 0;
  }
  .avatar-wrapper {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    overflow: hidden;
    margin: 40px auto 14px auto;
    border: 3px solid #00ffc3;
    background: #fff;
  }
  .avatar-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
  .social-links {
    margin-top: 14px;
    display: flex;
    flex-direction: column;
    gap: 13px;
    align-items: flex-start;
    width: 100%;
    padding-left: 18px;
  }
  .social-link {
    display: flex;
    align-items: center;
    gap: 7px;
    color: #fff;
    text-decoration: none;
    font-size: 16px;
    transition: color 0.15s;
  }
  .social-link:hover {
    color: #00ffc3;
    text-decoration: underline;
  }
  .social-link img {
    width: 24px;
    height: 24px;
    display: inline-block;
    vertical-align: middle;
    filter: drop-shadow(0 0 2px #2229);
    background: white;
    border-radius: 4px;
  }

  .content-box {
    flex: 1;
    background-color: rgba(0, 0, 0, 0.8);
    border-radius: 15px;
    padding: 0 0 25px 0;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
    height: 100%;
    max-height: 100%;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: stretch;
    position: relative;
  }

  .home-vertical-stack {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 28px;
    padding: 40px 0 0 0;
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;
  }
  .intro-text {
    font-size: 1.2em;
    color: #2d2d2d;
    text-align: left;
    font-weight: 500;
    background: rgba(255,255,255,0.58);
    border-radius: 10px;
    width: 100%;
    max-width: 1000px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.11);
    padding: 15px 20px 13px 20px;
    line-height: 1.45;
    margin: 0;
  }
  .updates-heading {
    color: #2d2d2d;
    margin: 0 0 9px 0;
    font-size: 2em;
    font-weight: 700;
    letter-spacing: .5px;
    line-height: 1;
    display: block;
    padding-bottom: 0;
  }
  .updates-scrollbox {
    font-size: 0.98em;
    color: #e0e0e0;
    background: rgba(40,40,40,0.95);
    border-radius: 9px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    padding: 18px 20px;
    width: 100%;
    max-width: 1000px;
    min-width: 310px;
    max-height: 340px;
    overflow-y: auto;
  }

  /* Projects: invisible vertical scrollbar */
  .projects-box {
    width: 100%;
    max-width: 900px;
    margin: 40px auto 0 auto;
    background-color: rgba(0, 0, 0, 0.87);
    border-radius: 15px;
    padding: 28px 26px 24px 26px;
    box-shadow: 0 8px 22px rgba(0,0,0,0.40);
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    min-height: 360px;
    max-height: 400px;
    overflow-y: auto;
    overflow-x: hidden;
    scrollbar-width: none; /* Firefox */
    -ms-overflow-style: none; /* IE and Edge */
  }
  .projects-box::-webkit-scrollbar {
    width: 0px;
    background: transparent;
  }
  .projects-header-row {
    display: flex;
    width: 100%;
    align-items: center;
    margin-bottom: 8px;
    position: relative;
    z-index: 2;
  }
  .projects-header-row h1 {
    color: #2d2d2d;
    margin: 0 0 0 0;
    font-size: 2em;
    font-weight: 700;
    letter-spacing: .5px;
    padding-bottom: 0;
    line-height: 1;
    flex: 1 1 auto;
    text-align: left;
  }
  .projects-list {
    margin-top: 0;
    padding-left: 0;
    width: 100%;
    color: #f4f4f4;
    z-index: 2;
    position: relative;
  }
  .projects-list li {
    margin-bottom: 26px;
    font-size: 1.05em;
    line-height: 1.6;
    list-style: disc inside;
  }
  .projects-list strong {
    color: #00ffc3;
    font-weight: 600;
    font-size: 1.07em;
  }

  .cv-header-row {
    display: flex;
    align-items: center;
    gap: 18px;
    margin-top: 32px;
    margin-left: 36px;
    margin-bottom: 10px;
  }
  .cv-fullscreen-link, .cv-download-link {
    display: inline-block;
    font-size: 16px;
    color: #2d2d2d;
    text-decoration: underline;
    vertical-align: middle;
    cursor: pointer;
    background: none;
    border: none;
    margin-left: 0px;
    margin-right: 20px;
    white-space: nowrap;
    margin-bottom: 0;
  }
  .cv-download-link:hover, .cv-fullscreen-link:hover {
    color: #00ffc3;
  }
  .cv-iframe-box {
    width: 96%;
    height: 80vh;
    border: none;
    margin: 18px 2% 0 2%;
    border-radius: 8px;
    background: #181818;
    box-shadow: 0 2px 10px rgba(0,0,0,0.15);
    flex: 1 1 auto;
  }

  /* SCROLLABLE ABOUT DETAIL BOX */
  .about-detail-container {
    margin: 38px auto 0 auto;
    background: rgba(255,255,255,0.62);
    border-radius: 14px;
    box-shadow: 0 4px 14px rgba(0,0,0,0.10);
    max-width: 1100px;
    min-width: 360px;
    min-height: 420px;
    padding: 28px 32px 26px 32px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .about-detail-intro {
    color: #232323;
    font-size: 1.12em;
    margin-bottom: 18px;
    font-weight: 500;
    letter-spacing: 0.01em;
  }
  .about-detail-scrollbox {
    background: #fff;
    color: #232323;
    font-size: 1.02em;
    border-radius: 10px;
    max-height: 320px;
    min-height: 210px;
    overflow-y: auto;
    text-align: left;
    padding: 19px 26px 14px 26px;
    box-shadow: 0 2px 9px rgba(0,0,0,0.06);
    border: 1px solid #e2e2e2;
    line-height: 1.7;
    width: 100%;
  }
  .projects-box {
    width: 100%;
    max-width: 900px;
    margin: 40px auto 0 auto;
    background-color: rgba(0, 0, 0, 0.87);
    border-radius: 15px;
    padding: 28px 26px 24px 26px;
    box-shadow: 0 8px 22px rgba(0,0,0,0.40);
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    min-height: 360px;
    max-height: 400px;
    overflow-y: auto;
    overflow-x: hidden;
    scrollbar-width: none;
    -ms-overflow-style: none;
  }
  .projects-box::-webkit-scrollbar {
    width: 0px;
    background: transparent;
  }

  /* Video container to ensure full-screen coverage */
  .video-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    z-index: 1; /* Video stays above background but below content */
    opacity: 0; /* Initially hidden */
    transition: opacity 1s ease-in-out; /* Smooth fade effect */
  }

  /* Style the video element */
  video {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures video covers the entire area */
    opacity: 0.3; /* Adjust translucency (0.0 = fully transparent, 1.0 = fully opaque) */
  }

  /* Class to show the video */
  .video-container.visible {
    opacity: 1;
  }

  .view-counter {
    position: fixed;
    bottom: 20px;
    right: 20px;
    z-index: 4;
    background: rgba(0, 0, 0, 0.7);
    padding: 10px;
    border-radius: 5px;
  }

  .view-counter img {
    vertical-align: middle;
    width: 100px;
    height: auto;
  }

{% include mobile-responsive-fixes.html %}

  Home
  Projects
  CV
  Publications
  Contact
  About in Detail




  
    
    Your browser does not support the video tag.
  



  
    
      
    
    
      
        LinkedIn
      
      
        GitHub
      
      
        X (Twitter)
      
      
      
        Email
      
    
  

  
    
    
      
        
          Hi! My name is Dishana. I recently completed high school and was a fully funded YTS scholar at Plaksha University, where I co-built “Marvin,” an autonomous indoor robot. I’ve published a research paper on Quantum Temporal Lattice theory and worked on applied AI projects, including NLP bots and CLI tools. I’ve also freelanced in AI automation and received a 90% scholarship at FIITJEE for academic excellence.
        
        Updates
        
          2025: Started internship at Lawroom AI as a Junior AI Evangelist — contributed to automation in legal AI pipelines, improved model accuracy, and supported prompt engineering for client-focused systems.
          2025: Published a research paper on Quantum Temporal Lattice, a theoretical physics concept merging M-theory with time loops.
          2025: Provided a hands-on demo and guided people on how AI could be efficiently used in real-world scenarios.
          2024: Conducted a detailed theoretical project on Gauss’s Law — performed calculations, thought experiments, and reached a formal conclusion about electric flux distribution.
          2024: Joined The Indian Vidyarthi as a summer student, engaging in workshops on sustainability and global development.
          2023: Participated in a CLI-based hackathon; secured second position and received a ₹7,000 cash prize.
          2023: Explored machine learning; created bots and AI agents — including a Twitter bot that automates pre-call research and lead qualification.
          2022: Received a 100% scholarship to attend the YTS program; built an autonomous robot named Marvin equipped with LiDAR and ultrasonic sensors.
          2021: Received a diploma in software learning.
          2019: Enrolled in a formal software learning program.
          2018: Received a silver medal in the BOB Wonderkid IQ-based competition.
          2018: Built an HTML-based webpage that served as a reference guide for users facing common CMD issues.
          2017: Started training at Infotech Solutions; later began working there.
          2017: Participated in a city-wide Go Green campaign and received a prize for the same.
          2016: Received a token of recognition for raising funds for people with visual and hearing impairments.
        
      
    
    
    
      
        
          Projects
        
        
          
            Marvin (Autonomous Indoor Robot)
            Designed and built an autonomous robot during YTS at Plaksha University. Marvin uses a LiDAR sensor, ultrasonic sensors, and a Raspberry Pi to map and navigate indoor spaces, detect obstacles and people, and carry items. The project included hardware assembly, Python firmware, and hands-on robotics teamwork.
          
          
            CMD Error Detector & Fixer
            Developed a CLI tool to automatically detect common Windows CMD errors, explain them, and offer one-click fixes. Won 2nd place and a cash prize in a competitive hackathon.
          
          
            Programming Languages Predictor
            Created a Python-based tool that predicts which programming language a code snippet is written in. Utilizes various ML models for accurate language detection.
          
          
            Twitter AI Lead Qualifier Bot
            Created a Python-based bot for Twitter/X that uses NLP to qualify leads for outreach, automating profile scanning and message sending. Improved outreach efficiency for freelance clients.
          
          
            ML Bots & Automation Agents
            Built several smart bots, including NLP-powered customer support chatbots and automation pipelines for document management, using Python and cloud APIs for various freelance clients.
          
          
            Gauss’s Law Simulation
            Conducted a project to simulate and analyze the effects of a hole in a charged spherical shell using Gauss’s Law, blending theoretical physics with computational modeling.
          
        
      
    
    
    
      
        
          Click to open in fullscreen
        
        
          Download
        
      
      
    
    
      Contact
      Email me at dishanarupani@gmail.com
    
    
    
      
        This section contains life updates in detail:
        
          2016: Received a token of recognition for raising funds for visually and hearing-impaired individuals during a city-wide charity campaign.
          2017: Participated in a city-wide Go Green campaign; awarded for contributions.
          Began training at Infotech Solutions in hardware troubleshooting and system recovery.
          2018: Built an HTML-based reference webpage to assist users with common CMD errors.
          Won a silver medal in the Brainobrain Wonderkid competition for IQ and logical thinking.
          2019: Enrolled in software learning to deepen understanding of system and program architecture.
          2021: Received a diploma in Computer Science Software Learning from Next Generation Technical Institute.
          2022: Awarded a 100% scholarship to attend the YTS program at Plaksha University.
          Built Marvin, an autonomous robot equipped with LiDAR and ultrasonic sensors for indoor navigation.
          2023: Set up a fundraiser shop at the school fete, raising the second-highest amount for Ukrainian relief efforts (₹19,500).
          Developed ML-driven bots and AI agents including a Twitter automation tool for lead qualification.
          Secured 2nd position and ₹7,000 in a CLI-based hackathon for developing the CMD Error Detector & Fixer tool.
          2024: Selected as a Summer Student at The Indian Vidyarthi, focused on urban sustainability and global policy workshops.
          Theoretically conducted and completed a high-level project on Gauss’s Law, involving precise calculations and thought experiments, culminating in insightful conclusions about electric flux through non-uniform shells.
          2025: Led an AI awareness session with hands-on demos, guiding students and young professionals on how to efficiently leverage AI in their daily workflows.
          Published a research paper on Quantum Temporal Lattice theory in IJSAT, combining string theory and time-loop concepts.
          Began internship as Junior AI Evangelist at Lawroom AI, contributing to the automation of NLP pipelines and improving the quality and performance of legal-tech models.
        
      
    
  



  



  function showSection(section) {
    const sections = ['home', 'projects', 'cv', 'contact', 'about-detail'];
    sections.forEach(id => {
      const el = document.getElementById(id);
      if (el) el.style.display = id === section ? 'block' : 'none';
    });
  }
  document.addEventListener('DOMContentLoaded', function(){
    showSection('home');
  });

  // JavaScript to toggle video visibility
  const videoContainer = document.getElementById('videoContainer');
  
  function toggleVideo() {
    videoContainer.classList.toggle('visible');
  }

  // Show video for 5 seconds, hide for 5 seconds, repeat
  setInterval(toggleVideo, 5000);
  
  // Start with the video visible
  toggleVideo();
