<script>
    import ExperienceCard from './ExperienceCard.svelte'; // Adjust the path as necessary
    import ProjectCard from './ProjectCard.svelte'; // Adjust the import path as needed
    import { fly } from 'svelte/transition';
    
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
        background-color: rgba(0, 0, 0, 0.07); /* light gray background */
        color: #006400;
                font-family: 'Roboto', sans-serif;
        width: 100%;
    }
    
    
    .main-container {
  display: flex;
  flex-direction: column; /* Stack elements vertically */
  align-items: left;
  width: 100%;
  padding: 100px;
  box-sizing: border-box;
}

/* Keep the container layout as it is */
.container {
  display: flex;
  flex-direction: row; /* Keeps text-container and links-container side by side */
  justify-content: space-between;
  width: 100%;
  max-width: 1200px; /* Controls max width of the container */
  margin-bottom: 20px; /* Adds space below the container */
}

.text-container {
  flex: 1; /* Takes up the left half */
  padding-right: 20px;
}

.links-container {
  margin-left: 200px;
  flex: 1; /* Takes up the right half */
  text-align: left; /* Aligns text to the left */
  display: flex;
  flex-direction: column; /* Aligns text vertically */
  justify-content: center; /* Vertically centers content within links-container */

}

/* Nav */
.nav {
  width: 100%;
  max-width: 1200px; /* Keeps the nav aligned with the container */
  text-align: left; /* Centers the nav items */
  margin-bottom: 20px; /* Adds space below the nav */
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
  color: #006400;
  text-decoration: none;
  font-size: 1em;
  transition: color 0.3s, transform 0.3s, padding-left 0.3s;
  padding-left: 10px;
}

.nav a.active {
  color: rgba(68, 0, 95, 0.445);
  font-weight: bold;
}

.nav a:hover {
  color: rgba(0, 170, 255, 1); /* Change to greenish blue on hover */
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

/* Social Links */
.social-links {
  display: flex;
  justify-content: center; /* Center the social links */
  margin: 20px 0; /* Space around social links, adjusted to center vertically */
  z-index: 3; /* Ensure this is above the glow effect */
}

.social-links ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex; /* Align items horizontally */
}

.social-links a {
  margin: 0 10px;
  color: #006400;
  text-decoration: none;
  padding: 10px;
  position: relative;
  transition: color 0.3s ease;
}

.social-links a:hover {
  color: rgba(0, 170, 255, 1);
}

.social-links i {
  font-size: 2rem;
}

.social-links a:hover::before {
  opacity: 1;
}

/* Info Container */
.info-container {
  max-height: 100vh;
  text-align: left;
  padding: 2rem;
  overflow-y: auto; /* Changes from scroll to auto for better handling */
  scrollbar-width: none;
  margin-bottom: 0; /* Ensures no extra margin at the bottom */
}
    
section {
  margin: 0; /* Reset margin between sections */
  padding: 0; /* Reset padding if needed */
}
    
    
    h1 {
        color: #006400;

      font-size: 3.25rem; /* Title size */
      margin: 0;
    }
    
    h2 {
      font-size: 2.5rem; /* Subtitle size */
      color: #006400;
      /* Subtitle color */
        margin-bottom: 10px; /* Space below subtitles */
      margin: 0.5rem 0; /* Space between title and subtitle */
    }
    
    .paragraph {
      font-family: 'Inter', sans-serif;
      font-size: 1.0rem; /* Smaller subtitle size */
      color: #006400;

       /* Light color with transparency */
      margin-top: 20px; /* No extra margin */
      font-family: 'Inter', sans-serif; /* Modern, clean typeface */
      line-height: 1.6; /* Increased leading for roomier text */
      letter-spacing: -0.02em; /* Slightly tightened tracking */
    }
    
     
    /* Styles for the resume link */
    #resume_link {
        display: inline-block;
        padding: 10px 15px;
        border: 2px solid #006400;
        border-radius: 5px;
        text-decoration: none;
        font-weight: bold;
        color: #006400;

        transition: all 0.3s ease;
    }
    
    #resume_link:hover {
        background-color: #006400;

        color: whitesmoke;
        border-color: rgba(255, 255, 255, 0.226);
    }
    
    /* Styles for the portfolio link */
    #portfolio_link {
        display: inline-block;
        padding: 10px 15px;
        border: 2px solid#006400;
        border-radius: 5px;
        text-decoration: none;
        font-weight: bold;
        color: #006400;

        transition: all 0.3s ease;
    }
    
    #portfolio_link:hover {
        background-color: #006400;

color: whitesmoke;
border-color: #006400;
    }
    
    /* Icon styling (optional) */
    #resume_link i, #portfolio_link i {
        margin-left: 5px; /* Adds space between the text and icon */
    }
    
    
    p {
      font-size: 1.2rem; /* Adjust font size for the paragraph */
      line-height: 1.5; /* Line height for readability */
    }
  
 /* Mobile-specific styles */
 @media (max-width: 768px) {
        .main-container {
            flex-direction: column;
        }

        .container {
            width: 100%;
        }

        .info-container {
            width: 100%;
            padding: 1rem;
            max-height: none; /* Remove max-height for mobile */
        }

        .nav a {
            font-size: 1.5em; /* Adjust font size for smaller screens */
        }

        /* Disable hover effects */
        .nav li:hover::before,
        .nav a:hover,
        .social-links a:hover {
            transform: none;
            color: rgba(238, 196, 255, 0.8); /* Use the default color */
        }

        .glow-effect {
            width: 60vw;
            height: 60vw;
            position: absolute;
            opacity: 1; /* Keep it as a static background */
        }
    }
</style>
    
    <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    </head>
    
    <!-- svelte-ignore a11y-no-redundant-roles -->
    <section class="main-container" role="region">    
    <div class="container">
        
      
        <div class="text-container">
            <h1>Andrew Fischer</h1> <!-- Replace with your name -->
            <h2>Full Stack Developer & Designer</h2> <!-- Replace with your subtitle -->
            <p class="paragraph">Creative designer capable of building company assets and business collateral as well as hand developing functional code for your website or application. </p> <!-- Replace with your transparent subtitle -->
            <div class="nav">
                <ul>
                  <li><a href="#about" on:click={() => handleNavClick('about')} class:active={activeSection === 'about'}>ABOUT</a></li>
                  <li><a href="#experience" on:click={() => handleNavClick('experience')} class:active={activeSection === 'experience'}>EXPERIENCE</a></li>
                  <li><a href="#projects" on:click={() => handleNavClick('projects')} class:active={activeSection === 'projects'}>PROJECTS</a></li>
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
    
       

            

            <!-- Resume and Portfolio Links -->
    <div class="links-container">
        <a href="/images/resumeAF.pdf" id="resume_link" class="bold-link" target="_blank">
          View my full resume here <i class="fa-solid fa-arrow-up-right-from-square" id="arrows"></i>
        </a>
        <br><br>
        <a href="https://afisch2014315a.myportfolio.com/" id="portfolio_link" class="bold-link" target="_blank">
          View my Design Portfolio here <i class="fa-solid fa-arrow-up-right-from-square" id="arrows"></i>
        </a>
      </div>
    </div>
  </section>



<div class="info-container">
  <section id="experience">
    {#each experiences as exp (exp.positionTitle)}
      <div transition:fly={{ y: -50, duration: 300 }}>
        <ExperienceCard 
          startDate={exp.startDate}
          endDate={exp.endDate}
          positionTitle={exp.positionTitle}
          companyName={exp.companyName}
          description={exp.description}
          skills={exp.skills}
        />
      </div>
    {/each}
  </section>
</div>
  
    <!-- Projects Section -->
    <section id="projects">
      {#each projects as project (project.title)} <!-- Keying by project title -->
        <div transition:fly={{ y: -50, duration: 300 }}> <!-- Wrap with a div for the fly transition -->
          <ProjectCard 
            title={project.title}
            description={project.description}
            imageUrl={project.imageUrl}
            skills={project.skills}
            repoUrl={project.link}
          />
        </div>
      {/each}
    </section> 