<template>
  <div class="card">
    <img src="https://source.unsplash.com/random/300x300" />
    <div class="header">Card Header</div>
    <div class="body">Card Body</div>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  width: 100%;

  background-color: #ffffff;
  border-radius: 2rem;
}

.card * {
  padding: 0.8rem;
  text-align: center;
}

.card .header {
  font-weight: bold;
}

.card img {
  border-radius: 2rem;
}
</style>
