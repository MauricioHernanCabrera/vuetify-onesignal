<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-btn @click="enableSW">Activar SW</v-btn>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  methods: {
    enableSW () {
      this.$OneSignal.push(() => {
        this.$OneSignal.isPushNotificationsEnabled((isEnabled) => {
          if (isEnabled) {
            console.log('Push notifications are enabled!')
          } else {
            console.log('Push notifications are not enabled yet.')
          }
        })
      })
    }
  },
  
}
</script>
