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
  height: 100vh;
  overflow-x: hidden;
  overflow-y: auto; /* Allow vertical scrolling */
  width: 100%;
}


.main-container {
  display: flex;
  flex-direction: row; /* Change to column on smaller screens */
  height: auto; /* Allow the container to adjust based on content */
  max-width: 1200px; /* Keep the max width */
  margin: 0 auto; /* Center the container */
  overflow-x: hidden; /* Prevent horizontal overflow
  overflow-y: auto; /* Allow scrolling if content exceeds height */
}

.container {
  width: 50%; /* Full width */
  padding: 20px; /* Padding for spacing */
  display: flex;
  flex-direction: column; /* Stack items vertically */
  justify-content: flex-start; /* Align items to the start */
  align-items: flex-start; /* Align items to the top */
}



.nav {
    display: flex;
    flex-direction: column; /* Stack links vertically */
    z-index: 3; /* Ensure this is above the glow effect */
    margin-top: -30px;
    padding-left: 30px;
}

.nav ul {
    list-style-type: none; /* Remove bullet points */
    padding: 0; /* Remove padding */
    margin: 0; /* Remove margin */
}

.nav li {
    margin: 10px 0; /* Space between nav items */
    position: relative; /* Position relative to allow absolute positioning of pseudo-element */
}

.nav a {
    color: rgba(238, 196, 255, 0.8); /* Color for nav links */
    text-decoration: none; /* Remove underline */
    font-size: 1em; /* Adjust font size */
    transition: color 0.3s, transform 0.3s, padding-left 0.3s; /* Smooth color, transform, and padding change */
    padding-left: 10px; /* Initial padding for spacing */
}

.nav a.active {
    color: rgb(255, 255, 255); /* Active color, same as hover */
    font-weight: bold; /* Optional: make it bold */
}

.nav a:hover {
    color: rgb(255, 255, 255); /* Change color on hover */
}

/* Pseudo-element for the line */
.nav li::before {
    content: ''; /* Required for the pseudo-element to work */
    position: absolute; /* Position it relative to the li */
    left: 0; /* Align it to the left */
    top: 50%; /* Center it vertically */
    width: 0px; /* Thickness of the line */
    height: 1%; /* Make it the full height of the li */
    background-color: rgba(238, 196, 255, 0.8); /* Color of the line */
    transform: translateY(-50%); /* Center the line vertically */
    transition: width 0.3s; /* Smooth transition for the line */
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
  height: 100vh;
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
  font-size: 1.0 rem; /* Smaller subtitle size */
  color: rgba(240, 229, 252, 0.6); /* Light color with transparency */
  margin-top: 20px; /* No extra margin */
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


.social-links i {
    padding: 20px;
    scale: 325%;
}

/* Glow effect */
.glow-effect {
  position: absolute;
  top: 0;
  left: 0;
  width: 2000px; /* Large size to go beyond the viewport */
  height: 2000px;
  background: radial-gradient(
    circle,
    rgba(0, 170, 255, 0.15) 0%,
    rgba(0, 170, 255, 0.05) 30%,
    rgba(0, 170, 255, 0.03) 60%,
    rgba(0, 170, 255, 0.01) 100%,
    transparent 100%
  );
  border-radius: 50%; /* Keep the glow circular */
  pointer-events: none;
  transition: opacity 0.2s ease-out;
  opacity: 1;
  z-index: 1; /* Ensure this is below the text and info containers */
}

/* Center the glow around the pointer */
.glow-effect {
  transform: translate(calc(var(--mouseX) - 750px), calc(var(--mouseY) - 750px));
}

p {
  font-size: 1.2rem; /* Adjust font size for the paragraph */
  line-height: 1.5; /* Line height for readability */
}

/* Social Links */
.social-links {
    display: flex; /* Flexbox for horizontal alignment */
    justify-content: center; /* Center the social links */
    margin: 20px 20px; /* Space above social links */
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
    color: rgba(240, 229, 252, 0.6);
    text-decoration: none; /* Remove underline */
}

.social-links a:hover {
    color: rgba(0, 170, 255, 1); /* Change color on hover */
}

@media (max-width: 768px) {
  .main-container {
    flex-direction: column; /* Stack the containers vertically */
    width: 100%; /* Take up the full width of the screen */
    margin: 20px 0; /* Add margin on the top and bottom */
    overflow-x: hidden; /* Prevent horizontal overflow
  }

  .container {
    width: 100%; /* Each container takes full width */
    padding: 20px; /* Keep padding for spacing inside the containers */
    margin: 10px auto; /* Auto margin horizontally will center the element */
  }

  .nav ul {
    padding-left: 0; /* Reset padding for nav in mobile view */
  }

  .nav li {
    margin: 5px 0; /* Adjust spacing between nav items */

  }

  .text-container, .info-container {
    width: 100%; /* Full width for both text and info containers */
    text-align: left; /* Ensure text is left-aligned */
    padding: 20px; /* Add padding for better readability on small screens */
    margin: 10px 0; /* Add margin for spacing between stacked containers */
    overflow-y: auto; /* Allow scrolling if content exceeds height */
    height: auto; /* Let the container expand naturally with the content */
  }

  .short-text {
    display: none; /* Hide short text by default */
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
    <div class="long-text">
    <p class="paragraph">
        Hello and welcome to my portfolio! I’m Andrew, and I presently work as an <a href="https://pulitzerarts.org/" class="bold-link" target="_blank" >art handler</a> and <a href="https://mohistory.org/museumhttps://mohistory.org/museum" class="bold-link" target="_blank">exhibits installation specialist</a> for local museums in the Saint Louis Area. On the side, I work as a bartender in the <a href="https://www.seedsproutspoon.com/" class="bold-link" target="_blank" >Weddings and Events industry!</a> My career has taken a diverse path, blending my passion for design with my background in education and technology.

        Before stepping into my current roles, I spent several years at UPS as a Training Manager. This experience allowed me to leverage my education degree to develop talent and improve building production. With the help of UPS's tuition assistance program, I explored my true interest in design, which has become a key part of my professional journey.
        
        In 2023, I completed a <a href="https://www.launchcode.org/" class="bold-link" target="_blank" >six-month coding bootcamp</a>, further expanding my skill set to include technology and programming. This blend of design and technical expertise allows me to approach projects with a unique perspective.
        
        When I’m not immersed in designing or programming, you’ll find me cooking, studying for my personal training certificate, or enjoying quality time with my partner. I believe in maintaining a balance between my professional and personal interests, which adds depth to my work and life.
        
        Thank you for taking the time to visit my portfolio. I look forward to connecting and exploring potential collaborations!
               
    </p>
</div>
<div class="short-text">"
    Welcome to my portfolio! I’m Andrew, an <a href="https://pulitzerarts.org/" class="bold-link" target="_blank">art handler</a> and <a href="https://mohistory.org/museum" class="bold-link" target="_blank">exhibits installation specialist</a> in Saint Louis. I also bartend in the <a href="https://www.seedsproutspoon.com/" class="bold-link" target="_blank">Weddings and Events industry</a>.

    Previously, I was a Training Manager at UPS, where I combined my education background with my passion for design. In 2023, I completed a <a href="https://www.launchcode.org/" class="bold-link" target="_blank">coding bootcamp</a>, enhancing my technical skills. 

    In my free time, I enjoy cooking and studying for my personal training certificate. Thank you for visiting my portfolio!
    
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

