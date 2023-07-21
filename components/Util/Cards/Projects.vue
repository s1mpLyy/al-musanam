<template>
  <div
    id="ProjectsUtilCards"
    class="w-full columns-1 md:columns-2 lg:columns-3 gap-5 lg:px-10 px-5"
  >
    <article
      v-for="(_, indexOfProject) in [1, 2, 3, 4, 5, 6, 7, 8, 9]"
      :key="indexOfProject"
      :id="`projectCard-${indexOfProject}`"
      class="flex flex-col items-center max-w-md max-h-fit h-auto border-[1.5px] border-black bg-primary-gradient relative mb-5 overflow-hidden"
      @mouseenter="() => (isOnMouse[indexOfProject] = true)"
      @mouseleave="() => (isOnMouse[indexOfProject] = false)"
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
      <Transition name="slide">
        <div
          v-show="onMouse[indexOfProject]"
          class="bg-primary-gradient absolute bottom-0 p-4 border-t-[1.5px] border-black"
          style="box-shadow: 0px -58px 43px -6px rgba(0, 0, 0, 0.1)"
        >
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
        </div>
      </Transition>
    </article>
  </div>
</template>

<script>
export default {
  props: {
    projects: {
      type: Array,
      default: () => [
        {
          hamza: true,
        },
      ],
    },
  },
  data: () => ({ isOnMouse: {} }),
  methods: {
    onMouseHover(index) {
      this.isOnMouse[index] = !this.isOnMouse[index];
      console.log({ pew: this.isOnMouse });
    },
    beforeEnter: function (el) {
      el.style.opacity = 0;
      el.style.transformOrigin = "left";
    },
    enter: function (el, done) {
      Velocity(el, { opacity: 1, fontSize: "1.4em" }, { duration: 300 });
      Velocity(el, { fontSize: "1em" }, { complete: done });
    },
    leave: function (el, done) {
      Velocity(el, { translateX: "15px", rotateZ: "50deg" }, { duration: 600 });
      Velocity(el, { rotateZ: "100deg" }, { loop: 2 });
      Velocity(
        el,
        {
          rotateZ: "45deg",
          translateY: "30px",
          translateX: "30px",
          opacity: 0,
        },
        { complete: done }
      );
    },
  },
  computed: {
    onMouse() {
      return this.isOnMouse;
    },
  },
};
</script>

<style></style>
