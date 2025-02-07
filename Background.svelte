<script>
    import { onMount } from 'svelte';
    let { children, headerH } = $props();

    let stars = $state([]);

    function getPosition() {
        let x, y;
        const screenWidth = window.innerWidth;

        let minThreshold, maxThreshold;
        if (screenWidth < 320) { // xs
        minThreshold = (screenWidth - 350) / 2;
        maxThreshold = (screenWidth + 350) / 2;
        } else if (screenWidth < 768) { // sm
        minThreshold = (screenWidth - 500) / 2;
        maxThreshold = (screenWidth + 500) / 2;
        } else if (screenWidth < 1024) { // md
        minThreshold = (screenWidth - 650) / 2;
        maxThreshold = (screenWidth + 650) / 2;
        } else if (screenWidth < 1440) { // lg
        minThreshold = (screenWidth - 810) / 2;
        maxThreshold = (screenWidth + 810) / 2;
        } else { // 2xl
        minThreshold = (screenWidth - 950) / 2;
        maxThreshold = (screenWidth + 950) / 2;
        }

        // Generate x position outside the threshold
        do {
        x = Math.random() * screenWidth;
        } while (x > minThreshold && x < maxThreshold);

        // Generate y position
        y = Math.min(Math.random() * document.documentElement.scrollHeight, document.documentElement.scrollHeight - 1600);

        return { x, y };
    }

    // function getPosition() {
    //     const x = Math.min(Math.random() * window.innerWidth, window.innerWidth - 20);
    //     const y = Math.min((Math.random() * (document.documentElement.scrollHeight - 1000)), document.documentElement.scrollHeight);
    //     return { x, y };
    // }

    function createStars(count) {
        for (let i = 0; i < count; i++) {
            const position = getPosition();
            stars = [...stars, position];
            // $inspect(stars, position)
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

<div class="star-div absolute z-1 w-[99%] max-h-screen top-[{headerH}px] motion-reduce:hidden overflow-x-clip">
    {#each stars as star}
    <img class="w-[15px] origin-center animate-[rotate_8s_ease-in-out_infinite]"
        style="position: absolute;
            top: {star.y}px;
            left: {star.x}px;
            animation-duration: {randomDur(3)}s"
        id="star"
        src="https://static.startribune.com/news/projects/all/2025-MOVIES.rankings/assets/star.svg"
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