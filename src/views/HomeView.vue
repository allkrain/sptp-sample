<template>
  <div class="home">
    <div class="split-text">
      This <strong>text</strong> will be <em>split</em>
    </div>
    <div class="split-text">
      This <strong>text</strong> will be <em>split</em>
    </div>
    <div class="split-text">
      This <strong>text</strong> will be <em>split</em>
    </div>
    <div class="split-text">
      This <strong>text</strong> will be <em>split</em>
    </div>
    <div class="split-text">
      This <strong>text</strong> will be <em>split</em>
    </div>
    <router-link to="/about">Go to inner page</router-link>
  </div>
</template>

<script setup>
import SplitType from "split-type";
import gsap from "gsap";
import { RouterLink } from "vue-router";
import { onMounted } from "vue";

onMounted(() => {
  SplitType.create(".split-text", { types: "words, chars" });
  gsap.fromTo(
    ".split-text .char",
    {
      autoAlpha: 0,
    },
    {
      autoAlpha: 1,
      duration: 0.3,
      stagger: 0.1,
      ease: "power1.outIn",
    }
  );
});
</script>
<style lang="scss" scoped>
.home {
  .split-text {
    font-size: 60px;
    line-height: 1.1;
    overflow: hidde;

    em {
      background: linear-gradient(
        90.23deg,
        #ca7342 9.61%,
        #bc1f1f 32.53%,
        #7f65b7 70.72%
      );
      -moz-background-clip: text;
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
      text-fill-color: transparent;
    }
  }

  a {
    display: inline-block;
    font-size: 20px;
    margin-top: 30px;
  }
}
</style>
