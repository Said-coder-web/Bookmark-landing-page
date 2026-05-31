<template>
  <section class="extent py-[100px]">
    <TitleSection></TitleSection>
    <div class="container">
      <div
        class="cards flex justify-center gap-[20px] max-md:flex-col mt-[40px]"
      >
        <div
          class="card text-center pt-[30px] p-[20px] grid gap-[20px] shadow-xl rounded-[10px]"
          v-for="(card, i) in cards"
          :key="i"
        >
          <div class="image">
            <img class="m-auto" :src="card.image" :alt="`image-${i + 1}`" />
          </div>
          <div class="card-info">
            <h4 class="text-lg font-medium">{{ card.title }}</h4>
            <span class="text-sm opacity-50">{{ card.version }}</span>
          </div>
          <span class="dots"></span>
          <button class="py-[10px] px-[20px] text-white text-sm rounded-[5px]">
            Add & Install Extension
          </button>
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
    headSection: "Download the extension",
    parSection: `We’ve got more browsers in the pipeline. Please do let us know if you’ve 
                got a favourite you’d like us to prioritize.`,
  },
  data() {
    return {
      cards: [
        {
          image: require("@/assets/logo-chrome.svg"),
          title: "Add to Chrome",
          version: "Minimum version 62",
        },
        {
          image: require("@/assets/logo-firefox.svg"),
          title: "Add to Firefox",
          version: "Minimum version 55",
        },
        {
          image: require("@/assets/logo-opera.svg"),
          title: "Add to Opera",
          version: "Minimum version 46",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@use "@/sass/variables" as *;
.extent .card {
  &:nth-of-type(2) {
    @media (min-width: 768px) {
      transform: translateY(30px);
    }
  }
  &:nth-of-type(3) {
    @media (min-width: 768px) {
      transform: translateY(60px);
    }
  }

  .dots {
    background-image: radial-gradient(
      circle,
      rgba(0, 0, 0, 0.397) 1px,
      transparent 1px
    );
    background-size: 10px 10px; /* المسافة بين النقاط */
    height: 10px;
  }

  button {
    background: $blue-600;
    border: 2px solid $blue-600;
    transition: 0.3s;

    &:hover {
      color: $blue-600;
      background: transparent;
    }
  }
}
</style>
