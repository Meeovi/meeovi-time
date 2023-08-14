<template>
  <div class="homeSection">
    <v-row>
      <v-col cols="12">
        <h1 id="dateTime"></h1>
      </v-col>
      <v-col cols="12">
        <quote />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import quote from '../components/quote.vue'

  export default {
    components: { quote },
    mounted() {
      setInterval(myTimer, 1000);

      function myTimer() {
        const month = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October",
          "November", "December"
        ];
        const date = new Date();

        let name = month[date.getMonth()];
        const day = new Date().toLocaleString();

        document.getElementById("dateTime").innerHTML = name + " " + day;

        document.getElementById("quote").innerHTML = Quote.getRandomQuote();
      }
    }
  }
</script>