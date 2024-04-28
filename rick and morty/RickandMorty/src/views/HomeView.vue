<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListChars from '../components/ListChars.vue';

let chars = reactive(ref())

onMounted(()=> {
  fetch("https://rickandmortyapi.com/api/character/?page=7")
  .then(response => response.json())
  .then(response => {
    chars.value = response.results
    console.log(chars)
  });
})
</script>

<template>
  <main>
    <header>
      <div class="navbar">
        <img src="/src/components/ram_logo.png" alt="logo" style="width: 200px;">
        <div class="links">
          <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
          <router-link class="nav-link" to="/about">About</router-link>
        </div>
      </div>
    </header>

    <div class="container">
      <ListChars
      v-for="char in chars"
            :key="char.name"
            :name="char.name"
            :image="char.image"
            :status="char.status"
            :species="char.species"
            :gender="char.gender"
            :location="char.location"          
            :url="char.url"
      ></ListChars>
    </div>

    <footer>
      <div>
        Unimar | ADS | {{ new Date().getFullYear() }}
      </div>
    </footer>
  </main>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

body{
  background-color: rgb(0, 0, 0);
  font-family: "Poppins", sans-serif;
  font-weight: 100;
  font-style: normal;
}
header{
  background-color: rgb(19, 8, 61);
  position: fixed;
  top: 0;
  left: 0;
  padding: 20px;
  width: 100%;
  display: flex;
  align-items: center;
  height: 40px;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.219);
  color: white;
}

.navbar{
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 96%;
}

.links{
  display: flex;
  justify-content: space-between;
  width: 320px;
  font-size: 30px;
  font-weight: 200;
}

.links a{
  outline: none;
  text-decoration: none;
  color: white;
}

.container{
  background-image: url(/src/components/ram_background.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: none;
  padding: 40px;
  height: 100%;
  padding-bottom: 150px;
  margin: 70px -8px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 80px;
  border-radius: 10px;
  margin-bottom: 40px;
}

.card{
  background-color: rgb(76, 76, 197);
  background: linear-gradient(360deg, rgb(50, 50, 136) 0%, #69c8ecff 100%);
  padding: 20px;
  width: fit-content;
  height: fit-content;
  border-radius: 10px;
  color: rgb(216, 216, 216);
  font-size: larger;
}

.card-body{
  max-width: 200px;
  height: 100%;
}

.card img{
  max-width: 250px;
  border-radius: 5px;
  box-shadow: 1px 2px 2px rgba(0, 0, 0, 0.384);
}

footer{
  background-color: rgb(9, 9, 43);
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 40px;
  color: white;
}
</style>