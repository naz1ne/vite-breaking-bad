<script>
export default {
      name: 'AppHeader'
}
</script>
<template>
      <header>
            <div class="logo">
                  <img src="../assets/img/logo.png" alt="">
            </div>
            <h1 class="title">Breaking Bad</h1>
      </header>
</template>
<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

header {
      display: flex;
      padding: 2rem;
      align-items: center;
      justify-content: center;

      .title {
            color: $light;
            font-weight: bold;
      }

      .logo {
            img {
                  width: 200px;
                  margin-right: 0.5rem;
            }
      }
}
</style>