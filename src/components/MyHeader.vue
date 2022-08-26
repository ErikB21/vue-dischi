<template>
  <header class="container-fluid m-0">
    <div class="row p-1 ms_bg">
        <div class="col">
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
    header{
        height: 70px;
        .ms_bg{
            background-color: $my_bg_header;
            img{
                width: 50px;
            }  
        }
    }
</style>