<script>
    import ExperienceCard from './ExperienceCard.svelte'; // Adjust the path as necessary
    import ProjectCard from './ProjectCard.svelte'; // Adjust the import path as needed
    const experiences = [
    
    {
            startDate: 'July 2024',
            endDate: 'Present',
            positionTitle: 'Web Designer (contract)',
            companyName: 'Seed Sprout Spoon',
            description: 'Redesigned the Seed Sprout Spoon website for improved user experience and responsive design. Focused on modern visuals and usability to enhance engagement driving more sales for the client..',
            skills: ['Customer Service', 'Food Safety', 'Event Coordination']
        },
        {
            startDate: 'Jan 2023',
            endDate: 'Present',
            positionTitle: 'Art Handler/Preparator',
            companyName: 'History Museum | Pulitzer Arts Foundation',
            description: 'Responsible for the installation and maintenance of museum exhibits, ensuring proper display and handling of artifacts.',
            skills: ['Art Handling', 'Team Collaboration', 'Installation Techniques']
        },
        {
            startDate: 'May 2021',
            endDate: 'Present',
            positionTitle: 'Bartender',
            companyName: 'Seed Sprout Spoon',
            description: 'Assisted in organizing and serving food and beverages at private events, focusing on customer service and attention to detail.',
            skills: ['Customer Service', 'Food Safety', 'Event Coordination']
        }
        // Add more experiences as needed
    ];
    
    
    
    const projects = [
        {
            title: "Seed Sprout Spoon Website Redesign",
            description: "Redesigned the Seed Sprout Spoon website for improved user experience and responsive design. Focused on modern visuals and usability to enhance engagement driving more sales for the client.",
            imageUrl: "/images/HomeScreen.png", // Replace with your actual image URLs
            skills: ['SquareSpace', 'CSS', 'JavaScript'],
            link: "https://tuna-jaguar-6sx8.squarespace.com/config/"
        },
        {
            title: "Web Portfolio V1",
            description: "A personal portfolio showcasing projects with technologies like HTML, CSS, JavaScript, and Svelte, highlighting design and development skills.",
            imageUrl: "/images/PortfolioV1.png", // Replace with your actual image URLs
            skills: ['Sveltekit', 'CSS', 'JavaScript', 'git'],
            link: ""
        },
        {
            title: "Butcher Shop Application (Work In Progress)",
            description: "A web app for a butcher shop offering online ordering, inventory management, and customer tracking using React, Node.js, and MongoDB.",
            imageUrl: "/images/Butcher_shop_home.png", // Replace with your actual image URLs
            skills: ['React', 'Node.js', 'MongoDB', "REST API"],
            link: "https://github.com/Andrewfischer100/Butcher_Shop"
        },
        {
            title: "Along The Way (Work In Progress)",
            description: "A road trip planner using Angular that calculates routes, provides real-time weather, suggests points of interest, and estimates fuel costs.",
            imageUrl: "/images/logo-with-text.png", // Replace with your actual image URLs
            skills: ['Angular', 'Google Places API', 'OpenWeatherMap'],
            link: "https://github.com/Apr-23-LC-LiftOff-STL/Liftoff-Eswari-"
        },
        // Add more projects as needed
    ];
    
    
    let mouseX = 0;
    let mouseY = 0;
    
    function handleMouseMove(event) {
      mouseX = event.clientX;
      mouseY = event.clientY;
    }
    
    let activeSection = ''; // This will hold the currently active section
    
    
    
    function handleNavClick(section) {
    activeSection = section;
    const target = document.getElementById(section);
    target.scrollIntoView({ behavior: 'smooth' });
    }
    
    
    
    </script>
    
    <style>
        * {
        box-sizing: border-box;
    }
    
    :global(body) {
        margin: 0;
        padding: 0;
        background-color: #1a0731; /* Dark blue-purple background */
        color: #f6fbfd; /* Azure blue text */
        font-family: 'Roboto', sans-serif;
        min-height: 100vh;
        overflow-x: hidden; /* Prevent horizontal scrolling */
        overflow-y: auto; /* Allow vertical scrolling */
        width: 100%;
    }
    
    
    .main-container {
    display: flex;
    flex-direction: row;
    max-width: 1200px;
    min-height: 100vh; /* Changed from height: 100vh to min-height */
    margin: 0 auto;
    overflow-y: auto; /* Allow scrolling when content exceeds height */
}
    
.container {
    width: 50%;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    overflow: hidden; /* Ensure no child elements overflow */
}
    
    
    .nav {
        display: flex;
        flex-direction: column;
        z-index: 3;
        margin-top: -30px;
        padding-left: 30px;
    }
    
    .nav ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
    }
    
    .nav li {
        margin: 10px 0;
        position: relative;
    }
    
    .nav a {
        color: rgba(238, 196, 255, 0.8);
        text-decoration: none;
        font-size: 1em;
        transition: color 0.3s, transform 0.3s, padding-left 0.3s;
        padding-left: 10px;
    }
    .nav a.active {
        color: rgb(255, 255, 255);
        font-weight: bold;
    }
    
    .nav a:hover {
        color: rgb(255, 255, 255);
    }
    
    /* Pseudo-element for the line */
    .nav li::before {
        content: '';
        position: absolute;
        left: 0;
        top: 50%;
        width: 0px;
        height: 1%;
        background-color: rgba(238, 196, 255, 0.8);
        transform: translateY(-50%);
        transition: width 0.3s;
    }
    
    .nav li:hover::before {
        width: 50px; /* Expand the line to full width on hover */
    }
    
    .nav li:hover a {
        padding-left: 60px; /* Increase padding on hover to shift text to the right */
    }
    
    
    .text-container {
      width: 100%; /* Take full width for text */
      text-align: left; /* Align text to the left */
      padding: 2rem; /* Padding for spacing */
      z-index: 2; /* Ensure this is above the glow effect */
    }
    
    .info-container {
      width: 50%; /* Fixed width for info */
      max-height: 100vh; /* Limit the height to viewport */
      text-align: left; /* Align text to the left */
      padding: 2rem; /* Add padding for spacing */
      overflow-y: scroll; /* Keep vertical scrolling enabled */
      scrollbar-width: none; /* For Firefox */
      z-index: 2; /* Ensure this is above the glow effect */
    }
    
    /* Hide scrollbar for WebKit browsers (Chrome, Safari, Edge) */
    .info-container::-webkit-scrollbar {
      display: none; /* Hide the scrollbar */
    }
    
    
    h1 {
      font-size: 3.25rem; /* Title size */
      margin: 0;
    }
    
    h2 {
      font-size: 2.5rem; /* Subtitle size */
      color: #f6fbfd; /* Subtitle color */
        margin-bottom: 10px; /* Space below subtitles */
      margin: 0.5rem 0; /* Space between title and subtitle */
    }
    
    .paragraph {
      font-family: 'Inter', sans-serif;
      font-size: 1.0rem; /* Smaller subtitle size */
      color: rgba(240, 229, 252, 0.6); /* Light color with transparency */
      margin-top: 20px; /* No extra margin */
      font-family: 'Inter', sans-serif; /* Modern, clean typeface */
      line-height: 1.6; /* Increased leading for roomier text */
      letter-spacing: -0.02em; /* Slightly tightened tracking */
    }
    
    
    .bold-link {
        text-decoration: none;
        color: aliceblue;
        transition: color 0.3s ease-in-out, text-decoration 0.3s ease-in-out; /* Smooth transition for both color and underline */
    }
    
    .bold-link:hover {
        color: rgb(0, 252, 134);
    }
    
    /* Styles for the resume link */
    #resume_link {
        display: inline-block;
        padding: 10px 15px;
        border: 1px solid rgb(0, 255, 191);
        border-radius: 5px;
        text-decoration: none;
        font-weight: bold;
        color: #ffffff;
        transition: all 0.3s ease;
    }
    
    #resume_link:hover {
        background-color: rgba(0, 0, 0, 0.05);
        color: rgb(0, 255, 191);
        border-color: rgba(255, 255, 255, 0.226);
    }
    
    /* Styles for the portfolio link */
    #portfolio_link {
        display: inline-block;
        padding: 10px 15px;
        border: 1px solid rgb(0, 255, 191);
        border-radius: 5px;
        text-decoration: none;
        font-weight: bold;
        color: #ffffff;
        transition: all 0.3s ease;
    }
    
    #portfolio_link:hover {
        background-color: rgba(0, 0, 0, 0.05);
        color: rgb(0, 255, 191);
        border-color: rgba(255, 255, 255, 0.226);
    }
    
    /* Icon styling (optional) */
    #resume_link i, #portfolio_link i {
        margin-left: 5px; /* Adds space between the text and icon */
    }
    
    
    
    .glow-effect {
  position: fixed;
  top: 0;
  left: 0;
  width: 40vw; /* Equal width and height for a circle */
  height: 40vw; /* Match the width to maintain a circular shape */
  overflow: hidden;
  background: radial-gradient(
    circle,
    rgba(0, 170, 255, 0.15) 0%,
    rgba(0, 170, 255, 0.05) 30%,
    rgba(0, 170, 255, 0.03) 60%,
    #1a0731 100%,
    transparent 100%
  );
  border-radius: 50%; /* Keep it circular */
  pointer-events: none;
  transition: opacity 0.2s ease-out;
  opacity: 1;
  z-index: 1;
  transform: translate(calc(var(--mouseX) - 100vw), calc(var(--mouseY) - 100vw)); /* Adjust based on size */
}


    
    .glow-effect {
    /* Adjust the transform to take the element size into account */
    transform: translate(calc(var(--mouseX) - 50%), calc(var(--mouseY) - 50%));
}

    
    p {
      font-size: 1.2rem; /* Adjust font size for the paragraph */
      line-height: 1.5; /* Line height for readability */
    }
    
  /* Social Links */
.social-links {
    display: flex; /* Flexbox for horizontal alignment */
    justify-content: center; /* Center the social links */
    margin: 20px 20px; /* Space around social links */
    z-index: 3; /* Ensure this is above the glow effect */
}

.social-links ul {
    list-style-type: none; /* Remove bullet points */
    padding: 0; /* Remove padding */
    margin: 0; /* Remove margin */
    display: flex; /* Align items horizontally */
}

.social-links a {
    margin: 0 10px; /* Space between social links */
    color: rgba(240, 229, 252, 0.6); /* Initial color */
    text-decoration: none; /* Remove underline */
    padding: 10px; /* Reduced padding to limit hover bleed */
    position: relative; /* Relative positioning for pseudo-elements */
    transition: transform 0.3s ease, color 0.3s ease; /* Smooth transition */
}

.social-links a:hover {
    color: rgba(240, 229, 252, 1); /* Full color on hover */
    transform: scale(1.1); /* Slight scale on hover */
}

/* Icon Styling */
.social-links i {
    font-size: 2rem; /* Use font size to control icon size */
}

/* Optional: Add a hover effect like a shadow or border without bleed */
.social-links a::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    box-shadow: 0 0 15px rgba(240, 229, 252, 0.5); /* Glow effect on hover */
    opacity: 0;
    transition: opacity 0.3s ease;
}

.social-links a:hover::before {
    opacity: 1; /* Show the shadow/glow on hover */
}

    @media (max-width: 768px) {
      * {
          box-sizing: border-box; /* Ensure padding is included in width calculations */
      }
    
        .main-container {
            display: flex;
            flex-direction: column;
            height: 100vh; /* Ensure the main container fills the viewport height */
            width: 100%;
            margin: 0 auto;
            overflow: hidden; /* Prevent both horizontal and vertical overflow */    }
    
      .container {
        width: 100%; /* Each container takes full width */
        padding: 20px; /* Keep padding for spacing inside the containers */
        margin: 10px auto; /* Auto margin horizontally will center the element */
      }
    
      .text-container,
      .info-container { 
        max-width: 100%;
        overflow-y: auto; 
            width: 100%;
            padding: 20px;
            margin: 0;
            height: auto;
      }
    
      .short-text {
        display:contents; /* Hide short text by default */
      }
    
      .social-links {
        justify-content: flex-start; /* Align social links to the left */
        margin-left: 10px; /* Add a little margin for space from the edge */
      }
    
      /* Adjust icon size for smaller screens */
      .social-links i {
        scale: 200%; /* Reduce the size of the icons on smaller screens */
      }
    }
    
    
    </style>
    
    <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    </head>
    
    <!-- svelte-ignore a11y-no-redundant-roles -->
    <section class="main-container" on:mousemove={handleMouseMove} role="region">
    <div class="glow-effect" style="--mouseX: {mouseX}px; --mouseY: {mouseY}px;"></div>
    
    <div class="container">
        <div class="text-container">
            <h1>Andrew Fischer</h1> <!-- Replace with your name -->
            <h2>Full Stack Developer & Designer</h2> <!-- Replace with your subtitle -->
            <p class="paragraph">Creative designer capable of building company assets and business collateral as well as hand developing functional code for your website or application. </p> <!-- Replace with your transparent subtitle -->
        </div>
    
        <div class="nav">
            <ul>
                <li>
                    <a href="#about" on:click={() => handleNavClick('about')} class:active={activeSection === 'about'}>ABOUT</a>
                </li>
                <li>
                    <a href="#experience" on:click={() => handleNavClick('experience')} class:active={activeSection === 'experience'}>EXPERIENCE</a>
                </li>
                <li>
                    <a href="#projects" on:click={() => handleNavClick('projects')} class:active={activeSection === 'projects'}>PROJECTS</a>
                </li>
            </ul>
            
        </div>
        
        
    
        <!-- Social Links -->
        <div class="social-links">
            <ul>
                <li><a href="https://www.instagram.com/AndrewFischer100" target="_blank"><i class="fab fa-instagram"></i></a></li>
                <li><a href="https://github.com/Andrewfischer100" target="_blank"><i class="fab fa-github"></i></a></li>
                <li><a href="https://www.linkedin.com/in/afischer100" target="_blank"><i class="fab fa-linkedin"></i></a></li>
                <li><a href="https://afisch2014315a.myportfolio.com/" target="_blank"><i class="fab fa-behance"></i></a></li>
            </ul>
        
        </div>
    </div>
    
    <div class="info-container">
    
    <div class="short-text">    <p class="paragraph">
        Welcome to my portfolio! I’m Andrew, an <a href="https://pulitzerarts.org/" class="bold-link" target="_blank">art handler</a> and <a href="https://mohistory.org/museum" class="bold-link" target="_blank">exhibits installation specialist</a> in Saint Louis. I also bartend in the <a href="https://www.seedsproutspoon.com/" class="bold-link" target="_blank">Weddings and Events industry</a>.
    
        Previously, I was a Training Manager at UPS, where I combined my education background with my passion for design. In 2023, I completed a <a href="https://www.launchcode.org/" class="bold-link" target="_blank">coding bootcamp</a>, enhancing my technical skills. 
    
        In my free time, I enjoy cooking and studying for my personal training certificate. Thank you for visiting my portfolio!
    </p>
    </div>
    
        <section id="experience">
    
        {#each experiences as exp}
        <ExperienceCard 
            startDate={exp.startDate}
            endDate={exp.endDate}
            positionTitle={exp.positionTitle}
            companyName={exp.companyName}
            description={exp.description}
            skills={exp.skills}
        />
    {/each}
        </section>
    
    
      <a href="/images/resume_AF.pdf" id="resume_link"  class="bold-link" target="_blank"> View my full resume here <i class="fa-solid fa-arrow-up-right-from-square" id="arrows"></i> </a>
    <br><br>
      <a href="https://afisch2014315a.myportfolio.com/" id="portfolio_link"  class="bold-link" target="_blank"> View my Design Portfolio here <i class="fa-solid fa-arrow-up-right-from-square" id="arrows"></i> </a>
    
    
        <section id="projects">
            {#each projects as project}
                <ProjectCard 
                    title={project.title}
                    description={project.description}
                    imageUrl={project.imageUrl}
                    skills={project.skills}
                    repoUrl={project.link}
                />
            {/each}
        </section>
        <a href="https://github.com/Andrewfischer100"  class="bold-link" target="_blank"> View my Github <i class="fa-solid fa-arrow-up-right-from-square"></i> </a>
    </div> 
    
    
    
    </section>