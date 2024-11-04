<template>
  <div>
    <header class="pb-16">
      <div class="container-custom">
        <nav class="flex justify-between pt-6 items-center">
          <nuxt-link to="/"><span class="iconEccobell-logo"></span></nuxt-link>
          <button class="flex items-center">
            <span>EN</span>
            <span class="iconEccobell-globe"></span>
          </button>
        </nav>
        <div>
          <h1 class="text-4xl py-4">Eccobell Hotel Shoreditch</h1>
          <h2 class="text-3xl text-secondary pb-2">Room 301</h2>
          <p class="py-3">Welcome to the Guest Code. This is your home for all the information and services you may require during your stay.</p>
          <button class="btn-primary">
            <span class="iconEccobell-chat"></span>
            <span>Ask Belle, your guest assistant</span>
          </button>
        </div>
      </div>
    </header>
    <main class="list-wrapper home">
      <div class="list-container p-4">
        <ul class="list list-home">
          <li v-for="link in links" :key="link.name">
            <nuxt-link :to="link.href" class="flex items-center w-full gap-4">
              <span :class="link.icon"></span>
              <span class="flex-1">{{ link.name }}</span>
              <span class="iconEccobell-arrow-right"></span>
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
      name: "Hotel Telephone",
      icon: "iconEccobell-phone",
      href: "/phone",
    },
    {
      name: "View hotel information",
      icon: "iconEccobell-book",
      href: "/hotel",
    },
    {
      name: "In room dining",
      icon: "iconEccobell-food",
      href: "/",
    },
    {
      name: "Spa booking",
      icon: "iconEccobell-spa",
      href: "/",
    },
    {
      name: "Book a taxi",
      icon: "iconEccobell-car",
      href: "/",
    },
    {
      name: "Food delivery",
      icon: "iconEccobell-scooter",
      href: "/food",
    },
    {
      name: "Things to do",
      icon: "iconEccobell-location",
      href: "/things",
    },
    {
      name: "Feedback",
      icon: "iconEccobell-globe",
      href: "/feedback",
    },
  ]);
</script>


<style scoped>
main {
  min-height: calc(100vh - 360px);
}
header {
  min-height: 372px;
}

@media screen and (max-width: 340px) {
  h1,
  h2 {
    padding: 0 !important;
  }
}
</style>
