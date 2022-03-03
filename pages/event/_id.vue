<template>
  <div>
    <h1>Event #{{ id }}</h1>
  </div>
</template>

<script>
export default {
  name: 'EventDetails',
  head() {
    return {
      title: 'Event #' +  this.id,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'All you need to know about event #' + this.id,
        },
      ],
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    },
  },
}
</script>

<style></style>
