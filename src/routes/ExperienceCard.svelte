<script>
    export let startDate;
    export let endDate;
    export let positionTitle;
    export let companyName;
    export let description;
    export let skills = [];
</script>

<style>
   .card {
    background: rgba(255, 255, 255, 0.0); /* Transparent white background */
    border-radius: 10px;
    padding: 20px;
    margin: 10px 0;
    position: relative;
    transition: box-shadow 0.3s ease, transform 0.3s ease, background 0.3s ease; /* Added background transition */
    backdrop-filter: blur(10px); /* Blur effect for the background */
}

.card:hover {
    background: rgba(255, 255, 255, 0.04); /* Slightly darker background on hover */
    transform: translateY(-2px); /* Slight lift effect */
}

.title, .company {
    font-size: small;
    color: #f6fbfd;
    margin: 0;
    line-height: 1.2;
    transition: color 0.2s ease-in-out, text-decoration 0.2s ease-in-out;
}

.card:hover .title,
.card:hover .company {
    color: rgb(0, 252, 134); /* Apply hover effect when hovering over the card */
}

.description {
    font-size: small;
}

.skills {
    display: flex;
    flex-wrap: wrap;
    margin-top: 10px;
}

.skill {
    background: rgba(7, 190, 145, 0.685); /* Skill bubble background */
    border-radius: 15px;
    padding: 5px 5px;
    margin-right: 5px;
    margin-bottom: 5px;
    color: white; /* Skill text color */
    font-size: 1rem;
}


    .header {
        display: flex;
        justify-content: space-between; /* Ensures space between dates and title */
        align-items: flex-start; /* Aligns the top of dates and title */
        margin-bottom: 10px;
    }

    .dates {
        font-size: small;
        color: rgba(150, 208, 238, 0.8);
        margin-top: 0; /* Ensures the dates align with the top of the title */
    }

    .title-company-wrapper {
    display: flex;
    flex-direction: column;
}



    .description {
        font-size: small;
    }

    .skills {
        display: flex;
        flex-wrap: wrap;
        margin-top: 10px;
    }

    .skill {
        background: rgba(7, 190, 145, 0.685); /* Skill bubble background */
        border-radius: 15px;
        padding: 5px 5px;
        margin-right: 5px;
        margin-bottom: 5px;
        color: white; /* Skill text color */
        font-size: 0.5rem;
    }
</style>

<div class="card">
    <div class="header">
        <div class="title-company-wrapper">
            <div class="title">{positionTitle}</div>
            <div class="company">{companyName}</div>
        </div>
        <div class="dates">{startDate} - {endDate}</div>
    </div>
    <p class="description">{description}</p>
    <div class="skills">
        {#each skills as skill}
            <div class="skill">{skill}</div>
        {/each}
    </div>
</div>
