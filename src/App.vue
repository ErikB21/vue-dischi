<template>
  <div id="app">
    <MyHeader @changeGenre="iniziaRicerca" :genereSelezionato="genereSelezionato" />
    <MyMain @genresReady="genereAlbum" :genereRicercato="genereRicercato" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data(){
    return{
      genereSelezionato: [],
      genereRicercato: ''
    }
  },
  methods:{
    genereAlbum(allGenere){
      this.genereSelezionato = allGenere;
    },
    iniziaRicerca(genereRicercato){
      this.genereRicercato = genereRicercato;
    }
  }
}
</script>

<style lang="scss">
  @import '@/style/general.scss';
</style>
