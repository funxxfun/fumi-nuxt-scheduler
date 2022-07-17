<template>
  <v-container>
    <event-editor />
    <v-btn>
      Go!
    </v-btn>
  </v-container>
</template>

<script>
import EventEditor from '../components/EventEditor.vue'
export default {
  components: { EventEditor },
  head() {
    return {
      title: 'New Event'
    }
  }
}
</script>
