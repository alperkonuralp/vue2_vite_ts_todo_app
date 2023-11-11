<template>
  <div class="home">
    <the-Welcome />
  </div>
</template>

<script lang="ts" setup>
import { watch } from 'vue';

// import { useStore } from '@logue/vue2-helpers/vuex';
import { useRoute } from 'vue-router/composables';

// Components
import TheWelcome from '@/components/TheWelcome.vue';

/** Home Component */
/** Route */
const route = useRoute();
/** Vuex */
// const store = useStore();

/* *
 * Computed
 * /
const computedValue: Ref<string> = computed({
  get: () => store.getters.computedValue,
  set: v => store.dispatch('setComputedValue', v)
}
 */
console.log('first');

// Watch
watch(
  () => route?.name,
  name => console.log('route is changed:', name)
);
</script>
