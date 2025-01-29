<script>
    //todo better y positioning for div
    import { onMount } from 'svelte';
    let { children, headerH, headerW } = $props();

    let stars = $state([]);

    function getPosition() {
    const x = Math.min(Math.random() * window.innerWidth, window.innerWidth - 20);
    const y = Math.min(Math.random() * document.documentElement.scrollHeight, document.documentElement.scrollHeight - 20); // Ensure y does not exceed scroll height
    return { x, y };
  }

    function createStars(count) {
        for (let i = 0; i < count; i++) {
            const position = getPosition();
            stars = [...stars, position];
        }
    }

    function randomDur(max) {
        const random = Math.floor(Math.random() * max)+ 6;
        return random;
    }

    onMount(() => {
        createStars(250);
    })

</script>

<div class="star-div absolute z-1 w-full h-full top-[{headerH}px] left-[{headerW}px] motion-reduce:hidden">
    {#each stars as star}
    <img class="w-[20px]"
        style="position: absolute;
            top: {star.y}px;
            left: {star.x}px;
            animation-duration: {randomDur(3)}s"
        id="star"
        src="./img/star.svg"
        alt="a star"
    />
    {/each}
</div>

{@render children() }

<style>
    #star {
        transform-origin: center;
        animation: rotate 8s linear infinite;
    }

    @keyframes rotate {
        0%{
            transform: rotate(0deg) scale(0);
        }
        50%{
            transform: rotate(180deg) scale(1);
        }
        100%{
            transform: rotate(360deg) scale(0)
        }
    }
</style>