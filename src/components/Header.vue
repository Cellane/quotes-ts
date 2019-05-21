<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes added</h3>
      <div class="progress">
        <div class="progress">
          <div
            class="progress-bar"
            role="progressbar"
            :style="{ width: (quoteCount / maxQuotes) * 100 + '%' }"
          >
            {{ quoteCount }} / {{ maxQuotes }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator"

@Component
export default class Header extends Vue {
  @Prop({ required: true })
  private quoteCount!: number

  @Prop({ required: true })
  private maxQuotes!: number
}
</script>

<style scoped></style>
