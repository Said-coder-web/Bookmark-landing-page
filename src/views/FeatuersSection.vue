<template>
  <section class="feat py-[100px]">
    <title-section></title-section>
    <div class="container">
      <ul
        class="my-[40px] max-w-[600px] m-auto flex justify-between border-b max-md:flex-col max-md:text-center"
      >
        <li
          v-for="tab in tabs"
          :key="tab.id"
          class="p-[20px] cursor-pointer max-md:border-t"
          :class="{ active: activeTabe === tab.id }"
          @click="activeTabe = tab.id"
        >
          {{ tab.label }}
        </li>
      </ul>

      <div class="feat-tabs">
        <div
          v-if="activeTabe === 'bookMarking'"
          class="tab one flex justify-evenly items-center max-md:flex-col relative max-md:gap-[100px]"
        >
          <div class="image">
            <img
              class="h-[300px]"
              src="../assets/illustration-features-tab-1.svg"
              alt="image-tab1"
            />
          </div>

          <div class="tab-info grid gap-[20px] max-md:text-center">
            <h3 class="text-[2rem] font-medium">Bookmark in one click</h3>
            <p class="max-w-[400px] opacity-50">
              Organize your bookmarks however you like. Our simple drag-and-drop
              interface gives you complete control over how you manage your
              favourite sites.
            </p>
            <button
              class="w-[100px] p-[10px] text-[12px] text-white rounded-[5px] shadow-md hover:translate-y-[-2px] max-md:m-auto"
            >
              More Info
            </button>
          </div>
        </div>

        <div
          v-if="activeTabe === 'searching'"
          class="tab two flex justify-evenly items-center max-md:flex-col relative max-md:gap-[100px]"
        >
          <div class="image">
            <img
              class="h-[300px]"
              src="../assets/illustration-features-tab-2.svg"
              alt="image-tab2"
            />
          </div>

          <div class="tab-info grid gap-[20px] max-md:text-center">
            <h3 class="text-[2rem] font-medium">Intelligent search</h3>
            <p class="max-w-[400px] opacity-50">
              Our powerful search feature will help you find saved sites in no
              time at all. No need to trawl through all of your bookmarks.
            </p>
            <button
              class="w-[100px] p-[10px] text-[12px] text-white rounded-[5px] shadow-md hover:translate-y-[-2px] max-md:m-auto"
            >
              More Info
            </button>
          </div>
        </div>

        <div
          v-if="activeTabe === 'sharing'"
          class="tab three flex justify-evenly items-center max-md:flex-col relative max-md:gap-[100px]"
        >
          <div class="image">
            <img
              class="h-[300px]"
              src="../assets/illustration-features-tab-3.svg"
              alt="image-tab3"
            />
          </div>

          <div class="tab-info grid gap-[20px] max-md:text-center">
            <h3 class="text-[2rem] font-medium">Share your bookmarks</h3>
            <p class="max-w-[400px] opacity-50">
              Easily share your bookmarks and collections with others. Create a
              shareable link that you can send at the click of a button.
            </p>
            <button
              class="w-[100px] p-[10px] text-[12px] text-white rounded-[5px] shadow-md hover:translate-y-[-2px] max-md:m-auto"
            >
              More Info
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import TitleSection from "../components/TitleSection.vue";
export default {
  components: {
    TitleSection,
  },

  provide: {
    headSection: "Features",
    parSection: `Our aim is to make it quick and easy for you to access your favourite websites. 
                Your bookmarks sync between your devices so you can access them on the go.`,
  },

  data() {
    return {
      activeTabe: "bookMarking",

      tabs: [
        { id: "bookMarking", label: "Simple Bookmarking" },
        { id: "searching", label: "speedy Searching" },
        { id: "sharing", label: "Easy Sharing" },
      ],
    };
  },
};
</script>

<style lang="scss">
@use "../sass/variables" as *;
.feat {
  position: relative;

  &::before {
    content: "";
    position: absolute;
    left: 0;
    top: 50%;
    width: 600px;
    height: 400px;
    background: hsl(231, 69%, 60%);
    border-radius: 0 200px 200px 0;

    @media (max-width: 768px) {
      width: 90%;
      height: 250px;
    }
  }
  ul li {
    position: relative;
    transition: 0.3s;

    &::before {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 3px;
      background: $red;
      transition: 0.3s;

      @media (max-width: 768px) {
        left: 50%;
        transform: translateX(-50%);
      }
    }

    &:hover {
      color: $red;
    }

    &.active::before {
      width: 100%;

      @media (max-width: 768px) {
        width: 30%;
      }
    }
  }

  button {
    background: $blue-600;
    transition: 0.3s;

    &:hover {
      background: rgba($color: $blue-600, $alpha: 0.9);
    }
  }
}
</style>
