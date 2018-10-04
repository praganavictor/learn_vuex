<template>
  <div class="">
    <button :disabled="!hasUser" @click="mudarDados">Mudar dados do usuario</button>
  </div>
</template>
<script>
  export default {
    methods: {
      mudarDados () {
        const payload = {
          name: 'Pragana Victor',
          email: 'email@email.com',
          level: 'usuario'
        }
        this.$store.commit('CHANGE_USER', payload)
      }
    },
    computed: {
      hasUser () {
        return this.$store.state.user.name !== ''
      }
    }
  }
</script>
