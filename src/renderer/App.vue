<template>
  <main>
    <TheHeader />
    <EnviromentTable />
  </main>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

import TheHeader from './components/TheHeader'
import EnviromentTable from './components/EnviromentTable'

export default {
  components: { TheHeader, EnviromentTable }
}
</script>

<style>
body {
    background: #efefef;
}
</style>
