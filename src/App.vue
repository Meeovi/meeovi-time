<template>
  <v-app :theme="theme">
    <v-app-bar id="topnav" density="compact">
      <v-app-bar-title><a class="logobrand" href="/">
          <v-icon start icon="fas fa-clock"></v-icon>Meeovi Time
        </a></v-app-bar-title>

      <v-spacer></v-spacer>

      <div class="d-flex align-center flex-column flex-sm-row fill-height">
        <v-col>
          <v-btn :prepend-icon="theme === 'dark' ? 'fas fa-sun' : 'fas fa-moon'" @click="toggleTheme"></v-btn>
        </v-col>

        <v-col>
          <ecosystemmenu />
        </v-col>
      </div>
    </v-app-bar>

    <v-main>
      <v-card>
        <v-layout>
          <v-main id="sidebarNav"></v-main>
          <main id="mainSection">
            <router-view />
          </main>
        </v-layout>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
import ecosystemmenu from '@/components/ecosystemmenu.vue'
import { useTheme } from 'vuetify'

export default {
  setup () {
    const theme = useTheme()

    return {
      theme,
      toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
    }
  },
  components: { ecosystemmenu },
  data() {
      return {
        drawer: null,
        location: 'bottom',
        rail: true,
      }
    }
}
</script>