<template>
  <div>
    <h1>Welcome Vuex2</h1>
    <h4>{{user}}</h4>
    <hr>
    <cc-users></cc-users>
  </div>
</template>

<script>
import CcUsers from './components/users/main.vue'
import { mapState } from 'vuex'
  export default {
    name: 'CodecastApp',
    mounted () {
      const payload = {
        name: 'Victor Pragana',
        email: 'vp@email.com',
        level: 'admin'
      }
      setTimeout(() => {
        this.$store.commit('CHANGE_USER', payload)
      }, 3000)

    },
    components: {
      CcUsers
    },
    computed: {
      user () {
        const { name, email } = this.$store.state.user
        return `O usuario logado e ${name} e possui o email ${email}.`

      // return `O usuario logado e ${this.$store.state.user.name} e possui o email ${this.$store.state.user.email}.`
      }
    }
  }
</script>
