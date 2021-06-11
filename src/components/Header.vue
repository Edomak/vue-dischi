<template>
  <header>
        <img src="../assets/spotify.png" alt="Logo Spotify">
        <div class="select">
          <label for="generi">Filtra per genere:</label>

            <select v-model="select" @change="$emit('changeSelect', select)" name="generi" id="generi">
                <option value="All">All</option>
                <option :value="genre" v-for="(genre, index) in generi" :key="index">{{ genre }}</option>
            </select>
        </div>
  </header>
</template>

<script>
export default {
    name: "Header",
    props: {
        "generi": Array
    },
    components: {
        
    },
    data: function () {
        return {
            select: ""
        } 
    },
}
</script>

<style lang="scss" scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 80px;
        line-height: 80px;
        background-color: #2e3b46;

        img {
            height: 80%;
            vertical-align: middle;
            margin-left: 20px;
        }

        .select {
        margin-right: 20px;

        label {
            margin-right: 10px;
        }

        select {
            border-radius: 5px;
            padding: 8px 12px;
            font-size: 16px;
            font-weight: bolder;
        }
    
    }  

    
}
</style>