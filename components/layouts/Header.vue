<template>
  <div id="header-layout">
    <header
      class="w-full grid grid-cols-2 lg:grid-cols-[30%,25%,45%] border-b-[1.5px] border-black px-5"
    >
      <div id="burger" class="my-auto" @click="toggleNavMenu">
        <div class="grid grid-cols-1 min-w-[56px] max-w-[56px]">
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black"
          ></span>
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black my-1.5"
          ></span>
          <span
            class="w-8 hover:w-14 transform-gpu duration-300 ease-in-out h-1 rounded bg-black"
          ></span>
        </div>
      </div>
      <div class="relative group">
        <nuxt-link
          title="home-page"
          to="/"
          class="w-full flex items-center justify-end overflow-hidden"
        >
          <img
            src="/images/E-3.svg"
            class="select-none max-h-[70px] lg:max-h-[100px] h-full z-20"
            alt="Al-Musnam Logo 2000x2000"
          />
          <span class="absolute top-2 lg:top-5">
            <span
              class="absolute w-full h-full -ml-2.5 shadow-sm bg-primary-100 z-10"
            ></span>
            <img
              src="/images/E-3-name.svg"
              height="60"
              class="select-none z-0 opacity-0 max-h-[65px] group-hover:translate-x-48 group-hover:opacity-100 duration-500"
              alt=""
            />
          </span>
        </nuxt-link>
      </div>
      <nav
        class="hidden lg:inline-flex items-center justify-end list-none uppercase font-medium underline underline-offset-8 decoration-1 text-base md:text-lg lg:text-xl"
      >
        <li class="px-2.5">
          <nuxt-link title="about-us-page" to="/about"> About </nuxt-link>
        </li>
        <li class="px-2.5">Projects</li>
        <li class="px-2.5">
          <nuxt-link title="contact-us-page" to="/contact">
            Contact Us
          </nuxt-link>
        </li>
      </nav>
    </header>
    <transition name="slide-top-bottom" :duration="1000">
      <NavLayout
        v-if="isOpenNav"
        class="fixed inset-0 h-screen w-screen z-50"
        :action="toggleNavMenu"
      />
    </transition>
  </div>
</template>

<script>
import NavLayout from "../Util/Widgets/Nav.vue";

export default {
  name: "",
  components: { NavLayout },
  data: () => ({
    isNavToggeld: false,
  }),
  mounted() {},
  methods: {
    toggleNavMenu() {
      this.isNavToggeld = !this.isNavToggeld;
    },
  },
  computed: {
    isOpenNav() {
      return this.isNavToggeld;
    },
  },
};
</script>

<style></style>
