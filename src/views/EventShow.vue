<template>
  <h1>Event #{{ id }}</h1>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true
    }
  }
}
</script>
