<script>
    let { children, headline, dek, authors, hero, spotColor } = $props()
</script>



<div class="xl:max-w-[1550px] lg:max-w-[1000px] xl:aspect-[4/3] lg:aspect-[4/3] md:aspect-[4/3] xs:aspect-[4/3] bg-no-repeat bg-cover xs:bg-right mx-auto relative mb-2" style="background-size:cover;background-position:center;background-image: url('./img/{hero}');">
    <div class="rt-Box absolute bottom-[12px] left-[16px] font-utility-meta-reg-02 text-white">Photo illustration by Anna Boone, The Minnesota Star Tribune</div>
</div>

    <div class="text-center block py-5 mb-4 mx-auto w-min">
        <p class="rt-Text uppercase bg-[{spotColor}] text-black  p-2 font-utility-label-bold-caps-02 tracking-normal whitespace-nowrap !no-underline">
            <a data-testid="link-button" class="!no-underline" href="https://www.startribune.com/food-culture" target="_blank">Food & Culture</a>
        </p>
    </div>

    <!-- end section label -->

    <!-- headline -->
    <h1 class="text-center rt-Heading font-publico-text-bold leading-title tracking-tighter lg:text-66 text-56 xs:text-40 max-w-[1000px] text-primary rt-r-size-6 rt-r-weight-bold px-3 mx-auto">{headline}</h1>
    <!-- summary -->
    <h2 class="xs:!text-1xl md:!text-2xl px-3 w-full xl:w-2/3 max-w-[800px] font-editorial-body-reg-01 font-regular leading-title  text-center mx-auto my-8 text-primary">{dek}</h2>
<!-- </div> -->

<!-- byline -->

<div class="byline rt-Box col-span-full flex items-center gap-x-2 flex-wrap max-w-2xl px-4 mx-auto font-utility-label-reg-02">
    <div class="rt-Box col-span-full flex items-center gap-x-2 flex-wrap">
        <div class="rt-Box w-full mb-3 flex items-center gap-x-2">
            <div class="rt-Box flex flex-col gap-y-0.5">
                <div class="rt-Box flex items-center">
                    {#if authors.length > 2}
                        <p class="rt-Text font-utility-label-bold-02 text-text-primary relative mr-2">By <a class="!no-underline" href="https://www.startribune.com/elliot-hughes/600375018" target="_blank">{authors[0]}</a>
                        and <a class="!no-underline" href="https://www.startribune.com/yuqing-liu/9090528" target="_blank">{authors[1]}</a> and <a class="!no-underline" href="https://www.startribune.com/bryan-brussee/8455834" target="_blank">{authors[2]}</a></p>
                    {:else if authors.length > 1} 
                    <p class="rt-Text font-utility-label-bold-02 text-text-primary relative mr-2">By <a class="!no-underline" href="https://www.startribune.com/eder-campuzano/8801001" target="_blank">{authors[0]}</a>
                        and <a class="!no-underline" href="https://www.startribune.com/elliot-hughes/600375018" target="_blank">{authors[1]}</a></p>
                    {:else}
                    <p class="rt-Text font-utility-label-bold-02 text-text-primary relative">By <a class="!no-underline" href="https://www.startribune.com/eder-campuzano/8801001" target="_blank">{authors}</a></p>
                    {/if}  
                </div>
                <span class="rt-Text text-text-secondary font-utility-label-reg-02">The Minnesota Star Tribune</span>
            </div>
        </div>
        <div class="rt-Flex flex rt-r-display-flex rt-r-jc-start">
            <span class="rt-Text font-utility-label-reg-caps-03 text-text-secondary !text-[.6875rem] pb-3">February 15, 2025 at 7:01am</span>
        </div>
    </div>
</div>

{@render children() }