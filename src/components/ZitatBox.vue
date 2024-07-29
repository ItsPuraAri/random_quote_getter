<template>
  <div class="container">
    <div class="zitatBox">

      <h2>"{{ quoteText }}"</h2>

      <p>~{{ author }}</p>

      <div class="innerContent">
        <button id="copy" v-on:click="copyQuote">Kopieren</button>
        <button id="next" v-on:click="getQuote">Nächstes Zitat &raquo;</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ZitatBox',

  data() {
    return {
      quoteText: '',
      author: ''
    }
  },

  methods: {

    async getQuote() {
      try {
        let response = await fetch('https://dummyjson.com/quotes/random');
        let data = await response.json();
        this.quote = data.quote;
        this.author = data.author;
      } catch (error) {
        alert(error.message);
      }

      this.quoteText = this.quote;
    },

    copyQuote() {
      navigator.clipboard.writeText(this.quoteText);
    }
  },

  mounted() {
    this.getQuote();
  }
}
</script>

<style scoped>
#copy {
  left: 5mm;
}

#next {
  right: 5mm;
}

button {
  position: absolute;
  bottom: 5mm;
  cursor: pointer;
  padding: 20px 30px;
  background-color: #ffaec9;
  border: none;
  color: black;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 15px;
  border-radius: 4px;
}

.container {
  background-color: white;
  border-radius: 4px;
  height: 80vh;
  width: 100vw;
  box-sizing: border-box;
  padding: 2cm;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.zitatBox {
  background-color: #e6e6e6;
  border-radius: 4px;
  padding: 13% 40%;
  box-sizing: border-box;

  position: relative;
}

h2 {
  font-weight: bold;
  font-style: italic;
}

p {
  font-style: italic;
  color: gray;
}

</style>