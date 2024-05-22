<template>
  <v-app>
    <v-main>
      <Nav />
      <router-view class="router-view" v-slot="{Component, route}">
        <Transition name="page-slide" mode="out-in">
          <component :key="route.name" :is="Component" />
        </Transition>
      </router-view>
    </v-main>
  </v-app>
</template>

<script setup>
import Nav from '@/components/Nav.vue'

</script>

<style>
@font-face {
    font-family: 'hel-neue';
    src: url('@/fonts/helvetica-neue/HelveticaNeue-Regular.otf');
}

@font-face {
  font-family: 'hel-neue-light';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-Light.otf');
}

@font-face {
  font-family: 'hel-neue-md';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-Medium.otf');
}

@font-face {
  font-family: 'hel-neue-bold';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-Bold.otf');
}

@font-face {
  font-family: 'hel-neue-italic';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-RegularItalic.otf');
}

@font-face {
  font-family: 'hel-neue-thin';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-Thin.otf');
}

@font-face {
  font-family: 'hel-neue-ul';
  src: url('@/fonts/helvetica-neue/HelveticaNeue-Ultralight.otf');
}

.hel-neue {
  font-family: 'hel-neue';
}

.hel-neue-light {
  font-family: 'hel-neue-light';
}

.hel-neue-md {
  font-family: 'hel-neue-md';
}

.hel-neue-bold {
  font-family: 'hel-neue-bold';
}

.hel-neue-italic {
  font-family: 'hel-neue-italic';
}

.hel-neue-thin {
  font-family: 'hel-neue-thin';
}

.hel-neue-ul {
  font-family: 'hel-neue-ul';
}

.page-slide-enter-active,
.page-slide-leave-active {
  transition: 1s ease all;
}

.page-slide-enter-from,
.page-slide-leave-to {
  opacity: 0;
  transform: translateY(100px);
}
</style>
