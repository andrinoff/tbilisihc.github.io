<script>
    import { page } from '$app/stores';
    import { Event_list } from '../events.js';
    import { derived } from 'svelte/store';
    import ArrowLeft from 'lucide-svelte/icons/arrow-left'; // Optional: for a nice icon

    // Get the slug from the URL params
    const event = derived(page, $page => {
        const slug = $page.params.slug;
        return Event_list.find(e => e.Slug === slug);
    });
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
</svelte:head>

<div class="page-container">
    {#if $event}
        <article class="event-details">
            <div class="back-link-container">
                 <a href="/events" class="back-link">
                    <ArrowLeft size={18} /> 
                    <span>Back to all events</span>
                </a>
            </div>

            <div class="event-banner">
                <img src={$event.Image} alt="{$event.Name} banner" />
            </div>
            
            <div class="content-wrapper">
                <h1 class="event-title">{@html $event.Name}</h1>
                <p class="event-date">{$event.Date}</p>
                <div class="event-description">
                    {@html $event.BigDescription}
                </div>
            </div>
        </article>
    {:else}
        <div class="not-found-container">
            <h1>Event Not Found</h1>
            <p>Sorry, we couldn't find the event you were looking for.</p>
            <a href="/events" class="back-link">Back to all events</a>
        </div>
    {/if}
</div>

<style>
    :global(body) {
        font-family: 'Inter', sans-serif;
        background-color: #f8f9fa; /* A slightly different light gray */
    }

    .page-container {
        width: 100%;
        max-width: 900px;
        margin: 0 auto;
        padding: 2rem 1rem;
    }

    /* Back link styling */
    .back-link-container {
        margin-bottom: 2rem;
    }

    .back-link {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        text-decoration: none;
        color: #495057;
        font-weight: 500;
        transition: color 0.2s ease;
    }

    .back-link:hover {
        color: #007bff;
    }
    
    /* Hero banner for the image */
    .event-banner {
        width: 100%;
        height: 400px;
        border-radius: 16px;
        overflow: hidden;
        margin-bottom: 2.5rem;
        background-color: #fff;
    }

    .event-banner img {
        width: 100%;
        height: 100%;
        object-fit: scale-down;
    }
    
    /* Wrapper for text content */
    .content-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
    
    .event-title {
        font-size: 3rem;
        font-weight: 900;
        color: #212529;
        line-height: 1.2;
        margin-bottom: 0.5rem;
    }
    
    .event-date {
        color: #6c757d;
        font-size: 1.1rem;
        margin-bottom: 2.5rem;
    }

    .event-description {
        font-size: 1.1rem;
        line-height: 1.8;
        color: #343a40;
        text-align: left;
        max-width: 750px; /* Optimal reading width */
    }
    
    /* Make embedded elements in the description responsive */
    .event-description :global(img) {
        max-width: 100%;
        height: auto;
        border-radius: 8px;
    }

    /* "Not Found" message styling */
    .not-found-container {
        text-align: center;
        padding: 4rem 1rem;
    }

    .not-found-container h1 {
        font-size: 2rem;
        margin-bottom: 1rem;
    }
</style>