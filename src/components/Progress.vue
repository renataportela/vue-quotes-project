<template>
  <div class="progress">
    <div class="progress-bar" role="progressbar" :style="{ width: barWidth+'%' }"
         :aria-valuenow="barWidth" aria-valuemin="0" aria-valuemax="100">
      {{ actual }} / {{ max }}
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      max: {required: true},
      actual: {required: true}
    },

    computed: {
      barWidth() {
        return (this.actual / this.max) * 100;
      }
    }
  }
</script>