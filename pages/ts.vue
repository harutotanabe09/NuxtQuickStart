<template>
  <div>Name: {{ fullName }} Message: {{ message }}</div>
</template>

<script lang="ts">
import Vue, { PropOptions } from 'vue'

interface User {
  firstName: string
  lastName: string
}

export default Vue.extend({
  name: 'YourComponent',

  props: {
    user: {
      type: Object,
      required: true,
    } as PropOptions<User>,
  },

  data() {
    return {
      message: 'This is a message',
    }
  },

  computed: {
    fullName(): string {
      return `${this.user.firstName} ${this.user.lastName}`
    },
  },
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
