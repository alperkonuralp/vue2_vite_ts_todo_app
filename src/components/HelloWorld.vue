<template>
  <div class="greetings">
    <h1 class="green">
      <a href="https://github.com/logue/vite-vue2-ts-starter#readme" target="_blank" rel="noopener">
        {{ msg }}
      </a>
    </h1>
    <p>
      Build:
      <time :datetime="meta.date" v-text="new Date(meta.date).toLocaleString()" />
    </p>
    <p v-if="!title">
      Please define
      <code>VITE_APP_TITLE</code>
      variable in to
      <code>.env</code>
      file.
    </p>
    <h3>
      You've successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a>
      +
      <a href="https://v2.vuejs.org/" target="_blank" rel="noopener">Vue 2</a>
      . What's next?
    </h3>
  </div>
</template>

<script lang="ts" setup>
import { defineProps, ref } from 'vue';

import Meta from '@/Meta';

/** HelloWorld Component */
const { msg } = defineProps({
  /** Prop message */
  msg: { type: String, required: true },
});

/** Meta information */
const meta = ref(Meta);

const title = ref(import.meta.env.VITE_APP_TITLE);
</script>

<style lang="scss" scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
  margin-bottom: 1rem;
}

h3 {
  font-size: 1.2rem;
  margin-top: 1rem;
}

.greetings {

  h1,
  h3,
  p {
    text-align: center;
  }
}

@media (min-width: 1024px) {
  .greetings {

    h1,
    h3,
    p {
      text-align: left;
    }
  }
}
</style>
