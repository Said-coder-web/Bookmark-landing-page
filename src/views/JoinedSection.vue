<template>
  <section class="joined text-center py-[50px]">
    <div class="content grid gap-[20px] max-w-[400px] m-auto">
      <h4 class="text-[12px] font-light tracking-[5px] uppercase text-white">
        35,000+ already joined
      </h4>
      <h5 class="text-[2rem] text-white">
        Stay up-to-date with what we’re doing
      </h5>
      <form
        class="input flex gap-[20px] max-md:flex-col max-md:gap-[50px] max-md:px-[15px]"
        @submit.prevent="handleSubmit"
      >
        <div class="flex-1" :class="{ error: isError }">
          <!-- <span>Whoopes, make sure it's an email</span> -->
          <input
            type="email"
            name="email"
            id="email"
            v-model="email"
            class="py-[10px] px-[10px] porder-none outline-none rounded-md w-full h-full"
          />
        </div>
        <input
          type="submit"
          value="Contact Us"
          class="text-white py-[10px] px-[20px] text-sm rounded-md cursor-pointer"
        />
      </form>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      isError: false,
      matchEmail: /^\w+@\w+.(com|net|org)$/,
    };
  },
  methods: {
    handleSubmit() {
      if (!this.email || !this.matchEmail.test(this.email)) {
        this.isError = true;
      } else {
        this.isError = false;
      }
    },
  },
};
</script>

<style lang="scss">
@use "@/sass/variables" as *;

.joined {
  background: $blue-600;

  form {
    > div {
      position: relative;

      &::after {
        content: url(@/assets/icon-error.svg);
        position: absolute;
        right: 10px;
        top: 50%;
        width: 20px;
        height: 20px;
        transform: translateY(-50%);
        opacity: 0;
        transition: 0.3s;
      }

      &.error::after {
        opacity: 1;
      }

      &::before {
        content: "Whoops, make sure it's an email";
        position: absolute;
        left: -4px;
        top: -4px;
        width: calc(100% + 8px);
        height: 0;
        background: $red;
        color: white;
        font-size: 14px;
        font-style: italic;
        border-radius: 5px;
        align-content: end;
        text-align: start;
        overflow: hidden;
        transition: 0.3s;
      }

      &.error::before {
        padding: 0 0 5px 10px;
        height: 80px;
      }

      [type="email"] {
        position: relative;
      }
    }
  }

  form [type="submit"] {
    background: $red;
    border: 2px solid $red;
    transition: 0.3s;

    &:hover {
      background: white;
      color: $red;
    }
  }
}
</style>
