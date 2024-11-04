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
        <h1>Phone</h1>
        <p class="page-description">Please select a department to call. Turn on video to show a staff member your issue if needed.</p>
      </div>
      <div class="list-container p-4">
        <ul class="list">
          <li v-for="link in links" :key="link.name">
            <div @click="selectOption(link.value)" :class="['flex items-center w-full gap-4', { selected: selectedOption === link.value }]">
              <div class="icon-wrapper">
                <span :class="link.icon"></span>
              </div>
              <span class="flex-1">{{ link.name }}</span>
            </div>
          </li>
        </ul>
      </div>
      <div class="cta-container">
        <button class="btn-primary">
          Call
        </button>
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue';

  const selectedOption = ref("reception");
  const links = ref([
    {
      name: "Reception",
      icon: "iconEccobell-person",
      value: "reception",
    },
    {
      name: "Housekeeping",
      icon: "iconEccobell-bed",
      value: "housekeeping",
    },
    {
      name: "In room dining",
      icon: "iconEccobell-food",
      value: "dining",
    },
  ]);

function selectOption(option: string) {
  selectedOption.value = option;
}
</script>


<style scoped>
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

.cta-container {
  height: 112px;
  bottom: 0;
  background-color: var(--white-core);
  padding: 20px 30px 0 30px;
  position: absolute;
  width: 100%;
  box-shadow: 0 -3px 8px #1F1F1E0D;
}

.cta-container .btn-primary {
  width: 100%;
  padding: 10px 0;
}

.list li {
  cursor: pointer;
}

.list .selected {
  color: var(--blue-secondary);
}

.list .selected .icon-wrapper {
  background-color: #19759433;
}
</style>
