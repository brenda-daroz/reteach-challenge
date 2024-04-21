<template>
  <div class="site-container">
    <AwesomeHeader />
    <main>
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
</style>
