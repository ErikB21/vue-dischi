<template>
  <header class="container-fluid">
    <div class="row p-1 ms_bg align-items-center justify-content-between">
        <div class="col-2 pb-3 d-flex align-items-center">
            <img src="../assets/spotify.png" alt="logo-Spotify">
        </div>
        <div class="col-2">
            <select v-model="selezionaGenere" @change.prevent="$emit('changeGenre', selezionaGenere)" class="form-select">
                <option value="" selected>Seleziona un genere</option>
                <option :value="genre" v-for="(genre,index) in genereSelezionato" :key="index">{{genre}}</option>        
            </select>
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: 'MyHeader',
    props:{
        genereSelezionato: Array
    },
    data(){
        return{
            selezionaGenere: ''
        }
    }
}
</script>

<style scoped lang="scss">
    @import '@/style/general.scss';
    .ms_bg{
        background-color: $my_bg_header;
        height: 10vh;
        img{
            width: 40px;
        }  
    }
</style>