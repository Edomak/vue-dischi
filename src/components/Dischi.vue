<template>
  <section>
      <div class="container">
          <Disco v-for="(disco, index) in filtraDischi" :key="index" :item="disco" />
      </div>
  </section>
</template>

<script>
import Disco from '../components/Disco.vue';
import axios from 'axios';
export default {
    name: "Dischi",
    components: {
        Disco, 
    },
    props: [ "genere" ],

    data: function () {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            dischi: [],
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
    },
    computed: {
        filtraDischi: function () {

            const newArray = this.dischi.filter(
                (element) => {
                    // console.log(element.genre);
                    // console.log(this.genere);
                    if (element.genre == this.genere) {
                        return element
                    } else if (this.genere == "All"){
                        return this.dischi;
                    }
                    
                }
            )
            return newArray;
        }
    }
}
</script>

<style lang="scss" scoped>
    .container {
        display: flex;
        flex-wrap: wrap;
    }
</style>