<template>
  <header class="container-fluid">
    <div class="row p-1 ms_bg align-items-center justify-content-between">
        <div class="col-2 pb-3 d-flex align-items-center">
            <img src="../assets/spotify.png" alt="logo-Spotify">
        </div>
        <div class="col-2">
            <select @click.prevent="$emit('effettuaRicerca', cercaGenere)" v-model="cercaGenere" class="form-select">
                <option selected>All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Metal">Metal</option>
                <option value="Jazz">Jazz</option>
            </select>
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: 'MyHeader',
    data(){
        return{
            cercaGenere: ''
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