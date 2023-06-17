<template>
  <v-sheet
    elevation="12"
    max-width="600"
    rounded="lg"
    width="100%"
    class="pa-4 text-center mx-auto mt-4"
  >
    <h2 class="text-h5 mb-6">ポケモン自己診断 結果発表</h2>

    <p class="mb-4 text-medium-emphasis text-body-2">
      あなたをポケモンに例えると...
    </p>
    <!-- 罫線(不要なので外す)
        <v-divider class="mb-4"></v-divider> -->

    <div class="text-center">
      {{ $store.state.point }}
    </div>
  </v-sheet>
</template>
<style>
.custom-link {
  text-decoration: none;
  color: black;
}
</style>
<script lang="js">

export default {
  data () {
    return {
    }
  },
  methods: {
    startAnalysis () {

    }
  }
}
</script>
