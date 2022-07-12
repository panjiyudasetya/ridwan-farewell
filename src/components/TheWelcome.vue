<script setup>
import WelcomeItem from "./WelcomeItem.vue";
</script>

<template>
  <WelcomeItem v-for="(item, i) in messages" :key="i">
    <template #icon>
      <img :alt="item.from" :src="item.icon" width="35" height="35" />
    </template>

    <blockquote>
      {{ item.message }}
      <span>{{ item.from }}</span>
    </blockquote>
  </WelcomeItem>
</template>
<script>
import messageData from "../data/messages.json";

export default {
  data() {
    return {
      messages: messageData,
    };
  },
};
</script>
<style>
@import url(https://fonts.googleapis.com/css?family=Open+Sans:400italic);
blockquote {
  font-size: 1.2em;
  font-family: Open Sans;
  font-style: italic;
  line-height: 1.7em;
}

blockquote::before {
  font-family: Arial;
  content: "\201C";
  color: #78c0a8;
  font-size: 4em;
  left: -5px;
  top: 24px;
}

blockquote::after {
  content: "";
}

blockquote span {
  display: block;
  color: #333333;
  font-style: normal;
  font-weight: bold;
  margin-top: 1em;
}
</style>
