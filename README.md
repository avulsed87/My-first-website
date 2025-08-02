<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Project 1 - Blog post</title>

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Quicksand:wght@300..700&family=Spectral:ital,wght@0,400;0,700;1,400;1,700&display=swap"
    rel="stylesheet" />

  <style>
    /* Reset */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Quicksand', sans-serif;
      background: radial-gradient(circle at center, #1c003f 0%, #0b0019 80%);
      color: #eee;
      line-height: 1.6;
      padding: 20px;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      overflow-x: hidden;
      animation: bgPulse 15s ease-in-out infinite alternate;
      position: relative;
    }

    /* Background pulse animation */
    @keyframes bgPulse {
      0% {
        background-position: center;
        background-size: 200% 200%;
      }

      100% {
        background-position: top left;
        background-size: 220% 220%;
      }
    }

    /* Animated energy orbs */
    .energy-orb {
      position: fixed;
      width: 80px;
      height: 80px;
      background: radial-gradient(circle at center, #d500f9 0%, transparent 70%);
      border-radius: 50%;
      box-shadow:
        0 0 20px #d500f9,
        0 0 35px #f50057,
        0 0 50px #ce93d8;
      opacity: 0.8;
      filter: drop-shadow(0 0 8px #f50057);
      pointer-events: auto;
      z-index: 1;
      cursor: pointer;
      animation: subtleElectric 2s infinite alternate ease-in-out;
      user-select: none;
    }

    /* Right side orbs style */
    .energy-orb.right {
      left: auto;
    }

    /* Electric flicker animation for orbs */
    @keyframes subtleElectric {
      0% {
        box-shadow:
          0 0 15px #b300b3,
          0 0 25px #e040fb,
          0 0 40px #f50057;
        filter: drop-shadow(0 0 12px #f50057);
        opacity: 0.7;
      }

      100% {
        box-shadow:
          0 0 35px #d500f9,
          0 0 60px #f50057,
          0 0 90px #ce93d8;
        filter: drop-shadow(0 0 18px #f50057);
        opacity: 1;
      }
    }

    /* Electric arcs on hover */
    .energy-orb.electric {
      animation: electricArcs 0.3s infinite alternate ease-in-out;
      background: radial-gradient(circle at center, #420069 0%, transparent 80%);
      box-shadow:
        0 0 40px #7c4dff,
        0 0 80px #f50057,
        inset 0 0 15px #440088,
        inset 0 0 30px #651fff;
      filter: drop-shadow(0 0 25px #7c4dff);
      opacity: 1;
    }

    @keyframes electricArcs {
      0% {
        box-shadow:
          0 0 40px #7c4dff,
          0 0 80px #f50057,
          inset 0 0 15px #440088,
          inset 0 0 30px #651fff;
      }

      100% {
        box-shadow:
          0 0 60px #9c27b0,
          0 0 100px #f50057,
          inset 0 0 20px #7c4dff,
          inset 0 0 40px #651fff;
      }
    }

    /* Sparkly purple dark energy text effect */
    .sparkly-text {
      position: relative;
      color: #b388ff;
      font-weight: 700;
      text-shadow:
        0 0 5px #7e57c2,
        0 0 10px #651fff,
        0 0 15px #7c4dff,
        0 0 20px #b388ff,
        0 0 30px #651fff;
      animation: sparklePulse 3s ease-in-out infinite;
      user-select: text;
    }

    @keyframes sparklePulse {
      0%,
      100% {
        text-shadow:
          0 0 5px #7e57c2,
          0 0 10px #651fff,
          0 0 15px #7c4dff,
          0 0 20px #b388ff,
          0 0 30px #651fff;
        color: #b388ff;
      }

      50% {
        text-shadow:
          0 0 8px #9c27b0,
          0 0 15px #d500f9,
          0 0 25px #e040fb,
          0 0 30px #ce93d8,
          0 0 40px #f50057;
        color: #e1bee7;
      }
    }

    /* Header */
    header {
      font-family: 'Orbitron', sans-serif;
      font-size: 3.8rem;
      color: #f5f0ff;
      text-align: center;
      text-shadow:
        0 0 8px #9c27b0,
        0 0 15px #ce93d8,
        0 0 30px #f50057;
      margin-bottom: 30px;
      letter-spacing: 0.2em;
      user-select: none;
      z-index: 10;
      position: relative;
    }

    main {
      flex-grow: 1;
      max-width: 900px;
      margin: 0 auto;
      background: linear-gradient(135deg, #3a006f, #5a00af);
      padding: 25px 40px;
      border-radius: 15px;
      box-shadow:
        0 0 30px #d500f9,
        inset 0 0 15px #7c4dff;
      animation: fadeIn 1.5s ease forwards;
      position: relative;
      z-index: 10;
    }

    /* Fade in main content */
    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    figure {
      margin-bottom: 25px;
      text-align: center;
      user-select: none;
    }

    figure img {
      max-width: 100%;
      border-radius: 15px;
      border: 4px solid #9c27b0;
      box-shadow:
        0 0 20px #ce93d8,
        0 0 40px #f50057;
      transition: transform 0.3s ease;
    }

    figure img:hover {
      transform: scale(1.05) rotate(-2deg);
    }

    .post-category {
      font-family: 'Spectral', serif;
      font-weight: 700;
      font-size: 1.15rem;
      color: #e040fb;
      margin-bottom: 10px;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      text-shadow: 0 0 5px #b300b3;
      user-select: none;
    }

    h1,
    h2,
    h3,
    h4 {
      font-family: 'Spectral', serif;
      color: #f5f0ff;
      text-shadow:
        0 0 8px #d500f9,
        0 0 20px #aa00ff;
      margin-bottom: 15px;
      line-height: 1.2;
      user-select: none;
    }

    /* Ensure h1 same color as others */
    h1 {
      color: #f5f0ff;
    }

    h2 {
      font-weight: 600;
      margin-top: 25px;
    }

    h3 {
      font-weight: 500;
      margin-top: 20px;
    }

    #post-info {
      font-style: italic;
      color: #ce93d8;
      margin-bottom: 20px;
      user-select: none;
    }

    p {
      font-size: 1.1rem;
      margin-bottom: 20px;
      color: #ddd;
      user-select: text;
    }

    a {
      color: #ff80ab;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }

    a:hover {
      color: #f50057;
      text-shadow:
        0 0 5px #f50057,
        0 0 10px #f50057;
    }

    ul {
      margin-left: 20px;
      margin-bottom: 25px;
      color: #e1bee7;
      user-select: none;
    }

    ul li {
      margin-bottom: 12px;
      line-height: 1.4;
    }

    /* Related posts styling */
    #related-posts {
      background: #2c0055;
      padding: 20px 25px;
      border-radius: 12px;
      box-shadow: inset 0 0 10px #b300b3;
      margin-top: 35px;
      user-select: none;
    }

    #related-posts h4 {
      margin-bottom: 15px;
      font-weight: 700;
      color: #f48fb1;
    }

    #related-posts ul {
      list-style: none;
      padding-left: 0;
    }

    #related-posts ul li {
      margin-bottom: 12px;
      font-weight: 600;
      cursor: pointer;
      color: #f8bbd0;
      padding: 8px 12px;
      border-radius: 8px;
      transition: background-color 0.3s ease, color 0.3s ease;
    }

    #related-posts ul li:hover {
      background: #f50057;
      color: white;
      text-shadow:
        0 0 8px #f50057,
        0 0 15px #f50057;
    }

    #related-posts ul li a {
      color: inherit;
      text-decoration: none;
      display: block;
      user-select: text;
    }

    /* Footer */
    footer {
      margin-top: 40px;
      padding: 15px 0;
      text-align: center;
      font-family: 'Spectral', serif;
      color: #ce93d8;
      font-style: italic;
      user-select: none;
      border-top: 1px solid #5a00af;
      position: relative;
      z-index: 10;
    }

    /* Iframe styling */
    iframe {
      display: block;
      margin: 30px auto;
      border-radius: 15px;
      box-shadow:
        0 0 25px #d500f9,
        0 0 45px #f50057;
      max-width: 100%;
    }
  </style>
</head>

<body>
  <!-- Left side orbs -->
  <div class="energy-orb" id="orb1"></div>
  <div class="energy-orb" id="orb2"></div>
  <div class="energy-orb" id="orb3"></div>

  <!-- Right side orbs -->
  <div class="energy-orb right" id="orb4"></div>
  <div class="energy-orb right" id="orb5"></div>
  <div class="energy-orb right" id="orb6"></div>

  <header>
    My first website
  </header>

  <main>
    <figure>
      <img src="Frieza.jpg" alt="Originalni piclop" />
    </figure>

    <article>
      <div class="post-category">
        My programming journey
      </div>

      <h1>
        Getting started as a Front-End developer
      </h1>

      <div id="post-info">
        25 July 2025 - posted by Arman Kara
      </div>

      <p>
        Breaking into the world of front end web development
        is an exciting journey. This is by the way <a href="#">the paragraph</a>.
        Front end developers are responsible for creating the
        parts of the website that users interact with.
        Btw here is a <a href="http://www.google.com" target="_blank" rel="noopener noreferrer">link</a> of Google :D
      </p>

      <p class="sparkly-text">
        I honestly was bored AF at the start and I was stuck with the "Tutorial hell", after a while I decided to
        follow 1 course only and here I am. I believe I finished with the first part of HTML and CSS and now it's
        time to level up baby :D
      </p>

      <h2>Core Technologies For Web Development</h2>

      <h3>The Fundamental technology</h3>

      <ul>
        <li>
          HTML (HyperText Markup Language) is the backbone of any website
          used to structure content like headings, paragraphs, and images.
        </li>

        <li>
          CSS (Cascading Style Sheets) brings the layout and design to life,
          controlling the website’s appearance across different devices and screen sizes.
        </li>

        <li>
          JavaScript adds functionality and interactivity,
          making elements respond to user inputs
          and enhancing the user experience.
        </li>
      </ul>

      <p>
        After gaining a strong understanding of HTML, CSS, and JavaScript,
        it's important to put your knowledge into practice.
        One of the best ways to learn is by working on small
        projects like personal websites, portfolios, or simple web applications.
      </p>

      <iframe width="560" height="315" src="https://www.youtube.com/embed/8fku-CRhkIU?si=UMhZHoiwMD1JcBEe" title="YouTube video player"
        frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </article>

    <section id="related-posts">
      <h4>Related posts</h4>
      <ul>
        <li><a href="#">The 3 most popular Javascript frameworks</a></li>
        <li><a href="#">Best Blogs to Learn Front End Development</a></li>
        <li><a href="#">CSS Nesting is Now Native - Here’s How to Use It</a></li>
      </ul>
    </section>
  </main>

  <footer>
    Arman Kara - All Rights Reserved
  </footer>

  <!-- Dragon Ball style music - autoplay & loop WITHOUT controls -->
  <audio id="bg-music" autoplay loop>
    <source src="https://vgmsite.com/soundtracks/dragon-ball-z-saiyan-saga/abkbcpcz/01%20-%20Cha-La%20Head-Cha-La.mp3" type="audio/mpeg" />
    Your browser does not support the audio element.
  </audio>

  <script>
    // Smooth floating orbs with random free movement and electric flicker + hover electric effect

    const orbs = Array.from(document.querySelectorAll('.energy-orb'));
    const screenWidth = window.innerWidth;
    const screenHeight = window.innerHeight;

    // Initialize orb data with random positions and velocities
    const orbData = orbs.map(() => ({
      x: Math.random() * (screenWidth * 0.1) + 10, // start near left or right edges later fixed in loop
      y: Math.random() * (screenHeight - 100) + 50,
      vx: (Math.random() * 0.6 + 0.2) * (Math.random() > 0.5 ? 1 : -1),
      vy: (Math.random() * 0.6 + 0.2) * (Math.random() > 0.5 ? 1 : -1),
    }));

    // Fix starting x positions for left or right orbs
    orbs.forEach((orb, i) => {
      if (orb.classList.contains('right')) {
        orbData[i].x = screenWidth - orbData[i].x - 100;
      } else {
        orbData[i].x = orbData[i].x;
      }
      orb.style.left = orbData[i].x + 'px';
      orb.style.top = orbData[i].y + 'px';
    });

    function animate() {
      orbs.forEach((orb, i) => {
        const data = orbData[i];
        data.x += data.vx;
        data.y += data.vy;

        // Bounce inside a vertical range near side of screen (about 150px horizontal range)
        if (orb.classList.contains('right')) {
          if (data.x > screenWidth - 80) data.vx = -data.vx;
          if (data.x < screenWidth - 180) data.vx = -data.vx;
        } else {
          if (data.x > 180) data.vx = -data.vx;
          if (data.x < 10) data.vx = -data.vx;
        }

        // Bounce vertically in viewport limits (50 to screenHeight - 50)
        if (data.y > screenHeight - 100) data.vy = -data.vy;
        if (data.y < 50) data.vy = -data.vy;

        orb.style.left = data.x + 'px';
        orb.style.top = data.y + 'px';
      });

      requestAnimationFrame(animate);
    }
    animate();

    // Hover electric effect toggle
    orbs.forEach(orb => {
      orb.addEventListener('mouseenter', () => {
        orb.classList.add('electric');
      });
      orb.addEventListener('mouseleave', () => {
        orb.classList.remove('electric');
      });
    });

    // Attempt to autoplay music immediately (some browsers may block)
    const audio = document.getElementById('bg-music');
    audio.volume = 0.5;
    audio.play().catch(() => {
      // Autoplay blocked, no action
    });

  </script>
</body>

</html>

