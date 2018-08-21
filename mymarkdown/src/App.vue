<template>
  <div id="app">
    <!--　条件付きレンダリング  -->
    <Home v-if="!isLogin"></Home>
    <Editor v-if="isLogin"></Editor>
  </div>
</template>

<script>
// Vueを読み込む
import Home from './components/Home.vue';
import Editor from './components/Home.vue';

export default {
  name: 'app',
  data() {
    return {
      isLogin: false
    }
  },
  // Vue.jsでコンポーネントが作成されたタイミングで実行されます
  created:function() {
    firebase.auth().onAuthStateChanged(user => {
      console.log(user);
      if(user) {
        this.isLogin = true;
      } else {
        this.isLogin = false;
      };
    });
  },
  components: {
    'Home': Home,
    'Editor': Editor,
  }
}
</script>

<style>

</style>

