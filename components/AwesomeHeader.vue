<template>
  <div :class="{ topnav: true, 'is-open': isNavMenuOpen }">
    <header>
      <h1>Header</h1>
    </header>
    <AwesomeNavbar
      :is-dropdown-open="isNavMenuOpen"
      @toggle-dropdown="toggleDropdown"
    />
  </div>
</template>

<script lang="ts">
import { ref } from "vue";
import AwesomeNavbar from "./AwesomeNavbar.vue";

export default {
  components: {
    AwesomeNavbar,
  },
  setup() {
    const isNavMenuOpen = ref(false);

    const toggleDropdown = () => {
      isNavMenuOpen.value = !isNavMenuOpen.value;
    };

    return {
      isNavMenuOpen,
      toggleDropdown,
    };
  },
};
</script>

<style>
.topnav {
  background-color: aliceblue;
  overflow: hidden;
  padding: 10px;
  justify-content: space-between;
  display: flex;
}

.is-open {
  position: fixed;
  width: 100%;
  box-sizing: border-box;
}
</style>
