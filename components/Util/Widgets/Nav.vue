<template>
  <nav id="NavUtilWidget" class="w-full h-full bg-black text-yellow-50">
    <div
      class="p-2.5 lg:p-5 h-fit group transform-gpu duration-200 text-lg md:text-xl lg:text-3xl text-primary-100/50 hover:text-primary-100"
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
    <div class="w-full grid lg:grid-cols-[20%,80%] z-auto">
      <div
        class="flex z-10 flex-col capitalize text-primary-100/50 text-3xl lg:text-5xl font-bold"
      >
        <nuxt-link
          v-for="(link, indexOfLink) in links"
          :key="indexOfLink"
          :to="link.link"
          class="py-5 relative text-center border-t border-b border-r-8 border-white hover:text-primary-100 transition-all duration-300 cursor-pointer"
          :class="[
            activeRouteIso === link.iso
              ? 'tracking-wide text-primary-100 '
              : '',
          ]"
          @mouseenter="() => (activeRouteIso = link.iso)"
          @click="action()"
        >
          {{ link.title }}
          <transition name="slide-nav">
            <div
              v-show="activeRouteIso === link.iso"
              class="w-3 bg-black rounded-tl-lg rounded-bl-lg absolute -right-2 z-50"
              :class="[
                indexOfLink === 0 ? 'top-0' : '-top-0.5',
                indexOfLink === links.length - 1 ? 'bottom-0' : '-bottom-0.5',
              ]"
            ></div
          ></transition>
        </nuxt-link>
      </div>
      <div
        class="w-full ml-[-1px] h-full border-t border-r border-b border-l border-white"
      >
        <section class="overflow-hidden p-5">
          <transition name="fade" mode="out-in">
            <component
              :is="content[activeRouteIso].component"
              v-if="content[activeRouteIso]"
              :key="activeRouteIso"
              :data="content[activeRouteIso].data"
            ></component
          ></transition>
        </section>
        <!-- should make dynamic component and add component for each page route -->
      </div>
    </div>
    <div class="text-3xl text-center w-full italic">
      location should be here
    </div>
  </nav>
</template>

<script>
// should make dynamic component and add component for each page route
import NavigationContactWidget from "@/components/Util/Widgets/Navgation/Contact.vue";
import NavigationStoryWidget from "./Navgation/Story.vue";
import NavigationProjectsWidget from "./Navgation/Projects.vue";
import NavigationAboutWidget from "./Navgation/About.vue";

export default {
  name: "NavUtilWidget",
  components: {
    NavigationContactWidget,
    NavigationStoryWidget,
    NavigationProjectsWidget,
    NavigationAboutWidget,
  },
  props: {
    action: {
      type: Function,
      default: () => ({}),
    },
  },

  data: () => ({
    activeRouteIso: "projects",
    links: [
      { title: "Projects", iso: "projects", link: "/projects" },
      { title: "About", iso: "about", link: "/about" },
      { title: "Contact", iso: "contact", link: "/contact" },
      { title: "Story", iso: "story", link: "/story" },
    ],
    content: {
      projects: { component: "NavigationProjectsWidget", data: [] },
      about: { component: "NavigationAboutWidget", data: [] },
      contact: { component: "NavigationContactWidget", data: [] },
      story: { component: "NavigationStoryWidget", data: [] },
    },
  }),
  mounted() {
    console.log({ pew: this.content[this.activeRouteIso] });
  },
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
