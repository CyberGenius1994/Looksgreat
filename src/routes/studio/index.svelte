<script>
    import { onMount } from 'svelte';
    import { fade, fly } from 'svelte/transition';
    import { cubicInOut } from 'svelte/easing';
    import { deferredTransition } from '../../components/deferredTransition.js';
    import Cursor, { useCursor } from "../../components/Cursor.svelte";
    import Header from "../../components/Header.svelte";
    let ready;
    let page = "Studio"
    export let segment;
    let small;

    function scrolling() {
        small = this.scrollTop > 50;
    }
    onMount(() => ready = true);

    const workers = [
        {
            name: 'pavel',
            image: "./img/pavel.jpg",
        },
        {
            name: 'dima',
            image: "./img/pavel.jpg",
        },
        {
            name: 'mykola',
            image: "./img/pavel.jpg",
        },
        {
            name: 'name',
            image: "./img/pavel.jpg",
        }
    ]
</script>

<svelte:head>
    <title>{page}</title>
</svelte:head>

<div class="wrapper studio" on:scroll={scrolling}>
    {#if ready}
        <Cursor/>
        <Header {segment} {page} {small}/>
        <main class="studioContent">
            <h1 class="pageName" in:fly="{{ delay: 0, duration: 1000, easing: cubicInOut}}" use:deferredTransition>About</h1>
            <div class="studioContentOuter">
                <h2 class="infoTitle" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Студия</h2>
                <div class="info">
                    <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massLorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
                    <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Aenean massorem ipsum dolor sit amet, consectetuer <br> adipiscing elit.</p>
                    <div class="practice" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                        Области нашей деятельности: <br> Брендинг, WEB, UI/UX
                    </div>
                    <ul class="workersList">
                        {#each workers as worker, i}
                            <li class="worker" in:fly="{{y: -10, delay: i * 200, duration: 2000, easing: cubicInOut}}" use:deferredTransition>
                                <a href="/" data-image={worker.image} data-cursor="View">{worker.name}</a>
                            </li>
                        {/each}
                    </ul>
                </div>
            </div>
            <div class="studioContentOuter">
                <h2 class="infoTitle" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Подход</h2>
                <div class="info second_block">
                    <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massLorem ipsum dolor sit amet, consectetuer  adipiscing elit.</p>
                    <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Aenean massorem ipsum dolor sit amet, consectetuer <br> adipiscing elit.</p>
                </div>
            </div>
            <div class="studioContentOuter">
                <h2 class="infoTitle" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Услуги</h2>
                <div class="info">
                    <div class="service">
                        <h3 class="serviceType" in:fly="{{delay: 0, duration: 1000, easing: cubicInOut}}" use:deferredTransition>Branding</h3>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massLorem ipsum dolor sit amet, consectetuer  adipiscing elit.</p>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Aenean massorem ipsum dolor sit amet, consectetuer <br> adipiscing elit.</p>
                        <div class="rightText" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                            <p>Brand strategy, Business strategy, <br> Identity</p>
                        </div>
                    </div>
                    <div class="service">
                        <h3 class="serviceType" in:fly="{{delay: 0, duration: 1000, easing: cubicInOut}}" use:deferredTransition>Web</h3>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massLorem ipsum dolor sit amet, consectetuer  adipiscing elit.</p>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Aenean massorem ipsum dolor sit amet, consectetuer <br> adipiscing elit.</p>
                        <div class="rightText" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                            <p>Brand strategy, Business strategy, <br> Identity</p>
                        </div>
                    </div>
                    <div class="service">
                        <h3 class="serviceType" in:fly="{{delay: 0, duration: 1000, easing: cubicInOut}}" use:deferredTransition>UI/UX</h3>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massLorem ipsum dolor sit amet, consectetuer  adipiscing elit.</p>
                        <p class="infoDescription" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Aenean massorem ipsum dolor sit amet, consectetuer <br> adipiscing elit.</p>
                        <div class="rightText" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                            <p>Brand strategy, Business strategy, <br> Identity</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="studioContentOuter">
                <h2 class="infoTitle" in:fly="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>Client Map</h2>
                <div class="mapOuter">
                    <figure class="imageOuter" in:fade="{{delay: 0, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                        <img class="imageMap" src="../img/map.svg" alt="">
                    </figure>
                </div>
            </div>
            <div class="socialOuter">
                <p class="socialTest">
                    <a target="_blank" href="https://www.behance.net/prannychuk">BEHANCE</a>
                    <span>&</span>
                    <a target="_blank" href="https://dribbble.com/pacorasson">DRIBBBLE</a>
                </p>
            </div>
        </main>
    {/if}
</div>

<style>
    .studio {
        --main-color: #fff;
        --accent-color: #F65E08;
        --second-color: #eaeaea;
        --navigation-color: #171718;
        --title-font-size: 100px;
    }
    .studio {
        background: var(--second-color);
        width: 100%;
        height: 100vh;
        overflow-y: auto;
        overflow-x: hidden;
    }
    .studioContent {
        display: block;
        padding-top: 10px;
    }
    .studioContentOuter {
        width: 100%;
        display: flex;
        flex-direction: column;
    }
    .pageName {
        text-transform: uppercase;
        color: #292929;
        font-size: var(--main-font-size);
        font-weight: 400;
        opacity: .5;
        margin-left: calc((100% / 12) * 4 );
        margin-bottom: 150px;
    }
    .info {
        display: flex;
        flex-direction: column;
        position: relative;
        top: -90px;
        margin-left: calc((100% / 12) * 4 );
        width: calc((100% / 12) * 4 );
        margin-bottom: 200px;
    }
    .infoTitle {
        margin-left: calc((100% / 12) * 2 );
        width: calc((100% / 12) * 2 );
        font-weight: 400;
        font-size: 20px;
        line-height: 28px;
        letter-spacing: -0.05em;
        color: #292929;
        position: sticky;
        top: 15px;
        left: 0;
        padding-top: 0;
        padding-bottom: 50px;
        text-transform: capitalize;
        z-index: 999;
    }
    .infoDescription {
        font-size: 15px;
        line-height: 22px;
        color: #292929;
        width: 100%;
        padding-top: 0;
        margin-top: 0;
    }
    .practice,
    .rightText {
        align-self: flex-start;
        text-align: right;
        width: calc((100% / 12) * 6);
        font-size: 15px;
        line-height: 22px;
        color: #292929;
        margin-left: calc((100% / 12) * 6);
        margin-top: 80px;
    }
    .workersList {
        width: 100%;
        list-style-type: none;
        margin: 50px 0 0 0;
        height: 100%;
        padding: 50px 0 0 0;
    }
    .workersList a {
        text-decoration: none;
        font-size: 100px;
        line-height: 1;
        color: #292929;
        font-family: sans-serif;
        -webkit-text-stroke-width: 0;
        -webkit-text-stroke-color: #292929;
        position: relative;
        z-index: 110;
        cursor: none;
        text-transform: uppercase;
        letter-spacing: -0.05em;
        transition: all .3s ease-in-out;
    }
    .workersList a:hover {
        -webkit-text-stroke-width: 1px;
        -webkit-text-fill-color: transparent;
        z-index: 112;
    }
    .mapOuter {
        margin-top: 216px;
        position: relative;
        top: -90px;
    }
    .imageOuter {
        display: flex;
        align-items: center;
        align-content: center;
        justify-content: center;
        margin: 0 0 150px 0;
        width: 100%;
    }
    .imageMap {
        max-width: 100%;
    }
    .socialOuter {
        padding-left: calc((100% / 12) * 4 );
    }
    .socialTest span {
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
        padding-bottom: 1px;
    }
    .socialTest a {
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
        padding-bottom: 1px;
    }
    .socialTest a::before {
        display: block;
        position: absolute;
        content: "";
        top: calc(100% - 1px);
        left: -200%;
        width: 300%;
        height: 1px;
        text-transform: uppercase;
        background: linear-gradient(90deg, var(--navigation-color) 0%, var(--navigation-color) 33%, transparent 33%, transparent 66%, var(--navigation-color) 66%, var(--navigation-color) 100%);
        transition: left 500ms ease-in-out;
    }
    .socialTest a:hover::before {
        left: 0;
    }
    .service {
        margin-bottom: 150px;
    }
    .serviceType {
        font-size: 100px;
        line-height: 1;
        color: #292929;
        font-family: sans-serif;
        position: relative;
        z-index: 110;
        cursor: none;
        text-transform: uppercase;
        letter-spacing: -0.05em;
        font-weight: 400;
        margin-top: 0;
        margin-bottom: 50px;
    }
</style>
