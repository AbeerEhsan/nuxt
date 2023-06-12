<script setup lang="ts">
import Button from "~/ui/components/Button/Button.vue";

const { t } = useI18n()
const appName = t('app_name')

useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - ${appName}` : appName
  },
  meta: [
    {
      hid: 'description',
      name: 'description',
      content: t('app_description'),
    },
  ],
})
const { $gsap } = useNuxtApp()
// const { $ScrollTrigger } = useNuxtApp()
const { $ScrollToPlugin } = useNuxtApp()
// const { $Observer } = useNuxtApp()
// const { $TextPlugin } = useNuxtApp()
// const { $ExpoScaleEase } = useNuxtApp()
// const { $SlowMo } = useNuxtApp()

onMounted(() => {
  // $gsap.to(window, { duration: 2, scrollTo: 50 })
  // $gsap.to('.title', { rotation: 1, x: 100, duration: 1 })
  // $gsap.effects.fade('.title')
  // $gsap.effects.slideIn('#title')
})
</script>

<template>
  <Html lang="en" />
  <NuxtLoadingIndicator id="smooth-wrapper" />
  <NuxtLayout>
    <NuxtPage id="smooth-content" class="title" />
  </NuxtLayout>
</template>

<style>
a {
  background-image: linear-gradient(
      to right,
      #54b3d6,
      #54b3d6 50%,
      #000 50%
  );
  background-size: 200% 100%;
  background-position: -100%;
  display: inline-block;
  padding: 5px 0;
  position: relative;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: all 0.3s ease-in-out;
}

a:before {
  content: '';
  background: #54b3d6;
  display: block;
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0;
  height: 3px;
  transition: all 0.3s ease-in-out;
}

a:hover {
  background-position: 0;
}

a:hover::before {
  width:100%;
}

button:before {
  content: '';
  background: #54b3d6;
  display: block;
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0;
  height: 3px;
  transition: all 0.3s ease-in-out;
}

button:hover {
  background-position: 0;
}

button:hover::before {
  width:100%;
}
</style>