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
    <button on:click={handleClick} class="font-graphik-semibold text-11 md:text-16 z-20 rounded-full md:left-full border-2 w-[100px] h-[100px] md:w-[150px] md:h-[150px] shadow-lg py-2 md:px-5 text-black bg-gray-200" style="--hover-bg-color: {spotColor}">Read more</button>
    <ul id="nav">
        <li class="cursor-pointer"><div class="nav-item hidden text-11 leading-none md:text-12 md:leading-3 bottom-[110px] right-1 md:bottom-[160px] md:right-1 rounded-full w-[80px] h-[80px] md:w-[100px] md:h-[100px] max-w-64 border-2 py-4 md:py-6 shadow-md px-2 text-black bg-gray-200 font-graphik-semibold text-center" style="--hover-bg-color: #4FBDED"><a href="https://www.startribune.com/how-movies-of-the-1990s-captured-minnesota-on-the-big-screen/601220365-3?nav=true" target="_blank">How '90s movies captured Minnesota</a></div></li>
        <li class="cursor-pointer"><div class="nav-item hidden text-11 leading-none md:text-12 md:leading-3 bottom-[80px] right-[80px] md:bottom-[120px] md:right-32 rounded-full w-[80px] h-[80px] md:w-[100px] md:h-[100px] max-w-64 border-2 py-4 md:py-8 shadow-md px-2  text-black bg-gray-200 font-graphik-semibold text-center" style="--hover-bg-color: #F3DF26"><a href="https://startribune.com/the-10-most-minnesotan-90s-films/601220367?nav=true" target="_blank">The 10 most Minnesotan '90s films</a></div></li>
        <li class="cursor-pointer"><div class="nav-item hidden text-11 leading-none md:text-12 md:leading-3 bottom-0 right-[110px] md:bottom-0 md:right-40 rounded-full w-[80px] h-[80px] md:w-[100px] md:h-[100px] max-w-64 border-2 py-2 md:py-7 shadow-md px-2 text-black bg-gray-200 font-graphik-semibold text-center" style="--hover-bg-color: #BFAADF"><a href="https://startribune.com/minnesota-was-a-magnet-for-hollywood-in-the-1990s-a-new-state-office-wants-to-bring-productions-back/601220362?nav=true" target="_blank">Why so many '90s movies filmed in Minnesota</a></div></li>
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

        @media screen and (max-width: 768px) {
            transform: translateY(-0.5rem);
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

        @media screen and (max-width: 768px) {
            transform: translateY(-0.5rem);
        }
    }
</style>