<template>
  <div id="app">
    <div v-if="ready">
      <div v-if="auther">
        <img :src="profile.photoURL" alt="">
        <h2>{{ profile.displayName }}</h2>
        <p v-for="movie in movies">Rating: {{movie.rating}}</p>
        <p v-for="movie in movies">{{movie.title}}</p>
        <p v-for="movie in movies">{{movie.like}}</p>
        <p v-for="movie in movies">{{movie.dislike}}</p>
        <div class="progress" v-for="movie in movies">
          <!-- {{movie}} -->
        <div class="progress-bar progress-bar-success" :style="{width: movie.dislike + '%'}">
          <span class="sr-only">movie</span>
        </div>
        <!-- <div class="progress-bar progress-bar-warning progress-bar-striped" style="width: 20%">
          <span class="sr-only"></span>
        </div>
        <div class="progress-bar progress-bar-danger" style="width: 10%">
          <span class="sr-only"></span>
        </div> -->
        </div>
        <button type="button" @click="logout()">Logout</button>
        <div class="rating">
          <p v-for="movie in movies">{{ movie.vote }}</p>
          <button type="button" v-on:click="updateAddItem(movies[0])">add</button>
          <button type="button" v-on:click="updateSubItem(movies[0])">sub</button>
        </div>
      </div>
      <div v-else>
        <img src="./assets/logo.png">
        <button type="button" @click="login()">Login</button>

      </div>
    </div>
    <div v-else>
      <p>Loading....</p>
    </div>
  </div>
</template>

<script>
  // Initialize Firebase
  import firebase from 'firebase'
  var firebaseApp = firebase.initializeApp({
    apiKey: 'AIzaSyB0BoqBlmjwwZGcMl-g5oPVNrT0iNQsorI',
    authDomain: 'rotten-durian.firebaseapp.com',
    databaseURL: 'https://rotten-durian.firebaseio.com',
    projectId: 'rotten-durian',
    storageBucket: 'rotten-durian.appspot.com',
    messagingSenderId: '431169168698'
  })
  var db = firebaseApp.database()
  var provider = new firebase.auth.FacebookAuthProvider()

  // let moviesRef = db.ref('movies')

export default {
    name: 'app',
    data () {
      return {
        todos: [],
        ready: false,
        auther: false,
        like: 0,
        dislike: 0,
        counter: 1,
        rating: 0,
        movies: []
      }
    },
    methods: {
      login () {
        firebase.auth().signInWithRedirect(provider)
      },
      logout () {
        let vm = this
        firebase.auth().signOut().then(function () {
          vm.auther = false
        }, function (error) {
          console.error(error)
        })
      },
      addRating: function () {
        // moviesRef.push(this.newMovie)
        this.$firebaseRefs.movies.push({
          text: 'text'
        })
      },
      updateAddItem: function (movie) {
        // moviesRef.counter.child(newMovie['1']).set(this.counter)
        this.$firebaseRefs.movies.child(movie['.key']).update({
          like: movie.like += 1,
          vote: movie.vote += 1
        })
      },
      updateSubItem: function (movie) {
        // moviesRef.counter.child(newMovie['1']).set(this.counter)
        this.$firebaseRefs.movies.child(movie['.key']).update({
          dislike: movie.dislike += 1,
          vote: movie.vote += 1
        })
      }
    },
    mounted () {
      let vm = this
      firebase.auth().onAuthStateChanged(function (user) {
        if (user) {
          vm.auther = true
          vm.profile = user
          console.log(vm.profile)
          vm.$bindAsArray('movies', db.ref('movies/'))
        }
        vm.ready = true
      })
      firebase.auth().getRedirectResult().then(function (result) {
        if (result.credential) {}
      }).catch((error) => {
        console.error(error)
      })
    }

  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
