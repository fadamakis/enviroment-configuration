<template>
  <div class="application-row">
    <h4>{{application.name}}</h4>

    <b-button-group class="button-group">
      <b-button
        v-for="enviroment in enviromentVariants"
        @click="$emit('selectApplicationEnviroment', application, enviroment)"
        :key="enviroment"
        :pressed="enviroment === application.selected"
        variant="primary"
      >{{enviroment }}</b-button>
    </b-button-group>
    <button class="button button--build">Build</button>
  </div>
</template>

<script>
export default {
  props: ['application', 'enviromentVariants']
}
</script>

<style lang="scss">
.application-row {
    display: flex;
    border-bottom: 1px solid #ddd;
    padding: 20px;
    h4 {
        flex: 1;
        align-items: center;
        display: flex;
        font-size: 20px;
        margin: 0;
    }
    .button-group {
        flex: 2;
        margin: 0 20px;
    }

}
</style>