<template>
  <section>
      <div class="container">
          <Disco v-for="(disco, index) in dischi" :key="index" :item="disco" />
      </div>
  </section>
</template>

<script>
import Disco from '../components/Disco.vue';
import axios from 'axios';
export default {
    name: "Dischi",
    components: {
        Disco
    },
    data: function () {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            dischi: []
        } 
    },
    created: function () {
        axios
        .get(this.apiUrl)
        .then(
            (result) => {
                // console.log(result.data);
                this.dischi = result.data.response
                // console.log(this.dischi);
            }
        )
    }
}
</script>

<style lang="scss" scoped>
    .container {
        display: flex;
        flex-wrap: wrap;
    }
</style>