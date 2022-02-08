<script setup lang="ts">
import { isDark, toggleDark } from '~/composables'
</script>

<template>
  <header>
    <nav class="space-y-2 flex flex-col">
      <router-link
        class="icon-btn"
        :class="[ $route.path == '/' ? 'text-teal-500' : '' ]"
        to="/"
        title="Home"
      >
        <span>Home</span>
        <carbon-campsite />
      </router-link>

      <button
        class="icon-btn !outline-none"
        title="Dark Mode"
        @click="toggleDark()"
      >
        <span>Lesemodus</span>
        <carbon-moon v-if="isDark" />
        <carbon-sun v-else />
      </button>

      <router-link
        class="icon-btn"
        :class="[ $route.path == '/about' ? 'text-teal-500' : '' ]"
        to="/about" title="About"
      >
        <span>About</span>
        <carbon-dicom-overlay />
      </router-link>

      <router-link
        class="icon-btn"
        :class="[ $route.path.startsWith('/wiki') ? 'text-teal-500' : '' ]"
        to="/wiki/start"
        title="About"
      >
        <span>Wiki</span>
        <carbon-document />
      </router-link>
    </nav>
  </header>
</template>
