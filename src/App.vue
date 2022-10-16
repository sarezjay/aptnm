<template>
  <div class="h-screen w-full bg-gray-900 md:p-10">
    <div class="main-container">
      40.641620<br />
      -73.951820
      <br />
      <br />
      <br />
        <input type="text" id="code"
          v-model="code"
          class="bg-gray-500 
          border 
          border-gray-300 
          text-white
          text-5xl font-serif
          rounded-lg 
          focus:ring-blue-500 
          focus:border-white-500 
          p-2.5
          w-44"
          maxlength="10"
          required>
          <br />
          <button class="bg-blue-500 hover:bg-blue-700 text-white text-lg font-bold py-2 px-4 rounded m-10" @click="go">Go</button>
          <br /><br />
          <img src="./assets/muffin.png" class="max-w-xs shadow-xl dark:shadow-gray-800 mx-auto rounded-lg blur-sm"/>
    </div>
  </div>

</template>

<style scoped lang="postcss">
.main-container {
  @apply w-full h-full text-5xl font-serif text-center text-white tracking-wide;
}
</style>

<script>
import { ref } from '@vue/reactivity'
export default {
  components: {},
  name: 'App',

  setup() {
    const code = ref('')

    const go = async () => {
      window.location.href = `https://tiny.cc/${code.value}`
    }

    return {
      go,
      code
    }
  },
}
</script>