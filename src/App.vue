<template>
  <div id="app" class="container">
    <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Header>
    <NewQuote @quoteAdded="newQuote"></NewQuote>
    <QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></QuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: click on a quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import Header from "@/components/Header.vue"
import NewQuote from "@/components/NewQuote.vue"
import QuoteGrid from "@/components/QuoteGrid.vue"

@Component({
  components: {
    Header,
    NewQuote,
    QuoteGrid
  }
})
export default class App extends Vue {
  private quotes: string[] = ["Just a quote to see something"]
  private maxQuotes: number = 10

  private newQuote(quote: string) {
    if (this.quotes.length >= this.maxQuotes) {
      alert("Please remove some quotes first!")
      return
    }

    this.quotes.push(quote)
  }

  private deleteQuote(index: number) {
    this.quotes.splice(index, 1)
  }
}
</script>
