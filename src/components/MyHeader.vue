<template>
  <header class="container-fluid">
    <div class="row p-1 ms_bg align-items-center">
        <div class="col-2 pb-3 d-flex align-items-center">
            <img class="" src="../assets/spotify.png" alt="logo-Spotify">
        </div>
    </div>
  </header>
</template>

<script>
export default {
    name: 'MyHeader'
}
</script>

<style scoped lang="scss">
    @import '@/style/general.scss';
    .ms_bg{
        background-color: $my_bg_header;
        height: 80px;
        img{
            width: 40px;
        }  
    }
</style>