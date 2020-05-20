<template>
  <div class="main">
      <ApplicationRow 
      v-for="application in applicationVariants" 
      :enviromentVariants="enviromentVariants" 
      :application="application" 
      :key="application.id" 
      @selectApplicationEnviroment="selectApplicationEnviroment"
      />
  </div>
</template>


<script>
import ApplicationRow from './ApplicationRow.vue'
export default {
  components: {
    ApplicationRow
  },
  data () {
    return {
      applicationVariants: [
        {
          id: 'myaccount',
          name: 'My account',
          selected: 'local'
        },
        {
          id: 'push',
          name: 'Push Service',
          selected: 'local'
        },
        {
          id: 'napi',
          name: 'Napi',
          selected: 'local'
        }
      ],
      selectedEnviroment: null,
      enviromentVariants: ['local', 'staging', 'beta', 'production']
    }
  },
  methods: {
    selectApplicationEnviroment (application, enviroment) {
      this.applicationVariants.find(
        variant => variant.id === application.id
      ).selected = enviroment
    }
  }
}
</script>

<style lang="scss">

.button {
  border: 1px solid transparent;
  border-radius: 0.25rem;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  border-radius: 0.2rem;
  background-color: rgba(29, 201, 183, 0.87);

  color: #fff;

  transition: all 0.15s ease-in-out;
    &:hover {
      background-color: #1dc9b7;
    }
}
</style>