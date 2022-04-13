<template>
  <div class="app-main-layout">
    <AppNavbar @click="isOpen = !isOpen" />

    <AppSidebar v-model="isOpen" />

    <main class="app-content" :class="{ full: !isOpen }">
      <div class="app-page">
        <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <a class="btn-floating btn-large blue" href="#">
        <i class="large material-icons">add</i>
      </a>
    </div>
  </div>
</template>

<script>
import AppNavbar from "@/components/AppNavbar.vue";
import AppSidebar from "@/components/AppSidebar.vue";

export default {
  name: "main-layout",
  data: () => ({
    isOpen: true,
  }),
  components: {
    AppNavbar,
    AppSidebar,
  },
};
</script>
