<script>
    import { Event_list } from "./events.js";
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
</svelte:head>

<div id="root">
    <h1 class="section-title">Upcoming Events</h1>
    <div class="grid">
        {#each Event_list.filter(event => !event.Past) as Event}
            <div class="project-card">
                <div class="image-cover">
                    <img class="main-image" src={Event.Image} alt="{Event.Name}" />
                </div>
                <div class="card-content">
                    <h2 class="event-name">{@html Event.Name}</h2>
                    <p class="event-date">{Event.Date}</p>
                    <p class="event-description">{@html Event.Description}</p>
                    <a href="/events/{Event.Slug}" class="details-button">
                        Open details
                    </a>
                </div>
            </div>
        {/each}
    </div>
    {#if Event_list.filter(event => event.Past).length > 0}
    <h1 class="section-title">Past Events</h1>
    <div class="grid">
        {#each Event_list.filter(event => event.Past) as Event}
            <div class="project-card">
                <div class="image-cover">
                    <img class="main-image" src={Event.Image} alt="{Event.Name}" />
                </div>
                <div class="card-content">
                    <h2 class="event-name">{Event.Name}</h2>
                    <p class="event-date">{Event.Date}</p>
                    <p class="event-description">{@html Event.Description}</p>
                     <a href="/events/{Event.Slug}" class="details-button">
                        Open details
                    </a>
                </div>
            </div>
        {/each}
    </div>
    {/if}
</div>

<style>
    /* Global styles for a modern look */
    :global(body) {
        font-family: 'Inter', sans-serif;
        background-color: #f0f2f5;
        color: #333;
    }

    #root {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        margin-bottom: 50px;
    }

    .section-title {
        font-size: 2.5rem;
        font-weight: 700;
        margin-top: 40px;
        margin-bottom: 30px;
        color: #1a202c;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 30px;
        width: 100%;
        max-width: 1200px;
    }

    /* A more attractive and modern card design */
    .project-card {
        background-color: #ffffff;
        border-radius: 15px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        overflow: hidden;
        display: flex;
        flex-direction: column;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .project-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 12px 16px rgba(0, 0, 0, 0.1);
    }

    .image-cover {
        width: 100%;
        height: 200px;
        overflow: hidden;
    }

    .main-image {
        width: 100%;
        height: 100%;
        object-fit: scale-down;
        transition: transform 0.3s ease;
    }
    
    .project-card:hover .main-image {
        transform: scale(1.05);
    }
    
    .card-content {
        padding: 20px;
        display: flex;
        flex-direction: column;
        flex-grow: 1; /* Allows the button to stick to the bottom */
    }

    .event-name {
        font-size: 1.25rem;
        font-weight: 700;
        margin-bottom: 5px;
        color: #2d3748;
    }

    .event-date {
        font-size: 0.9rem;
        color: #718096;
        margin-bottom: 15px;
    }

    .event-description {
        font-size: 1rem;
        color: #4a5568;
        flex-grow: 1; /* Pushes the button down */
        margin-bottom: 20px;
    }
    
    /* A more appealing and consistent button */
    .details-button {
        display: inline-block;
        text-align: center;
        background-color: #2563eb;
        color: #ffffff;
        font-weight: 500;
        border-radius: 9999px; /* for a pill shape */
        padding: 12px 24px;
        text-decoration: none;
        transition: background-color 0.3s ease, transform 0.2s ease;
        margin-top: auto; /* Pushes the button to the bottom of the card */
    }

    .details-button:hover {
        background-color: #1d4ed8;
        transform: scale(1.03);
    }

</style>