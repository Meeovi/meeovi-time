<template>
  <div class="homeSection">
    <v-row>
      <v-col cols="12">
        <h1 id="dateTime"></h1>
      </v-col>
      <v-col cols="12">
        <p id="quote"></p>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import Quote from "inspirational-quotes";

  export default {
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

      setInterval(quoteTimer, 5000);

      function quoteTimer() {
        document.getElementById("quote").innerHTML = Quote.getRandomQuote();
      }
    }
  }
</script>