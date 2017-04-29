<template style="">
  <div id="app" class="bg">
    <div id="">
      <nav class="navbar navbar-inverse">
          <div class="container-fluid">
            <a class="navbar-brand" href="#" style="padding-top: 0;">
              <img src="./image/rottentext.png" class="logo" alt="">
            </a>
            <div class="navbar-header navbar-right" >
              <ul class="nav navbar-nav ">
                    <li><a href="#" class="navbar-brand" style="padding-bottom: 0;" ><span class="glyphicon glyphicon-user" aria-hidden="true"></span></a></li>
              </ul>
            </div>
          </div>
      </nav>
      <div class="col-md-12">
        <div class="panel panel-default">
          <div class="panel-heading">MOVIE</div>
            <div class="panel-body bg">
              <div class="col-sm-5 col-md-3">
                <div class="thumbnail">
                  <img src="./image/Guardians.jpg" alt="...">
                  <div class="caption">
                    <h3>Thumbnail label</h3>
                    <p>...</p>
                  <!-- <router-link to="/Test">Test</router-link> -->
                    <p><a href="#" class="btn btn-primary" role="button">Button</a> <a href="#" class="btn btn-default" role="button">Button</a></p>
                  </div>
                </div>
              </div>
              <div class="col-sm-5 col-md-3">
                <div class="thumbnail">
                  <img src="./image/Guardians.jpg" alt="...">
                  <div class="caption">
                    <h3>Thumbnail label</h3>
                    <p>...</p>
                    <p><a href="#" class="btn btn-primary" role="button">Button</a> <a href="#" class="btn btn-default" role="button">Button</a></p>
                  </div>
                </div>
              </div>
              <div class="col-sm-5 col-md-3">
                <div class="thumbnail">
                  <img src="./image/Guardians.jpg" alt="...">
                  <div class="caption">
                    <h3>Thumbnail label</h3>
                    <p>...</p>
                    <p><a href="#" class="btn btn-primary" role="button">Button</a> <a href="#" class="btn btn-default" role="button">Button</a></p>
                  </div>
                </div>
              </div>
              <div class="col-sm-5 col-md-3">
                <div class="thumbnail">
                  <img src="./image/Guardians.jpg" alt="...">
                  <div class="caption">
                    <h3>Thumbnail label</h3>
                    <p>...</p>
                    <p><a href="#" class="btn btn-primary" role="button">Button</a> <a href="#" class="btn btn-default" role="button">Button</a></p>
                  </div>
                </div>
              </div>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/

}
body {
  background-color:rgba(153, 255, 153, 0.5);
  background-image: url("image/rotten.png");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
}
.bg{
  /*opacity: 0.4;*/
}
.logo{
  /*width: 10vw;*/
  height: 4vw;
}
</style>
