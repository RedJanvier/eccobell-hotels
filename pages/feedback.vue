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
        <h1>Feedback</h1>
        <p class="page-description">Thank you for your feedback—we appreciate your input and incourage you to stay in touch</p>
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
      name: "Rate your room",
      icon: "iconEccobell-bed",
      href: "/",
    },
    {
      name: "Contact our phone",
      icon: "iconEccobell-phone",
      href: "/phone",
    },
    {
      name: "Help Center or FAQs",
      icon: "iconEccobell-chat",
      href: "/",
    },
    {
      name: "Special Offers/Promotions",
      icon: "iconEccobell-food",
      href: "/",
    },
    {
      name: "Follow on Social Media",
      icon: "iconEccobell-food",
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
