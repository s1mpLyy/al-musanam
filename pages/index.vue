<template>
  <div>
    <main class="grid grid-cols-1 lg:grid-cols-[60%,40%]">
      <section class="grid grid-cols-1">
        <div class="w-full grid grid-cols-2 max-h-fit">
          <div class="border-b-[1.5px] border-r-[1.5px] border-black p-5">
            <img
              src="/images/test/swimming-pool.jpg"
              class="w-full h-auto max-h-[350px] object-center object-cover"
              alt=""
            />
          </div>
          <div
            class="border-b-[1.5px] border-r-[1.5px] border-black flex items-end justify-start"
          >
            <h3
              class="text-base lg:text-2xl text-black uppercase p-5 font-medium tracking-tight hover:tracking-wide transform duration-200 ease-linear"
            >
              Transformaing skylines and crafting icons
            </h3>
          </div>
        </div>
        <article class="p-5 border-r-[1.5px] border-b-[1.5px] border-black">
          <h4 class="text-2xl font-medium text-black italic">- About Us</h4>
          <h3 class="text-2xl lg:text-8xl font-bold leading-none">
            Our Misson is to construct a better future
          </h3>
          <div class="grid grid-cols-1 lg:grid-cols-2">
            <p class="text-black text-xl font-normal pt-4">
              We deliver exceptional construction projects with integrity,
              professionalism, and safety, building logo2kng-lasting
              relationships based on trust, transparency, and respect. Our
              collaborative team of skilled professionals enhances the built
              environment and improves lives through superior results.
            </p>
            <button
              id="button-learn-more"
              class="w-full inline-flex items-center transform duration-150 ease-linear"
            >
              <div
                class="inline-flex items-center relative w-24 hover:w-32 hover:justify-around justify-start transform duration-150 ease-linear"
              >
                <span
                  class="h-14 w-14 rounded-full border-[1.5px] border-black"
                ></span>
                <span class="w-8 h-0.5 bg-black -ml-2.5"></span>
                <span class="w-2 h-2 triangle"></span>
              </div>
              <div class="font-semibold ml-2 text-lg">Our locations</div>
            </button>
          </div>
        </article>
      </section>
      <section class="grid grid-cols-1 items-start">
        <div
          class="p-5 border-l-[1.5px] border-b-[1.5px] border-black -ml-[0.5px] h-fit max-h-fit"
        >
          <!-- The main slider component should be here -->
          <img
            src="/images/test/out-door.jpg"
            class="w-full h-full max-h-[500px] object-cover object-center"
            alt=""
          />
        </div>
        <div class="p-5 boredr-l-[1.5px] border-b-[1.5px] border-black h-fit">
          <div class="inline-flex items-center">
            <p class="underline uppercase text-lg font-semibold tracking-wider">
              Find our more about our brand story
            </p>
            <div class="inline-flex items-center relative w-10">
              <span class="w-8 h-0.5 bg-black -ml-1.5"></span>
              <span class="w-2 h-2 triangle"></span>
            </div>
          </div>
          <button
            class="mt-5 w-full py-5 text-xl bg-amber-600 italic font-semibold border border-black"
          >
            Contact Us
          </button>
        </div>
      </section>
    </main>
    <section class="grid grid-cols-1 py-5">
      <h2
        class="text-4xl lg:text-8xl text-black font-bold tracking-wider uppercase w-11/12 lg:w-1/2 px-5"
      >
        constructor philosophy.
      </h2>
      <div class="">
        <div class="relative flex overflow-x-hidden">
          <div class="py-12 animate-marquee whitespace-nowrap">
            <span class="text-4xl mx-4">Marquee Item 1</span>
            <span class="text-4xl mx-4">Marquee Item 2</span>
            <span class="text-4xl mx-4">Marquee Item 3</span>
            <span class="text-4xl mx-4">Marquee Item 4</span>
            <span class="text-4xl mx-4">Marquee Item 5</span>
          </div>

          <div class="absolute top-0 py-12 animate-marquee2 whitespace-nowrap">
            <span class="text-4xl mx-4">Marquee Item 1</span>
            <span class="text-4xl mx-4">Marquee Item 2</span>
            <span class="text-4xl mx-4">Marquee Item 3</span>
            <span class="text-4xl mx-4">Marquee Item 4</span>
            <span class="text-4xl mx-4">Marquee Item 5</span>
          </div>
        </div>
      </div>
    </section>
    <section class="grid grid-cols-1 p-5 relative">
      <div class="inline-flex z-10">
        <h5 class="font-thin text-lg lg:text-2xl">
          About
          <div class="w-20 lg:w-52 h-[1px] border-t border-black"></div>
        </h5>
        <p
          class="text-xl md:text-4xl lg:text-5xl xl:text-6xl text-black font-bold break-words uppercase tracking-tight"
        >
          deliver exceptional projects while maintaining high standards of
          integrity, professionalism, and safety.
          <span class="text-gray-500/90">
            They prioritize building long-lasting relationships with clients,
            partners, and employees based on trust, transparency, and mutual
            respect. They approach each project with meticulous attention to
            detail,
          </span>
          ensuring strict adherence to timelines and budgets.
        </p>
      </div>
    </section>
    <section class="grid grid-cols-1 p-5 w-full">
      <h5 class="font-thin text-lg lg:text-2xl">
        Our projects
        <div class="w-20 lg:w-52 h-[1px] border-t border-black"></div>
      </h5>
      <div class="w-full columns-1 md:columns-2 lg:columns-3 p-5">
        <article
          v-for="(_, indexOfProject) in [1, 2, 3, 4, 5, 6, 7, 8, 9]"
          :key="indexOfProject"
          :id="`projectCard-${indexOfProject}`"
          class="flex flex-col items-center max-w-md max-h-fit h-auto m-4"
        >
          <figure class="w-full">
            <img
              :src="
                indexOfProject % 2 === 0
                  ? '/images/test/out-door.jpg'
                  : '/images/test/swimming-pool.jpg'
              "
              class="aspect-auto object-cover object-center w-full h-full"
              :class="indexOfProject % 2 !== 0 ? 'max-h-60' : 'max-h-72'"
              alt=""
            />
          </figure>
          <h3
            class="w-full text-start text-xl font-medium py-1 md:py-2 lg:py-3"
          >
            Project one
          </h3>
          <p
            class="text-lg font-normal"
            :class="indexOfProject % 2 === 0 ? 'line-clamp-3' : 'line-clamp-2'"
          >
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Recusandae
            officia animi maiores molestias eligendi est. Ipsum doloremque, rem
            velit id hic nobis repudiandae, quae odit, maxime ab dolores quaerat
            natus.
          </p>
        </article>
      </div>
    </section>
  </div>
</template>

<script setup></script>

<style>
.triangle {
  width: 0;
  height: 0;
  border-style: solid;
  border-top: 5px solid transparent;
  border-bottom: 5px solid transparent;
  border-left: 8px solid black;
  border-right: 0;
}
</style>
