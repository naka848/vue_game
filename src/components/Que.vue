<template>
  <div class="bg-warning text-white p-3 m-3">
    <h3>{{ title }}</h3>
    <h3>{{ message }}</h3>
  </div>
</template>

<script>
export default {
  name: 'Que',
  props: {
    title: String,
    message: String,
  }
}
</script>

