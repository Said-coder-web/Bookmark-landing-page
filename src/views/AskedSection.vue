<template>
  <section class="ask py-[100px]">
    <TitleSection></TitleSection>
    <div class="container">
      <ul class="max-w-[600px] mx-auto my-[40px]">
        <li v-for="(qust, i) in askes" :key="i" class="py-[20px] grid">
          <div
            class="asked flex justify-between items-center cursor-pointer"
            @click="toggleActive(i)"
            :class="{ active: activeIndexes.includes(i) }"
          >
            <h5 class="text-xl">{{ qust.ask }}</h5>
            <img src="@/assets/icon-arrow.svg" alt="icon" />
          </div>
          <p class="answer opacity-50">
            <span>{{ qust.answer }}</span>
          </p>
        </li>
      </ul>
      <button
        class="py-[10px] px-[20px] block mx-auto rounded-[5px] text-[12px] text-white"
      >
        More info
      </button>
    </div>
  </section>
</template>

<script>
import TitleSection from "@/components/TitleSection";
export default {
  components: {
    TitleSection,
  },
  provide: {
    headSection: "Frequently Asked Questions",
    parSection: ` Here are some of our FAQs. If you have any other questions you’d like 
                  answered please feel free to email us.`,
  },
  data() {
    return {
      activeIndexes: [0],
      askes: [
        {
          ask: `What is Bookmark?`,
          answer: ` Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt 
                    justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.`,
        },
        {
          ask: `How can I request a new browser?`,
          answer: ` Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. 
                    Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, 
                    ultricies non ligula. Suspendisse imperdie tVivamus luctus eros aliquet convallis ultricies. 
                    Mauris augue massa, ultricies non ligula. Suspendisse imperdiet.`,
        },
        {
          ask: `Is there a mobile app?`,
          answer: ` Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum 
                    urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed 
                    sollicitudin ex et ultricies bibendum.`,
        },
        {
          ask: `What about other Chromium browsers?`,
          answer: ` Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam 
                    vitae neque eget nisl gravida pellentesque non ut velit.`,
        },
      ],
    };
  },
  methods: {
    toggleActive(i) {
      if (this.activeIndexes.includes(i)) {
        this.activeIndexes = this.activeIndexes.filter((index) => index !== i);
      } else {
        this.activeIndexes.push(i);
      }
    },
  },
};
</script>

<style lang="scss">
@use "@/sass/variables" as *;
.ask {
  ul {
    border-bottom: 1px solid #cacaca;

    li {
      border-top: 1px solid #cacaca;

      > div {
        h5 {
          transition: 0.3s;
        }
        &:hover {
          color: $red;
        }

        &.active {
          + p {
            grid-template-rows: 1fr;
            margin-top: 20px;
          }

          img {
            transform: rotate(0deg);
            filter: brightness(0) saturate(100%) invert(52%) sepia(43%)
              saturate(4016%) hue-rotate(326deg) brightness(98%) contrast(99%);
          }
        }

        img {
          transform: rotate(180deg);
          transition: 0.3s;
        }
      }

      p {
        display: grid;
        grid-template-rows: 0fr;
        transition: 0.3s ease;

        span {
          overflow: hidden;
        }
      }
    }
  }
  button {
    background: $blue-600;
  }
}
</style>
