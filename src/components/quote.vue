<template>
    <div>
      <meta http-equiv="refresh" content="60">
      <p id="quote"></p>
    </div>
</template>

<script>
import Quote from "inspirational-quotes";

export default {
    mounted() {
      setInterval(quoteTimer, 1000);

      function quoteTimer() {
        document.getElementById("quote").innerHTML = Quote.getRandomQuote();
      }
    }
}
</script>

<script setup>

</script>