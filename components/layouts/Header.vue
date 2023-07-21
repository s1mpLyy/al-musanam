<template>
  <div id="header-layout">
    <header
      class="w-full grid grid-cols-2 lg:grid-cols-3 border-b-[1.5px] border-black px-5"
    >
      <div id="burger" class="my-auto">
        <div class="grid grid-cols-1 min-w-[56px] max-w-[56px]">
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black"
          ></span>
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black my-1"
          ></span>
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black"
          ></span>
        </div>
      </div>
      <div>
        <img
          src="/images/E-3-name.png"
          height="85"
          class="select-none max-h-[100px] mx-auto"
          alt="Al-Musnam Logo 2000x2000"
        />
      </div>
      <nav
        class="hidden lg:inline-flex items-center justify-evenly list-none italic text-base md:text-lg lg:text-xl"
      >
        <li>About</li>
        <li>Projects</li>
        <li>Contact Us</li>
      </nav>
    </header>
  </div>
</template>

<script setup></script>

<style></style>
