<template>
  <nav
    id="NavUtilWidget"
    class="w-full h-full bg-black text-yellow-50 grid grid-cols-1"
  >
    <div
      class="absolute left-5 top-5 h-fit group transform-gpu duration-200 text-lg md:text-xl lg:text-3xl text-primary-100/50 hover:text-primary-100"
      @click="action()"
    >
      <span class="group-hover:pl-2 hover:underline transform-gpu duration-300"
        >C</span
      >
      <span class="group-hover:pl-2 hover:underline transform-gpu duration-300"
        >L</span
      >
      <span class="group-hover:pl-2 hover:underline transform-gpu duration-300"
        >O</span
      >
      <span class="group-hover:pl-2 hover:underline transform-gpu duration-300"
        >S</span
      >
      <span class="group-hover:pl-2 hover:underline transform-gpu duration-300"
        >E</span
      >
    </div>
    <div
      class="w-full list-none grid grid-cols-2 lg:grid-cols-4 h-fit capitalize text-primary-100/50 text-3xl lg:text-5xl font-bold"
    >
      <nuxt-link
        v-for="(link, indexOfLink) in links"
        :key="indexOfLink"
        :to="link.link"
        class="hover:text-primary-100 duration-300 cursor-pointer hover:tracking-wide border-b border-r w-full text-center pt-20 pb-5 lg:pb-10 border-white"
      >
        {{ link.title }}
      </nuxt-link>
    </div>

    <div class="text-3xl text-center w-full italic">
      Location should be here
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavUtilWidget",
  props: {
    action: {
      type: Function,
      default: () => ({}),
    },
  },
  data: () => ({
    links: [
      { title: "Projects", link: "/projects" },
      { title: "About", link: "/about" },
      { title: "Contact", link: "/contact" },
      { title: "Story", link: "/story" },
    ],
  }),
};
</script>

<style></style>
