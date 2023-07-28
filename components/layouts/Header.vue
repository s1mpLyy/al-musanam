<template>
  <div id="header-layout">
    <header
      class="w-full flex justify-between border-b border-black p-5 relative"
    >
      <div id="burger" class="my-auto" @click="toggleNavMenu">
        <div class="grid grid-cols-1 min-w-[56px] max-w-[56px]">
          <span
            class="w-8 lg:w-12 hover:w-14 hover:lg:w-16 transform-gpu duration-300 ease-in-out h-1 lg:h-2 rounded bg-black"
          ></span>
          <span
            class="w-8 lg:w-12 hover:w-14 hover:lg:w-16 transform-gpu duration-300 ease-in-out h-1 lg:h-2 rounded bg-black mt-1.5"
          ></span>
        </div>
      </div>

      <nuxt-link
        title="home-page-link"
        to="/"
        class="flex items-center absolute right-20 lg:right-1/2 translate-x-1/2 top-1 lg:top-0"
      >
        <img
          src="/images/E-3-name.svg"
          height="60"
          class="select-none z-0 max-h-[50px] lg:max-h-[65px] mx-auto"
          alt=""
        />
      </nuxt-link>

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
