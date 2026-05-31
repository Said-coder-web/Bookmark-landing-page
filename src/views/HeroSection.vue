<template>
  <section class="hero h-[calc(100vh-70px)]">
    <div
      class="container flex items-center justify-between max-md:flex-col max-md:justify-center max-md:gap-[100px] relative"
    >
      <div class="hero-info grid gap-[20px] max-md:text-center max-md:order-2">
        <h1 class="text-[3rem] font-medium leading-none max-md:text-[2rem]">
          A Simple Bookmark <br />
          Manager
        </h1>
        <p class="max-w-[450px] text-gray-400">
          A clean and simple interface to organize your favourite websites. Open
          a new browser tab and see your sites load instantly. Try it for free.
        </p>
        <div class="buttons flex gap-[10px] max-md:justify-center">
          <button class="px-[20px] py-[10px] rounded-[5px] text-sm shadow-md">
            Get it on Chrome
          </button>
          <button class="px-[20px] py-[10px] rounded-[5px] text-sm shadow-md">
            Get it on Firefox
          </button>
        </div>
      </div>

      <div class="hero-image max-md:order-1">
        <img
          class="drop-shadow-md"
          src="@/assets/illustration-hero.svg"
          alt="image-hero"
        />
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@use "@/sass/variables" as *;
.hero {
  position: relative;

  &::before {
    content: "";
    position: absolute;
    right: 0;
    top: 50%;
    width: 600px;
    height: 400px;
    background: $blue-600;
    border-radius: 200px 0 0 200px;

    @media (max-width: 768px) {
      width: 90%;
      height: 250px;
      top: 20%;
    }
  }

  .buttons {
    button {
      &:first-of-type {
        background: $blue-600;
        border: 2px solid $blue-600;
        color: $grey;
        transition: 0.3s;

        &:hover {
          background: white;
          color: $blue-600;
          transform: translateY(-5px);
        }
      }
      &:last-of-type {
        border: 2px solid $grey;
        background: $grey;
        transition: 0.3s;

        &:hover {
          background: white;
          border-color: $blue-950;
          color: $blue-950;
          transform: translateY(-5px);
        }
      }
    }
  }

  .hero-image {
    img {
      animation: up-dowen 2s infinite alternate linear;
    }
  }
}

@keyframes up-dowen {
  from {
    transform: translateY(-10px);
  }
  to {
    transform: translateY(10px);
  }
}
</style>
