<template>
  <a href="url">{{ text }}</a>
</template>

<script>
export default {
  name: 'Navigation',
  props: ['url', 'text']
}
</script>

<style>
  a {
    text-decoration: none;
  }
</style>
