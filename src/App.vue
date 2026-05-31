<template>
  <header-page></header-page>
  <router-view />
  <FooterPage></FooterPage>
</template>

<script>
import HeaderPage from "@/components/NavBar";
import FooterPage from "@/components/FooterPage";

export default {
  components: {
    HeaderPage,
    FooterPage,
  },
};
</script>

<style lang="scss">
#app {
  font-family: "Rubik", sans-serif;

  .container {
    margin-inline: auto;
    width: 100%;
    height: 100%;

    @media (max-width: 768px) {
      padding-inline: 10px;
    }
    @media (min-width: 768px) and (max-width: 992px) {
      padding-inline: 20px;
    }
    @media (min-width: 992px) and (max-width: 1200px) {
      padding-inline: 50px;
    }
    @media (min-width: 1200px) {
      width: 1200px;
    }
  }
}

nav {
  a {
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
