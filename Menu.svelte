<script>
    //todo fix position for mobile menu alignment
    let menuItems = $state([])

    function handleClick() {
        const menuItems = document.querySelectorAll('#menu .menu-item');
        menuItems.forEach(item => {
        if (item.classList.contains('hidden')) {
            item.classList.remove('hidden');
            item.classList.add('block');
        } else {
            item.classList.add('hidden');
            item.classList.remove('block');
        }
    });
  }
</script>
<div class="absolute top-0 left-0 z-20 md:bottom-2">
    <button on:click={handleClick} class="font-graphik-semibold z-20 md:left-full border-2 rounded-md border-black max-w-40 shadow-md bg-gray-300 py-2 px-5 border-r-4 border-b-3 hover:bg-blue-800 hover:text-white">Minneosta. Movies. '90s.</button>
        <ul id="menu">
            <li><div class="menu-item hidden z-20 w-[400px] rounded-md border-2 border-black shadow-md bg-gray-300 py-2 px-5 border-r-4 border-b-3 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 1</a></div></li>
            <li><div class="menu-item hidden z-20 w-[400px] rounded-md border-2 border-black shadow-md bg-gray-300 py-2 px-5 border-r-4 border-b-3 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 2</a></div></li>
            <li><div class="menu-item hidden z-20 w-[400px] rounded-md border-2 border-black shadow-md bg-gray-300 py-2 px-5 border-r-4 border-b-3 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 3</a></div></li>
        </ul>    
</div>