<script>
    import { onMount } from 'svelte';
    import Cursor, { useCursor, useImage } from "../components/Cursor.svelte";
    import { fade } from "svelte/transition"

    import Projects from "../components/Projects.svelte";
    import Header from "../components/Header.svelte";
    import Slider from "../components/Slider.svelte";
    let ready;
    let small;
    let page = 'Looksgreat';

    function scrolling() {
        small = this.scrollTop > this.offsetHeight - 50
    }
    onMount(()=>ready=true);

</script>

<svelte:head>
    <title>{page}</title>
</svelte:head>

{#if ready}
    <div class="wrapper" on:scroll={scrolling}>
        <Cursor/>
        <Header {page} {small}/>
        <main class="page">
            <div class="sliderOuter">
                <Slider/>
            </div>
            <div class="ProjectsInner">
                <Projects/>
            </div>
        </main>
    </div>
{/if}

<style type="text/scss">
    .wrapper {
        background: #333333;
    }
    /*.page {*/
    /*    width: 100%;*/
    /*    overflow-y: auto;*/
    /*    overflow-x: hidden;*/
    /*}*/
    .sliderOuter {
        width: 100%;
        height: 100vh;
        background: #333333;
        text-transform: uppercase;
        display: flex;
        align-items: center;
        align-content: center;
        justify-content: center;
        color: #eaeaea;
    }
</style>
