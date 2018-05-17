<template>
  <div id="app">
    <Home v-if="!isLogin"></Home>
    <Editor v-if="isLogin"></Editor>
  </div>
</template>

<script>
import Home form './components/Home.vue';
import Editor form './components/Editor.vue';

export default {

}
</script>

<style>

</style>

