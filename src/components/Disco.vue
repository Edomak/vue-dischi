<template>
  <div class="disco_box">
      <img :src="item.poster" alt="">
      <h2>{{ item.title }}</h2>
      <p>{{ item.author }}</p>
      <p>{{ item.year }}</p>
  </div>
</template>

<script>
export default {
    name: "Disco",
    props: [ "item" ]
}
</script>

<style lang="scss" scoped>
    .disco_box {
        width: calc(100% / 5 - 40px);
        background-color: #2e3b46;
        margin: 10px 15px;
        padding: 15px 10px;
        text-align: center;
        border-radius: 10px;

        img {
            width: 90%;
            margin-bottom: 10px;
        }

        h2 {
            color: white;
            font-size: 25px;
            margin-bottom: 20px;
            font-weight: bolder;
        }

        p {
            color:gray;
        }
    }
</style>