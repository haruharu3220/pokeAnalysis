<template>
  <v-sheet
    elevation="12"
    max-width="600"
    rounded="lg"
    width="100%"
    class="pa-4 text-center mx-auto mt-4"
  >
    <h2 class="text-h5 mb-6">第1問</h2>

    <p class="mb-4 text-medium-emphasis text-body-2">
      あなたは明るいと言われますか？
    </p>
    <v-divider class="mb-4"></v-divider>

    <div class="text-center">
      <v-btn
        class="text-none ma-2"
        color="yellow"
        rounded
        variant="flat"
        width="200"
        to="/questions"
        @click="$store.commit('increment', 2)"
      >
        はい
      </v-btn>
      {{ $store.state.point }}
      <v-btn
        class="text-none ma-2"
        color="yellow"
        rounded
        variant="flat"
        width="200"
        to="/questions"
        @click="$store.commit('increment', 1)"
      >
        いいえ
      </v-btn>
      <v-btn
        class="text-none ma-2"
        color="yellow"
        rounded
        variant="flat"
        width="200"
        to="/questions"
      >
        どちらかといえばはい
      </v-btn>
      <v-btn
        class="text-none ma-2"
        color="yellow"
        rounded
        variant="flat"
        width="200"
        to="/questions"
      >
        どちらかといえばいいえ
      </v-btn>
    </div>
  </v-sheet>
</template>

<script>
export default {};
</script>

<style></style>
