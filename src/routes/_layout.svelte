<script>
	let segment;
</script>
<style>
    :root {
        --main-color: #fff;
        --accent-color: #F65E08;
        --second-color: #EAEAEA;
        --countdown-font-size: 200px;
        --title-font-size: 100px;
        --main-font-size: 15px;
        --color-cursor: #F23939;
    }
    :global(::selection) {
        background: transparent;
    }
    :global(a, button, body) {
        cursor: none;
    }
    :global(body) {
        width: 100%;
        height: 100vh;
        overflow: hidden;
    }
    :global(.wrapper) {
        width: 100%;
        height: 100vh;
        overflow-y: auto;
        overflow-x: hidden;
    }
    @font-face {
        font-family: 'HelveticaNeueCyr';
        src: local('HelveticaNeueCyr-Roman'),
        url('/fonts/hinted-HelveticaNeueCyr-Roman.woff2') format('woff2'),
        url('/fonts/hinted-HelveticaNeueCyr-Roman.woff') format('woff');
        font-weight: normal;
        font-style: normal;
    }
	:global(main) {
		position: relative;
		max-width: 100%;
		background-color: transparent;
		padding: 0;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<div {segment}>
    <slot/>
</div>
