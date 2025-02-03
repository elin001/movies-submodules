<script>
    import { onMount } from 'svelte';
    let { children, headerH } = $props();

    let stars = $state([]);

    function getPosition() {
        const x = Math.min(Math.random() * window.innerWidth, window.innerWidth - 20);
        const y = Math.min(Math.random() * document.documentElement.scrollHeight, document.documentElement.scrollHeight - 900); // Ensure y does not exceed scroll height
        return { x, y };
  }

    function createStars(count) {
        for (let i = 0; i < count; i++) {
            const position = getPosition();
            stars = [...stars, position];
            // console.log(stars, position)
        }
    }

    function randomDur(max) {
        const random = Math.floor(Math.random() * max)+ 5;
        return random;
    }

    onMount(() => {
        createStars(75);
        // console.log(randomDur(5))
    })

</script>

<div class="star-div absolute z-1 w-[99%] max-h-screen top-[{headerH}px] motion-reduce:hidden">
    {#each stars as star}
    <img class="w-[15px] origin-center animate-[rotate_8s_ease-in-out_infinite]"
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