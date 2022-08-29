<template>
  <div id="app">
    <MyHeader @effettuaRicerca="genereAlbum" />
    <MyMain :genereSelezionato="genereSelezionato" />
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
      genereSelezionato: ''
    }
  },
  methods:{
    genereAlbum(genere){
      this.genereSelezionato = genere;
    }
  }
}
</script>

<style lang="scss">
  @import '@/style/general.scss';
</style>
