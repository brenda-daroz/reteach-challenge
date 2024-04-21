<template>
  <div class="site-container">
    <AwesomeHeader />
    <main class="site-main">
      <slot />
    </main>
    <AwesomeFooter />
  </div>
</template>

<style>
.site-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.site-main {
  display: flex;
  flex: 1;
  box-sizing: border-box;
}
</style>
