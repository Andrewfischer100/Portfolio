<script>
    export let title = "";
    export let description = "";
    export let imageUrl = "";
    export let skills = [];
    export let repoUrl = ""; // New prop to hold the GitHub repo link
</script>

<style>
   .project-card {
    display: flex;
    flex-direction: column;
    padding: 16px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
}

.project-card:hover {
    background: rgba(255, 255, 255, 0.04); /* Slightly darker background on hover */
}

.header {
    display: flex;
    align-items: top;
    margin-bottom: 10px;
}

.image-preview {
    width: 65px; /* Adjust based on your design */
    height: 65px; /* Adjust based on your design */
    border-radius: 4px;
    object-fit: cover;
    margin-right: 16px; /* Space between image and text */
    max-width: 100%;
    height: auto; /* Maintain aspect ratio */
}

.title {
    font-size: x-small;
    color: #f6fbfd;
    margin: 0; /* Remove extra space around the title */
    line-height: 1.2; /* Adjust line height to align properly with the image */
    transition: color 0.2s ease-in-out, text-decoration 0.2s ease-in-out; /* Smooth transition for both color and underline */
}

.project-card:hover .title { 
    color: rgb(0, 252, 134); /* Change title color when hovering over the card */
}

.description {
    font-size: x-small;
    color: rgba(246, 237, 252, 0.425);
    margin: 10px 0 12px; /* Space above and below description */
    line-height: 135%;
}

.skills {
    display: flex;
    flex-wrap: wrap;
}

.skill-bubble {
    background: rgba(7, 190, 145, 0.685); 
    border-radius: 15px;
    padding: 5px 5px;
    margin-right: 5px;
    margin-bottom: 5px;
    color: white; 
    font-size: 0.5rem;
}

a {
    text-decoration: none;
    color: inherit;
    display: block; /* Ensure the link takes up the entire card */
}

</style>

<a href={repoUrl} target="_blank">
    <div class="project-card">    
        <div class="header">
            <img class="image-preview" src={imageUrl} alt={title} />
            <div>
                <h3 class="title">{title}</h3>
                <p class="description">{description}</p>
            </div>
        </div>
        <div class="skills">
            {#each skills as skill}
                <span class="skill-bubble">{skill}</span>
            {/each}
        </div>
    </div>
</a>

