<script>
    import { fade } from 'svelte/transition';
    import { cubicInOut } from 'svelte/easing';
    import {  deferredTransition } from './deferredTransition.js';
    import { useCursor, useImage } from "../components/Cursor.svelte";

	let projects = [
		{
		    name: 'blade', 
			image: './img/pavel.jpg'
		},
        {
            name: 'artbat',
            image: './img/pavel.jpg',
	        type: 'branding'
        },
        {
            name: 'kameya',
            image: './img/pavel.jpg',
            type: 'web'
        },
        {
            name: 'apple point',
            image: './img/pavel.jpg',
            type: 'branding, web'
        },
        {
            name: 'kyivteploenergo',
            image: './img/pavel.jpg',
            type: 'web'
        },
        {
            name: 'shpyci hotel',
            image: './img/pavel.jpg',
            type: 'web'
        },
        {
            name: 'falcon',
            image: './img/pavel.jpg',
            type: 'branding, web'
        },
        {
            name: 'vision shop',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'alekom',
            image: './img/pavel.jpg',
            type: 'branding, web'
        },
        {
            name: 'alexander bold',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'divine dev.',
            image: './img/pavel.jpg',
            type: 'branding, web'
        },
        {
            name: 'glossy.',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'cupbite.',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'CD’9',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'modified res.',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'bau comfort',
            image: './img/pavel.jpg',
            type: 'branding, web'
        },
		{
            name: 'TFL',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'vetiv',
            image: './img/pavel.jpg',
            type: 'branding'
        },
        {
            name: 'intensys',
            image: './img/pavel.jpg',
            type: 'branding'
        },
	];

</script>

<div class="projectsOuter" id="cases">
	<ul class="filterList">
		<li class="filterListItem">
            <a href="#latest">Latest</a>
		</li>
        <li class="filterListItem">
            <a href="#branding">Branding</a>
        </li>
        <li class="filterListItem">
            <a href="#web">Web</a>
        </li>
        <li class="filterListItem">
            <a href="#applications">Applications</a>
        </li>
	</ul>
	<ul class="projects">
		{#each projects as project, i}
			<li class="project project.type" transition:fade="{{delay: 500, duration: 1000, easing: cubicInOut}}" use:deferredTransition>
                <a href="/" data-image={project.image} data-cursor="Show">
	                {project.name}
                </a>
			</li>
		{/each}
	</ul>
</div>

<style>
	:root {
		--position-x: 0;
		--position-y: 0;
	}
    :global(.hidden){
        visibility: hidden;
	    pointer-events: none;
    }
    .filterList {
        flex: 0 0 calc((100% / 12) * 2 );
        position: sticky;
        top: 22px;
        left: 0;
        margin: 100px 0 0 0;
        padding: 0;
        align-self: flex-start;
        list-style-type: none;
        z-index: 999;
    }
    .filterListItem a {
        display: inline-block;
        position: relative;
        top: 0;
        font-size: var(--main-font-size);
        font-family: 'HelveticaNeueCyr', sans-serif;
        font-weight: 400;
        text-decoration: none;
        overflow: hidden;
        text-transform: uppercase;
        color: var(--navigation-color);
        transition: color 300ms 300ms ease-in-out;
        padding-bottom: 10px;
    }
    :global(.filterListItem a::before) {
        display: block;
        position: absolute;
        content: "";
        top: calc(100% - 9px);
        left: 0;
        width: 200%;
        height: 1px;
        text-transform: uppercase;
        background: linear-gradient(90deg, transparent 0%, transparent 50%, #6b6b6b 50%, #6b6b6b 100%);
        transition: left 500ms ease-in-out;
    }
    .filterListItem a:hover {
        color: #6b6b6b;
    }
    .filterListItem a:hover:before,
    :global(.filterListItem a.active:before) {
        left: -100%;
    }
	.projectsOuter {
        flex: 1 1 100%;
        padding: 10px 0 0 calc((100% / 12) * 2 );
        background: #110f11;
        height: auto;
        display: flex;
    }
    .projects {
        flex: 1 1 auto;
        margin: 0;
        list-style-type: none;
        padding: 0;
        height: 100%;
    }
    .projects a {
        text-decoration: none;
        font-size: 100px;
        line-height: 1;
        color: #eaeaea;
        font-family: sans-serif;
        -webkit-text-stroke-width: 0;
        -webkit-text-stroke-color: #eaeaea;
        position: relative;
        z-index: 110;
        cursor: none;
        text-transform: uppercase;
	    letter-spacing: -0.05em;
	    transition: all .3s ease-in-out;
    }
    .projects a:hover {
        -webkit-text-stroke-width: 1px;
        -webkit-text-fill-color: transparent;
	    z-index: 112;
    }
</style>
