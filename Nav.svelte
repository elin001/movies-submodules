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



<nav class="sticky z-20 flex flex-row-reverse bottom-3 mr-2 items-center">
    <button on:click={handleClick} class="font-graphik-semibold text-11 md:text-16 z-20 rounded-full md:left-full border-2 w-[80px] h-[80px] md:w-[150px] md:h-[150px] shadow-md py-2 md:px-5 text-black bg-gray-200" style="--hover-bg-color: {spotColor}">Minnesota. Movies. '90s.</button>
    <ul id="nav">
        <li class="cursor-pointer"><div class="nav-item hidden text-11 md:text-16 bottom-[100px] right-1 md:bottom-[160px] md:right-1 rounded-full w-[60px] h-[60px] md:w-[80px] md:h-[80px] max-w-64 border-2 py-5 md:py-7 px-2 text-black bg-gray-200 font-graphik-semibold" style="--hover-bg-color: #4FBDED"><a href="https://startribune.com" target="_blank">Story 1</a></div></li>
        <li class="cursor-pointer"><div class="nav-item hidden text-11 md:text-16 bottom-[70px] right-[70px] md:bottom-[120px] md:right-32 rounded-full w-[60px] h-[60px] md:w-[80px] md:h-[80px] max-w-64 border-2 py-5 md:py-7 px-2  text-black bg-gray-200 font-graphik-semibold" style="--hover-bg-color: #F3DF26"><a href="https://startribune.com" target="_blank">Story 2</a></div></li>
        <li class="cursor-pointer"><div class="nav-item hidden text-11 md:text-16 bottom-0 right-[90px] md:bottom-0 md:right-40 rounded-full w-[60px] h-[60px] md:w-[80px] md:h-[80px] max-w-64 border-2 py-5 md:py-7 px-2 text-black bg-gray-200 font-graphik-semibold" style="--hover-bg-color: #BFAADF"><a href="https://startribune.com" target="_blank">Story 3</a></div></li>
    </ul>    
</nav>

<style>
    button {
        transform: rotate(0deg);
    }

    button:hover {
        transition: transform 0.5s ease-in-out, background-color 0.1s;
        transform: translateY(-1rem);
        background-color: var(--hover-bg-color);
        @media prefers-reduced-motion {
            transition: none;
        }

    }
    
    .nav-item {
        transform: rotate(0deg);
    }

    .nav-item:hover {
        transition: transform 0.5s ease-in-out, background-color 0.1s;
        transform: translateY(-1rem);
        background-color: var(--hover-bg-color);
        @media prefers-reduced-motion {
            transition: none;
        }
    }
</style>