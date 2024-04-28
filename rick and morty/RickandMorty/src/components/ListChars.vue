<script setup>
    const char = defineProps(["image", "name", "status", "species", "gender", "location", "episode", "url"])
    const idChar = char.url.split('/')[6]
    // const eps = (char.episode.split(',')).lenght
    const urlImg = char.image

</script>

<template>
    <div class="card">
        <img class="card-img-top" :src="urlImg" alt="Card image cap">
        <div class="card-body">
          <h3>{{ char.name }}</h3>
          <p>Status: {{ char.status }}</p>
          <p>Species: {{ char.species }}</p>
          <p>Gender: {{ char.gender }}</p>
          <p>Location: {{ char.location.name }}</p>
          <p>{{ eps }}</p>
        </div>
      </div>
</template>