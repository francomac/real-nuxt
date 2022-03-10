<template>
  <div>
    <h1>Event {{ event.title }}</h1>
  </div>
</template>

<script>
import EventService from '@/services/EventService.js'
export default {
  name: 'EventDetails',
  async asyncData({ error, params }) {
    try {
      const { data } = await EventService.getEvent(params.id)

      return {
        event: data,
      }
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch event #' + params.id + ' at this time. Please try again.',
      })
    }
  },
  head() {
    return {
      title: 'Event ' + this.event.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'All you need to know about event #' + this.event.title,
        },
      ],
    }
  },
}
</script>

<style></style>
