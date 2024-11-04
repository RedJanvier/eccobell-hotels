<template>
  <div>
    <header class="pb-16">
      <div class="container-custom">
        <nav class="flex justify-between pt-6 items-center">
          <nuxt-link to="/">
            <span class="iconEccobell-logo"></span>
            <span class="room-number">Room 301</span>
          </nuxt-link>
          <button class="flex items-center">
            <span>EN</span>
            <span class="iconEccobell-globe"></span>
          </button>
        </nav>
      </div>
    </header>
    <main class="list-wrapper">
      <div class="p-6">
        <div class="nav flex justify-between items-center mb-4">
          <nuxt-link to="/"><span class="iconEccobell-carret-left"></span></nuxt-link>
          <nuxt-link to="/"><span class="iconEccobell-close"></span></nuxt-link>
        </div>
        <h1>Hotel Information</h1>
        <p class="page-description">Discover everything you need to know about the hotel to make the most of your stay</p>
      </div>
      <div class="list-container p-4">
        <ul class="list">
          <li v-for="link in links" :key="link.name">
            <nuxt-link :to="link.href" class="flex items-center w-full gap-4">
              <div class="icon-wrapper">
                <span :class="link.icon"></span>
              </div>
              <span class="flex-1">{{ link.name }}</span>
              <span class="iconEccobell-carret"></span>
            </nuxt-link>
          </li>
        </ul>
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue';

  const links = ref([
    {
      name: "Room Information",
      icon: "iconEccobell-bed",
      href: "/",
    },
    {
      name: "Amenities",
      icon: "iconEccobell-swimming",
      href: "/",
    },
    {
      name: "Food and drinks",
      icon: "iconEccobell-forks",
      href: "/",
    },
    {
      name: "Hotel map",
      icon: "iconEccobell-map",
      href: "/",
    },
    {
      name: "Check in/out",
      icon: "iconEccobell-key",
      href: "/",
    },
    {
      name: "Leave a review",
      icon: "iconEccobell-list",
      href: "/",
    },
  ]);
</script>


<style>
.icon-wrapper > [class^="iconEccobell-"],
.icon-wrapper > [class*="iconEccobell-"] {
  height: unset;
  width: unset;
}

.icon-wrapper {
  height: 36px;
  width: 36px;
  border-radius: 36px;
  background-color: var(--gray-30);
  display: grid;
  place-items: center;
}
</style>
