<script>
    import { onMount } from 'svelte';
    import Cursor, { useCursor, useImage } from "../components/Cursor.svelte";
    import { fade } from "svelte/transition"

    import Projects from "../components/Projects.svelte";
    import Header from "../components/Header.svelte";
    let ready;
    export let segment;
    let page = "Cases";
    let small;

    function scrolling() {
        small = this.offsetTop > 1
    }
    onMount(()=>ready=true);

</script>

<svelte:head>
    <title>{page}</title>
</svelte:head>

{#if ready}
    <div class="wrapper" on:scroll={scrolling}>
        <Cursor/>
        <Header  {segment} {page} {small}/>
        <main class="page">
            <Projects/>
        </main>

    </div>
{/if}

<style type="text/scss">
    .wrapper {
        background: #333333;
        height: 100vh;
    }
    .page {
        height: 100vh;
        width: 100%;
        overflow-y: auto;
        overflow-x: hidden;
    }
</style>
