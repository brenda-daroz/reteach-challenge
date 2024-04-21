<template>
  <div class="site-home">
    <UsersList />
    <aside class="sidebar">
      <h2>Sidebar</h2>
      <hr />
      <h3>What is this website?</h3>
      <h4>Awesome title 4</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita
        explicabo vero commodi hic voluptates dignissimos non maxime, sunt enim
        architecto doloribus, minima nobis nemo. Numquam maiores aliquid itaque
        dolor aliquam!
      </p>
      <hr />
      <h4>Awesome title 4</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita
        explicabo vero commodi hic voluptates dignissimos non maxime, sunt enim
        architecto doloribus, minima nobis nemo. Numquam maiores aliquid itaque
        dolor aliquam!
      </p>
      <p>Random text to conclude.</p>
    </aside>
  </div>
</template>

<style>
.site-home {
  display: flex;
  flex: 1;
  width: 100%;
  box-sizing: border-box;
}
section {
  order: 2;
  width: 80%;
}

.sidebar {
  order: 1;
  width: 20%;
}

@media screen and (max-width: 1024px) {
  .site-home {
    flex-direction: column;
  }

  section,
  .sidebar {
    order: initial;
    width: initial;
  }
}
</style>
