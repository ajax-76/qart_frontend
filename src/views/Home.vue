<template>
  <div>
    <ul class="list-unstyled">
      <li class="media" v-for="message in messages" :key="message._id">
        <p>UserName : {{message.username}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src

const API_URL = 'http://localhost:5000/messages';

export default {
  name: 'home',
  data: () => ({
    messages: [],
  }),
  mounted() {
    fetch(API_URL)
      .then(response => response.json())
      .then((result) => {
        this.messages = result;
      });
  },
};
</script>
