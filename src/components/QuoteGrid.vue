<template>
  <div class="row">
    <Quote
      v-for="(quote, index) in quotes"
      :key="quote"
      @click.native="deleteQuote(index)"
    >
      {{ quote }}
    </Quote>
  </div>
</template>

<script lang="ts">
import { Component, Emit, Prop, Vue } from "vue-property-decorator"
import Quote from "@/components/Quote.vue"

@Component({
  components: {
    Quote
  }
})
export default class QuoteGrid extends Vue {
  @Prop({ required: true })
  private quotes!: string[]

  @Emit("quoteDeleted")
  deleteQuote(index: number) {}
}
</script>
