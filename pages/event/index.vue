<template>
  <div>
    <h1>Event Details Page</h1>
  </div>
</template>

<script>
export default {
  name: 'EventDetails',
  head() {
    return {
      title: 'Event Details Page',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'All you need to know about Event Details',
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
