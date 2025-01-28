<script>
    import { onMount } from 'svelte';

    let stars = $state([]);

    function getPosition() {
        let x = Math.random() * window.innerWidth;
        let y = Math.random() * document.documentElement.scrollHeight;
        return { x, y }
    }

    function createStars(count) {
        for (let i = 0; i < count; i++) {
            const position = getPosition();
            console.log(`Star ${i + 1}:`, position); 
            stars = [...stars, position];
        }
    }

    function randomDur(max) {
        const random = Math.floor(Math.random() * max)+ 6;
        return random;
    }

    onMount(() => {
        createStars(100);
    })

</script>

<div class="star-div absolute z-1">
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


<style>
    .star-div {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 600;
        left: 0;
    }

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

    @media (prefers-reduced-motion) {
        .star-div {
            display: none;
        }
    }
</style>