<template lang="html">
  <div id="app">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
    <nav class="navbar navbar-inverse">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">
            <img src="./assets/rotten.png" class="logo" alt="">
          </a>
          <div class="navbar-header navbar-right">
            <ul class="nav navbar-nav ">
                  <li><a href="#"><span class="glyphicon glyphicon-user" aria-hidden="true"></span></a></li>
            </ul>
          </div>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'app',

  data () {
    return {
      message: 'Hello Vue!'
    }
  }
}
</script>

<style lang="css">
body{
  background-image: url("image/rotten.png");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-color:rgba(0, 0, 0, 0.5);
  /*margin-bottom: 50vw;*/
}
.logo{
  /*width: 10vw;*/
  height: 2vw;
}
</style>
