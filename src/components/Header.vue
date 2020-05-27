<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress">
          <div class="progress-bar" role="progress-bar" aria-valuenow="60" aria-voluemin="0" aria-voluemax="100"
          :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
            {{quoteCount}} / {{maxQuotes}}
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>


  export default {
    props: ['quoteCount', 'maxQuotes'],
    updated() {
      console.log( this.quoteCount, this.maxQuotes)
    }

  }


</script>

<style>

</style>
