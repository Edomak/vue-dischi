<template>
  <header>
      <img src="../assets/spotify.png" alt="Logo Spotify">
  </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
    header {
        height: 80px;
        line-height: 80px;
        background-color: #2e3b46;

        img {
            height: 80%;
            vertical-align: middle;
            margin-left: 20px;
        }
    }

</style>