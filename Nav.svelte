<script>
    //todo fix position for mobile menu alignment
    let { spotColor } = $props()
    console.log(spotColor)

    let navItems = $state([])

    function handleClick() {
        const navItems = document.querySelectorAll('.nav-item');
        navItems.forEach(item => {
        if (item.classList.contains('hidden')) {
            item.classList.remove('hidden');
            item.classList.add('absolute');
        } else {
            item.classList.add('hidden');
            item.classList.remove('absolute');
        }
    });
  }
</script>



<nav class="sticky z-20 flex flex-row-reverse bottom-2 mr-2 items-center">
    <button on:click={handleClick} class="font-graphik-semibold z-20 md:left-full rounded-md border-2 border-black max-w-40 max-h-20 shadow-md py-2 px-5 text-black bg-gray-300" style="--hover-bg-color: {spotColor}">Minnesota. Movies. '90s.</button>
    <ul id="nav">
        <li><div class="nav-item hidden bottom-10 right-0 my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-gray-300 font-graphik-semibold" style="--hover-bg-color: {spotColor}"><a href="https://startribune.com" target="_blank">Story 1</a></div></li>
        <li><div class="nav-item hidden top-3 left-0 my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-gray-300 font-graphik-semibold" style="--hover-bg-color: {spotColor}"><a href="https://startribune.com" target="_blank">Story 2</a></div></li>
        <li><div class="nav-item hidden top-5 left-0 my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-gray-300 font-graphik-semibold" style="--hover-bg-color: {spotColor}"><a href="https://startribune.com" target="_blank">Story 3</a></div></li>
    </ul>    
</nav>

<style>
    button:hover {
        transform: rotate(7deg);
        transition: 0.5s ease;
        @media prefers-reduced-motion {
            transition: none;
        }
    }

    /* @keyframes rotate {
        0%{
            transform: rotate(0deg) scale(0);
        }
        100%{
            transform: rotate(20deg) scale(0.5);
        }
    } */

    
    .nav-item {
        transition: background-color 0.1s ease;
        @media prefers-reduced-motion {
            transition: none;
        }
    }

    .nav-item:hover {
        background-color: var(--hover-bg-color);
    }
</style>