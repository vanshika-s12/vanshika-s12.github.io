---
title: Home
layout: default
---

<style>
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

  .glow-overlay {
    pointer-events: none;
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    z-index: 105;
    overflow: hidden;
    mix-blend-mode: lighten;
  }
  .glow-light, .glow-light2 {
    position: absolute;
    width: 180vw;
    height: 120vh;
    left: -100vw;
    top: -10vh;
    filter: blur(80px);
    opacity: 0.65;
  }
  .glow-light {
    background: linear-gradient(110deg, transparent 10%, #fff 48%, #fff 55%, transparent 90%);
    animation: lightflow 3.5s linear infinite;
  }
  .glow-light2 {
    background: linear-gradient(70deg, transparent 30%, #fff 54%, #fff 60%, transparent 80%);
    animation: lightflow2 7s linear infinite;
    opacity: 0.35;
  }
  @keyframes lightflow {
    0% { left: -100vw; }
    100% { left: 100vw; }
  }
  @keyframes lightflow2 {
    0% { left: 100vw; }
    100% { left: -80vw; }
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
</style>

<div class="glow-overlay">
  <div class="glow-light"></div>
  <div class="glow-light2"></div>
</div>

<div class="navbar">
  <a onclick="showSection('home')">Home</a>
  <a onclick="showSection('projects')">Projects</a>
  <a onclick="showSection('cv')">CV</a>
  <a onclick="showSection('publications')">Publications</a>
  <a onclick="showSection('contact')">Contact</a>
  <a onclick="showSection('about-detail')">About in Detail</a>
</div>

<div class="main-container">
  <div class="sidebar">
    <div class="avatar-wrapper">
      <img src="assets/avatar.jpeg" alt="Your Profile Picture">
    </div>
    <div class="social-links">
      <a class="social-link" href="https://www.linkedin.com/in/vanshika-s-304185308/" target="_blank">
        <img src="assets/linkedin.svg" alt="LinkedIn logo" onerror="this.onerror=null;this.src='https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/linkedin.svg';">LinkedIn
      </a>
      <a class="social-link" href="https://github.com/vanshika-s12" target="_blank">
        <img src="assets/github.svg" alt="GitHub logo" onerror="this.onerror=null;this.src='https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/github.svg';">GitHub
      </a>
      <a class="social-link" href="https://mail.google.com/mail/?view=cm&fs=1&to=vanshikasachdevaaa12@gmail.com" target="_blank" rel="noopener">
        <img src="assets/email.svg" alt="Email logo" onerror="this.onerror=null;this.src='https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/maildotru.svg';">Email
      </a>
    </div>
  </div>

  <div class="content-box" id="content-area">
    <!-- HOME -->
    <div id="home">
      <div class="home-vertical-stack">
        <div class="intro-text" id="intro-text">
          Hi! I'm Vanshika, a driven student passionate about science, AI, and research. I recently completed high school and have engaged in global issue workshops at The Indian Vidyarthi, focusing on urban water management, sustainability, and innovative business strategies. My journey includes authoring a research paper on Quantum Temporal Lattice Theory (QTL) in IJSAT, developing practical ML and automation tools, and consistently winning accolades in science exhibitions and hackathons. I thrive on creative problem-solving, research writing, and building solutions that blend technology with real-world impact.
        </div>
        <h1 class="updates-heading">Updates</h1>
        <div class="updates-scrollbox">
          <p><strong>2025:</strong> Contributed to a peer-reviewed research paper on Quantum Temporal Lattice Theory, exploring time manipulation using quantum mechanics and string theory.</p>
          <p><strong>2024:</strong> Selected as a Summer Student at The Indian Vidyarthi, India; participated in workshops on global issues and sustainable practices, and wrote on urban water management.</p>
          <p><strong>2024:</strong> Won First Prize in the annual school science exhibition for the most innovative and impactful project.</p>
          <p><strong>2023:</strong> Received a 90% scholarship for academic excellence at PW.</p>
          <p><strong>2023:</strong> Won a ₹7,000 cash prize in a hackathon and secured 2nd place in a CLI-based automation challenge for building the CMD Error Detector and Fixer tool.</p>
          <p><strong>2023:</strong> Participated at the national level in spell bees and was invited to India’s Got Talent.</p>
          <p><strong>2023:</strong> Secured 2nd position in Nav Sadhana Singing Competition among thousands of participants.</p>
          <p><strong>2022-2024:</strong> Developed and published multiple ML/AI projects: Spam Email Classifier, Sentiment Analyzer, Pattern Finder, Digit Recognizer, Log Error Detector, and Regex-based Data Extractor.</p>
          <p><strong>2016-2022:</strong> Raised donations for visually and hearing-impaired children and consistently participated in academic and extracurricular events.</p>
        </div>
      </div>
    </div>
    <!-- PROJECTS -->
    <div id="projects" style="display: none;">
      <div class="projects-box">
        <div class="projects-header-row">
          <h1>Projects</h1>
        </div>
        <ul class="projects-list">
          <li>
            <strong>Quantum Temporal Lattice Theory (QTL), IJSAT</strong><br>
            Authored a peer-reviewed research paper exploring theoretical concepts of localized time manipulation through quantum mechanics, string theory, and holographic encoding. Proposed the creation of time loops by altering encoded space-time data.
          </li>
          <li>
            <strong>Spam Email Classifier</strong><br>
            Built a Python spam detector using Scikit-learn (Naive Bayes), regex for feature extraction, and accuracy/loss functions for evaluation.
          </li>
          <li>
            <strong>Simple Sentiment Analyzer</strong><br>
            Classified sentences as positive/negative using logistic regression and regex-based text preprocessing. Visualized loss/accuracy plots.
          </li>
          <li>
            <strong>File Name Pattern Finder</strong><br>
            Developed a tool to scan directories and use regex for finding files matching patterns (e.g., dates, versions), with optional ML-based classification.
          </li>
          <li>
            <strong>Handwritten Digit Recognizer (MNIST)</strong><br>
            Used the MNIST dataset with neural networks (Keras/Scikit-learn); logged loss and accuracy during training and visualized misclassified digits.
          </li>
          <li>
            <strong>Basic Log File Error Detector</strong><br>
            Employed regex to find error patterns in log files, used clustering (KMeans) to group similar errors, and visualized cluster loss.
          </li>
          <li>
            <strong>Regex-based Data Extractor with ML Post-Processing</strong><br>
            Extracted phone numbers/emails using regex, then classified snippets with a simple ML model, plotting loss during training.
          </li>
        </ul>
      </div>
    </div>
    <!-- CV SECTION -->
    <div id="cv" style="display: none;">
      <div class="cv-header-row">
        <a class="cv-fullscreen-link" href="assets/vanshika_cv.pdf" target="_blank" rel="noopener">
          Click to open in fullscreen
        </a>
        <a class="cv-download-link" href="assets/vanshika_cv.pdf" download>
          Download
        </a>
      </div>
      <iframe class="cv-iframe-box" src="assets/vanshika_cv.pdf"></iframe>
    </div>
    <div id="publications" style="display: none;">
      <h1>Publications</h1>
      <p>
        I have published a research paper on Quantum Temporal Lattice Theory (QTL) in the International Journal for Science, Arts and Technology (IJSAT).<br>
        The paper explores the concept of localized time manipulation using quantum mechanics, string theory, and holographic encoding, proposing ways to create time loops by altering encoded space-time data.
      </p>
    </div>
    <div id="contact" style="display: none;">
      <h1>Contact</h1>
      <p>Email me at <a href="mailto:vanshikasachdevaaa12@gmail.com">vanshikasachdevaaa12@gmail.com</a></p>
    </div>
    <!-- ABOUT IN DETAIL: SCROLLABLE BOX -->
    <div id="about-detail" style="display: none;">
      <div class="about-detail-container">
        <div class="about-detail-intro">This section contains life updates in detail:</div>
        <div class="about-detail-scrollbox">
          <strong>2025:</strong> Contributed to a peer-reviewed research paper on Quantum Temporal Lattice Theory (QTL) in IJSAT, investigating theoretical models for time manipulation using quantum mechanics and string theory.<br><br>
          <strong>2024:</strong> Selected as a Summer Student at The Indian Vidyarthi, India. Participated in global issue workshops, wrote on urban water management, and explored sustainable practices and innovative business strategies.<br><br>
          <strong>2024:</strong> Won First Prize in the school science exhibition for the most innovative and impactful project, demonstrating creativity and strong presentation skills.<br><br>
          <strong>2023:</strong> Received a 90% merit scholarship at PW for academic excellence.<br>
          Won a ₹7,000 cash prize and 2nd place in a CLI-based hackathon for building the CMD Error Detector and Fixer tool.<br>
          Invited to India’s Got Talent at the national level and participated in national-level spell bees.<br>
          Secured second position in Nav Sadhana Singing Competition among thousands of competitors.<br><br>
          <strong>2016-2022:</strong> Raised donations for visually and hearing-impaired children, participated in academic and extracurricular competitions, and consistently delivered innovative projects in annual science exhibitions.
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  function showSection(section) {
    const sections = ['home', 'projects', 'cv', 'publications', 'contact', 'about-detail'];
    sections.forEach(id => {
      const el = document.getElementById(id);
      if (el) el.style.display = id === section ? 'block' : 'none';
    });
  }
  document.addEventListener('DOMContentLoaded', function(){
    showSection('home');
  });
</script>
