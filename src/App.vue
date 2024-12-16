<script setup>
import {useRoute , useRouter  } from "vue-router";
import {useUserStore} from '@/stores/modules/user'
const router = useRouter()
const route = useRoute()

const goList = () => {
  router.push('/list')
}

const userStore = useUserStore()
</script>

<template>
  <div>
    <hr />
    <router-view></router-view>
    <hr />
    <hr />
    <hr />


    我是app<br>
    <el-button @click="$router.push('/home')">跳首页</el-button><br>
    <el-button @click="goList">跳列表页</el-button ><br>
      <p>{{ userStore.token }}</p>
    <el-button type="success" @click="userStore.setToken('abc kkk')">登录</el-button>
    <el-button type="danger" @click="userStore.removeToken()">退出</el-button>
  </div>
</template>

<style scoped>

</style>  
