<template>
  <div id="app">
     <router-view></router-view>
  </div>
 
</template>

<script>
import HelloWorld from './components/HelloWorld'

import home from './components/home'

import createUser from './components/createUser'
import showUser from './components/showUser'
import updateUser from './components/updateUser'

import users from './components/users'
import login from './components/login'
import register from './components/register'
import navbar from './components/navbar'
import index from './components/index'
import resources from './components/resources'
import showResource from './components/showResource'

export default {
  name: 'App',
  components: {
    HelloWorld,

    home,

    createUser,
    showUser,
    updateUser,
    users,
    login,
    register,
    navbar,
    index,
    resources,
    showResource
  },
  methods:{
    
  }
}
</script>

<style>
@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
@import "../node_modules/@fortawesome/fontawesome-free/css/all.min.css";

</style>
