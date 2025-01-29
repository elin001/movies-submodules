<script>
    let { children, headline, dek, author1, author2 } = $props()
</script>


<!-- <div class="aspect-[1/1.2] xl:aspect-[6.5/3] xl:max-w-[1800px] lg:aspect-[5.5/3] md:aspect-[4.5/3] bg-no-repeat bg-cover bg-center relative mx-auto" style="background-image: url('https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg?dpr=2&auto=format&w=1800');">
    <div class="w-full px-4 lg:w-[835px] md:w-[705px] absolute bottom-[24px] md:bottom-[64px] left-1/2 -translate-x-1/2">
        <div class="mb-4 mx-auto w-min">
            <a href="/" target="_blank" class="uppercase !text-[white] bg-[black] p-2 font-utility-label-bold-caps-02 tracking-normal whitespace-nowrap !no-underline">Section label</a>
        </div>
        <h1 class="font-editorial-news-heading-01 text-center drop-shadow-[0px_2px_3px_rgba(102,102,102,1)] text-4xl xl:text-7xl lg:text-7xl md:text-6xl leading-heading-extra-tight uppercase text-[white]">Lorem ipsum dolor sit amet consectetur adipiscing elit</h1>
    </div>
</div> -->
<!-- end custom hero with absolute positioning -->
<!-- regular hero image -->
<!-- <div class="xl:max-w-[1800px] xl:aspect-[6/3] lg:aspect-[5/3] md:aspect-[4/3] xs:aspect-[3/3] bg-no-repeat bg-cover xs:bg-right mx-auto relative mb-2" style="background-size:cover;background-position:center;background-image: url('https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg?dpr=2&auto=format&w=1800&fit=crop');">
    <div class="rt-Box absolute bottom-[12px] right-[16px] opacity-60 font-utility-meta-reg-02">Photo by photographer, The Minnesota Star Tribune</div> -->
<!-- </div>
<div class="caption font-utility-meta-reg-02 text-tertiary xs:text-left md:text-center max-w-4xl mx-auto mb-8 px-4">Lorem ipsum dolor sit amet consectetur adipiscing elit, fusce sociis at montes vitae tempor enim, venenatis tristique feugiat arcu dis ridiculus. <span class="whitespace-nowrap !font-utility-meta-reg-02 !text-tertiary">(Photographer, The Minnesota Star Tribune)</span></div> -->
<!-- regular headline/summary bundle -->
<!-- <div class="mx-auto xl:max-w-7xl lg:max-w-6xl md:max-w-5xl sm:max-w-4xl px-4"> -->

    <!-- section label -->

    <div class="text-center block py-5">
        <p class="rt-Text break-words uppercase font-utility-label-bold-caps-02 text-text-color-01">
            <a data-testid="link-button" class="!no-underline" href="https://www.startribune.com/" target="_blank">Today Desk</a>
        </p>
    </div>

    <!-- end section label -->

    <!-- headline -->
    <h1 class="text-center rt-Heading font-editorial-news-heading-01 max-w-[800px] text-primary rt-r-size-6 rt-r-weight-bold px-3 mx-auto">{headline}</h1>
    <!-- summary -->
    <h2 class="xs:!text-1xl md:!text-2xl px-3 w-full xl:w-2/3 max-w-[800px] font-editorial-body-reg-01 font-regular leading-title  text-center mx-auto my-8 text-primary">{dek}</h2>
<!-- </div> -->

<!-- byline -->

<div class="byline rt-Box col-span-full flex items-center gap-x-2 flex-wrap max-w-2xl px-4 mx-auto font-utility-label-reg-02">
    <div class="rt-Box col-span-full flex items-center gap-x-2 flex-wrap">
        <div class="rt-Box w-full mb-3 flex items-center gap-x-2">
            <div class="rt-Box flex flex-col gap-y-0.5">
                <div class="rt-Box flex items-center">
                        <p class="rt-Text font-utility-label-bold-02 text-text-primary relative mr-2">By <a class="!no-underline" href="https://www.startribune.com/eder-campuzano/8801001" target="_blank">{author1}</a> and <a class="!no-underline" href="https://www.startribune.com/elliot-hughes/600375018" target="_blank">{author2}</a></p>
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