<template>
  <v-app dark>
    <!-- Top App Bar with only Logout -->
    <v-app-bar app flat>
      <v-spacer />
      <v-btn @click="$auth.logout()" color="blue" dark class="ml-4">Logout</v-btn>
    </v-app-bar>

    <!-- Main Content -->
    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  middleware: ['auth']
}
</script>
