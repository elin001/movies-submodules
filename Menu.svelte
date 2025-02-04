<script>
    //todo fix position for mobile menu alignment
    let menuItems = $state([])

    function handleClick() {
        const menuItems = document.querySelectorAll('.menu-item');
        menuItems.forEach(item => {
        if (item.classList.contains('hidden')) {
            item.classList.remove('hidden');
            item.classList.add('flex');
        } else {
            item.classList.add('hidden');
            item.classList.remove('flex');
        }
    });
  }
</script>
<div class="sticky uppercase z-20 flex flex-row-reverse bottom-2 mr-2 items-center">
    <button on:click={handleClick} class="font-graphik-semibold uppercase z-20 md:left-full border-2 border-black max-w-40 max-h-20 shadow-md bg-gray-300 py-2 px-5 hover:bg-blue-800 hover:text-white">Minnesota. Movies. '90s.</button>
    <ul id="menu">
        <li><div class="menu-item hidden my-3 max-w-64 border-2 border-black bg-gray-300 py-2 px-5 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 1</a></div></li>
        <li><div class="menu-item hidden flex-col my-3 max-w-64 border-2 border-black bg-gray-300 py-2 px-5 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 2</a></div></li>
        <li><div class="menu-item hidden flex-col my-3 max-w-64 border-2 border-black bg-gray-300 py-2 px-5 hover:bg-blue-800 hover:text-white font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 3</a></div></li>
    </ul>    
</div>