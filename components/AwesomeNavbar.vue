<template>
  <div class="navbar-wrapper">
    <nav :class="{ navbar: true, 'is-open': isDropdownOpen }">
      <ul class="navbar-ul">
        <li><a href="/">Home</a></li>
        <li><a href="/">Home 2</a></li>
        <li><a href="/">Home 3</a></li>
        <li><a href="/">Home 4</a></li>
      </ul>
    </nav>
    <button class="navbar-burger" @click="$emit('toggle-dropdown')">
      <span v-if="isDropdownOpen">✖</span>
      <span v-else>☰</span>
    </button>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    isDropdownOpen: Boolean,
  },
  emits: ["toggle-dropdown"],
};
</script>

<style>
.navbar-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-ul {
  display: flex;
  justify-content: space-around;
  list-style: none;
  padding-inline-start: 0;
  margin: 0;
}

.navbar-ul > li {
  margin: 0 1rem;
}

.navbar-ul > li > a {
  text-decoration: none;
}

.navbar-ul > li > a:hover {
  text-decoration: underline;
}

.navbar-burger {
  display: none;
  border: none;
  background-color: transparent;
  cursor: pointer;
  font-size: 1.5rem;
}

@media screen and (max-width: 1024px) {
  .navbar {
    display: none;
    top: 120px;
    right: 0;
    width: 100%;
    position: fixed;
    height: 100%;
    z-index: 1;
    flex-direction: column;
  }

  .is-open {
    display: block;
    justify-content: center;
  }

  .is-open > ul {
    flex-direction: column;
  }

  .navbar-burger {
    display: block;
  }
}
</style>
