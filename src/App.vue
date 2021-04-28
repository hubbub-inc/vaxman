<style>
@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
</style>

<template>
  <div id="app">
 
    <CompanyData/> <!-- Added New tag -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import CompanyData from './components/Comp' //import new component

export default {
  name: 'App',
  components: {
    HelloWorld,
    CompanyData //register new component
  }
}
</script>


