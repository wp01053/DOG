<template>
  <section class="section">
    <div class="hero is-danger">
      <div class="hero-body">
        <div class="container">
          <h1 class="title is-1">개사랑</h1>
          <h2 class="subtitle">개사랑 사이트는 개를 사랑하는 사람들을 위한 상세한 정보를 제공합니다.</h2>
        </div>
      </div>
    </div>
    <br>
    <article class="columns">
      <div class="column">
        <div class="notification is-info">
          <figure class="image is-squre">
            <img src="https://upload.wikimedia.org/wikipedia/commons/d/d9/Collage_of_Nine_Dogs.jpg" alt="">
          </figure>
        </div>
      </div>
      <div class="column">
        <div class="message is-info">
          <div class="message-header">
            <p>오늘의 개 사진</p>
          </div>
          <div class="message-body">
            <figure class="image is-squre">
              <img v-bind:src="image" alt="">
            </figure>
          </div>
        </div>
      </div>
    </article>
    <article class="box">
      <h1 class="title">보고싶은 개 정보를 누르세요.</h1>
      <span v-for="dog in dogs" :key="dog">
      <nuxt-link :to="'/dogs/'+ dog" class="button is-success">
        {{dog}}
     
    </nuxt-link> &nbsp;

  </span>
    </article>
  </section>
</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {};
    },
    async asyncData() {
      const myImage = await axios.get('https://dog.ceo/api/breeds/image/random');
      const myDogs = await axios.get('https://dog.ceo/api/breeds/list');
      return { image: myImage.data.message, dogs: myDogs.data.message };
    }
  };
</script>