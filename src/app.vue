<script setup>
  import {ref} from "vue"
  import SocialMedia from "@/components/social-media.vue"
  import HeadingSection from "@/components/heading-section.vue"
  import IntroSection from "@/components/intro-section.vue"
  import ExperienceSection from "@/components/experience-section.vue"
  import KnowledgeSection from "@/components/knowledge-section.vue"

  // Mouse movement watcher to name fill animate
  const traX = ref(null)
  const traY = ref(null)

  function mousemove(event) {
    traX.value = (4 * event.pageX) / 570 + 40
    traY.value = (4 * event.pageY) / 570 + 50
  }
</script>
<template>
  <div id="main" @mousemove="mousemove">
    <social-media class="print-hidden" />
    <heading-section :tra-x="traX" :tra-y="traY" />
    <intro-section class="print-hidden" />
    <experience-section />
    <knowledge-section />
  </div>
</template>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;700&display=swap");

  body {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-family: "Source Sans Pro", -apple-system, system-ui, sans-serif;
  }

  #main {
    margin-bottom: 50px;
  }

  @media print {
    #main {
      margin-bottom: 0;
    }

    .print-hidden {
      display: none !important;
    }
  }
</style>
