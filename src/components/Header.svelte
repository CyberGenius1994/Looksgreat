<script>
	import Icons from './Icons.svelte';
	export let segment;
    export let small;
    export let page;

</script>

<Icons/>
<header class="appHeader" class:smaller={small === true}>
	<div class="brand">
        <a href="/" class="logo">
            <svg viewBox="0 0 237 30">
	            <use href="#Logo"/>
            </svg>
        </a>
	</div>
    <nav>
        <ul>
            <li class="navigationItem halfItem">
                {#if page === "Looksgreat"}
                    <a data-cursor="GO" class="navigationItemLink" href="#cases">CASES</a>
                {:else}
                    <a data-cursor="GO" class='navigationItemLink { segment === "Cases" ? "active" : "" }' aria-current='Cases' href="/cases">CASES</a>
                {/if}
            </li>
            <li class="navigationItem">
                <a data-cursor="GO" class='navigationItemLink { segment === "Studio" ? "active" : "" }' aria-current='Studio' href='studio'>STUDIO</a>
            </li>
            <li class="navigationItem">
                <a data-cursor="GO" class='navigationItemLink { segment === "Contacts" ? "active" : "" }' aria-current='Contacts' href='contacts'>CONTACTS</a>
            </li>
        </ul>
    </nav>
</header>

<style>
    :root {
        --navigation-color: #EAEAEA;
    }
	.appHeader {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
		z-index: 999;
        display: flex;
        align-items: flex-start;
        align-content: center;
        justify-content: space-between;
        padding: 20px;
		/*mix-blend-mode: difference;*/
	}
	.brand {
        flex-basis: calc((100%/12)*2);
	}
    .appHeader.smaller .logo{
        width: 63%;
    }
	.logo {
        width: 100%;
        display: flex;
        color: var(--navigation-color);
        transition: all .5s ease-in-out;
	}
	.logo svg {
		max-width: 237px;
        width: 100%;
        height: auto;
        display: flex;
	}
    nav {
        flex-basis: calc((100% / 12) * 4 );
        font-weight: 300;
        padding: 0;
    }

    ul {
        margin: 0;
        padding: 0 0 0 20px;
        display: flex;
        width: 100%;
        align-items: flex-start;
        align-content: flex-start;
        justify-content: flex-start;
    }
    li.navigationItem {
        flex-basis: calc((100% - 20px)/4);
        display: inline-flex;
    }
    li.navigationItem.halfItem {
        flex-basis: calc((100% - 20px)/2);
    }
    .navigationItemLink {
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
    :global(.navigationItemLink::before) {
        display: block;
        position: absolute;
        content: "";
        top: calc(100% - 9px);
        left: 1px;
        width: 200%;
        height: 1px;
        text-transform: uppercase;
        background: linear-gradient(90deg, transparent 0%, transparent 50%, var(--navigation-color) 50%, var(--navigation-color) 100%);
        transition: left 500ms ease-in-out;
    }
    .navigationItemLink:hover:before,
    .navigationItemLink.active:before {
        left: -100%;
    }
</style>
