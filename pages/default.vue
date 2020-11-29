<template>
  <div>
    <Nuxt :nuxt-child-key="someKey" />
  </div>
</template>
<script>
export default {
  key(route) {
    return route.fullPath
  },
}
</script>
