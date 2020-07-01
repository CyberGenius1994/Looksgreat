<script>
    import {onMount} from 'svelte';
    import {fade, fly} from 'svelte/transition';
    import {cubicInOut} from 'svelte/easing';
    import {deferredTransition} from '../components/deferredTransition.js';
    import Cursor, {useCursor, useImage} from "../components/Cursor.svelte";
    import Header from "../components/Header.svelte";

    let page = 'Contacts';
    let ready;
    export let segment;
    let small;

    function scrolling() {
        small = this.scrollTop > 50
    }

    onMount(() => ready = true);
    const offices = [{
        name: 'KYIV', worker: '', email: 'looksgreat@kiev.com', phone: '+38 (093) 05 30 831', address: '', image: './img/location.jpg'
    }, {
        name: 'NEW YORK',
        worker: 'Sabo Dmitry',
        email: 'looksgreat@new-yok.com',
        phone: '+1 917-651-1533',
        address: '19W 21 st St, New York, NY',
        image: './img/location.jpg'
    },]
</script>

<svelte:head>
    <title>{page}</title>
</svelte:head>

{#if ready}
    <div class="wrapper contacts" on:scroll={scrolling}>
        <Cursor/>
        <Header  {segment} {page} {small}/>
        <main class="contactsContent">
            <div class="contactsContentOuter">
                <h1 class="pageName" in:fly="{{ delay: 0, duration: 1000, easing: cubicInOut}}" use:deferredTransition>Location</h1>
            </div>
            <div class="ContactsRowOuter">
                <ul class="OfficesList">
                    {#each offices as office}
                        <li class="office">
                            <span data-cursor="Location" data-image={office.image} class="officeName" in:fly="{{delay: 100, duration: 1200, easing: cubicInOut}}" use:deferredTransition>{office.name}</span>
                            <p class="worker" in:fly="{{delay: 250, duration: 1200, easing: cubicInOut}}" use:deferredTransition>{office.worker}</p>
                            <a href="/" class="email" data-cursor="Write" in:fly="{{delay: 350, duration: 1200, easing: cubicInOut}}" use:deferredTransition>{office.email}</a>
                            <a href="/" data-cursor="Copy" in:fly="{{delay: 375, duration: 1200, easing: cubicInOut}}" use:deferredTransition>{office.phone}</a>
                            <p class="address" in:fly="{{delay: 400, duration: 1200, easing: cubicInOut}}" use:deferredTransition>{office.address}</p>
                        </li>
                    {/each}
                </ul>
                <p class="pageText" in:fly="{{delay: 500, duration: 1200, easing: cubicInOut}}" use:deferredTransition>
                    Осознанное обращение за услугами <br/> дизайна эффективно приводит к успеху <br/> Ваш бизнес
                </p>
            </div>
        </main>
    </div>
{/if}

<style>

    :root {
        --main-color: #fff;
        --accent-color: #F65E08;
        --navigation-color: #EAEAEA;
        --second-color: #EAEAEA;
        --countdown-font-size: 200px;
        --title-font-size: 100px;
        --main-font-size: 15px;
        --color-cursor: #F23939;
    }
    .contacts {
        background: #110f11;
        width: 100%;
        overflow-y: auto;
        overflow-x: hidden;
    }
    .pageName {
        text-transform: uppercase;
        color: #6B6B6B;
        font-size: var(--main-font-size);
        font-weight: 400;
        opacity: .5;
        margin-left: calc((100% / 12) * 4 );
        position: sticky;
        top: 0;
        left: 0;
    }
    .contactsContent {
        display: block;
        padding-top: 10px;
        min-height: 100vh;
    }
    .worker:empty,
    .address:empty {
        display: none;
    }

    .OfficesList {
        display: flex;
        flex-direction: column;
        list-style-type: none;
        padding: 0;
        margin: 0 0 0 calc((100% / 12) * 4 );
        flex-basis: calc((100% / 12) * 4 );
    }
    .office {
        display: inline-flex;
        flex-direction: column;
        align-items: flex-start;
        margin-bottom: 110px;
    }
    .office .officeName {
        display: inline-block;
        width: auto;
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
        margin-bottom: 50px;
    }
    .office:hover .officeName {
        -webkit-text-stroke-width: 1px;
        -webkit-text-fill-color: transparent;
        z-index: 112;
    }
    .office a,
    .office p {
        font-size: 15px;
        line-height: 22px;
        letter-spacing: -0.05em;
        text-transform: uppercase;
        color: #eaeaea;
    }
    .email {
        text-decoration-line: underline;
    }
    .ContactsRowOuter {
        display: flex;
        margin-top: 150px;
    }
    .pageText {
        margin: 0;
        padding: 0;
        font-size: 15px;
        line-height: 22px;
        letter-spacing: 0.05em;
        color: #eaeaea;
        font-weight: 400;
    }
    .contactsContentOuter {
        position: sticky;
        top: 20px;
        left: 0;
    }
</style>
