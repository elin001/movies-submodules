<script>
    //todo fix position for mobile menu alignment
    let navItems = $state([])

    function handleClick() {
        const navItems = document.querySelectorAll('.nav-item');
        navItems.forEach(item => {
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
    <button on:click={handleClick} class="font-graphik-semibold uppercase z-20 md:left-full rounded-md border-2 border-black max-w-40 max-h-20 shadow-md py-2 px-5 text-black bg-[#f3df26] hover:text-[#f3df26] hover:bg-black">Minnesota. Movies. '90s.</button>
    <ul id="nav">
        <li><div class="nav-item hidden my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-[#f3df26] hover:text-[#f3df26] hover:bg-black font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 1</a></div></li>
        <li><div class="nav-item hidden flex-col my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-[#f3df26] hover:text-[#f3df26] hover:bg-black font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 2</a></div></li>
        <li><div class="nav-item hidden flex-col my-3 rounded-md max-w-64 border-2 py-2 px-5 border-black text-black bg-[#f3df26] hover:text-[#f3df26] hover:bg-black font-graphik-semibold"><a href="https://startribune.com" target="_blank">Story 3</a></div></li>
    </ul>    
</div>