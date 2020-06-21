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
            image: './img/pavel.jpg'
        },
        {
            name: 'divine',
            image: './img/pavel.jpg'
        },
        {
            name: 'kyivteploenergo',
            image: './img/pavel.jpg'
        },
        {
            name: 'bohemia',
            image: './img/pavel.jpg'
        },
        {
            name: 'CD’9',
            image: './img/pavel.jpg'
        },
		{
            name: 'TFL',
            image: './img/pavel.jpg'
        },
	];
</script>

<div class="projectsOuter" id="cases">
	<ul class="filterList">
		<li class="filterListItem">
            <a href="#dw">Latest</a>
		</li>
        <li class="filterListItem">
            <a href="#ww">Branding</a>
        </li>
        <li class="filterListItem">
            <a href="#dd">Applications</a>
        </li>
	</ul>
	<ul class="projects">
		{#each projects as project, i}
			<li class="project" transition:fade="{{delay: 1500 + (i * 100), duration: 1000 + i * 100, easing: cubicInOut}}" use:deferredTransition>
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
	.projectsOuter {
        width: 100%;
        padding: 10px 0 0 calc((100% / 12) * 4 );
        background: #110f11;
		min-height: 100vh;
		z-index: 10;
    }
    .projects {
        list-style-type: none;
        margin: 0;
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
