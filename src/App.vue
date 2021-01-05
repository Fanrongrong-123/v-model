<template>
  <div id="app">
    {{ user }}
    <form @submit.prevent="onsubmit">
      <label>
        <span>用户名</span>
        <!-- <input type="text" v-model="user.username" /> 与下面一段等价-->
        <!-- <input
          type="text"
          :value="user.username"
          @input="user.username = $event.target.value"
        /> -->
        <!-- <MyInput v-model="user.username" /> 与下面一行等价-->
        <MyInput :value="user.username" @input="user.username = $event" />
      </label>
      <label>
        <span>密码</span>
        <input type="password" v-model="user.password" />
      </label>
      <button type="submit">登陆</button>
    </form>
  </div>
</template>

<script>
import MyInput from "./MyInput.vue";
export default {
  components: { MyInput },
  name: "App",
  data() {
    return {
      user: {
        username: "",
        password: "",
      },
      x: [],
    };
  },
  methods: {
    onsubmit() {
      console.log(this.user.username, this.user.password);
    },
  },
};
</script>