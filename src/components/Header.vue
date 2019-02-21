<template>
    <div class="row">
        <div class="col-sm-12">
          <h3>Quotes Added</h3>
          <div class="progress">
              <div class="progress">
                  <div class="progress-bar"
                       role="pregressbar"
                       aria-valuenow="60"
                       aria-valuemax="100"
                       :style="{width: quoteCount * 10 + '%'}">
                      {{ quoteCount }} / {{ maxQuotes }}
                  </div>
              </div>
          </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>

<style scoped>
</style>
