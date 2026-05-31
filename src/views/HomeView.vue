<template>
  <main>
    <HeroSection></HeroSection>
    <FeatuersSection></FeatuersSection>
    <ExtentionSection></ExtentionSection>
    <AskedSection></AskedSection>
    <JoinedSection></JoinedSection>
  </main>
</template>

<script>
import HeroSection from "./HeroSection";
import FeatuersSection from "./FeatuersSection";
import ExtentionSection from "./ExtentionSection";
import AskedSection from "./AskedSection";
import JoinedSection from "./JoinedSection.vue";

export default {
  components: {
    HeroSection,
    FeatuersSection,
    ExtentionSection,
    AskedSection,
    JoinedSection,
  },
};
</script>
