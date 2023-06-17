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

    <div class="text-center"></div>
    <button @click="getPokemonImage">画像を取得</button>
    <img :src="pokemonImage" />
  </v-sheet>
</template>
<style>
.custom-link {
  text-decoration: none;
  color: black;
}
</style>
<script lang="js">
const options = {
    method: 'GET',
}

export default {
    data () {
        return {
            pokemonImage:'',
            finalResultPoint: 1,
            url:'',
    };
  },
  methods: {
    normalizePoint() {
        const point = this.$store.state.point; // $store.state.point を変数 point に代入
        const normalizedPoint = Math.floor((point / 9) * 151) + 1;
        console.log(normalizedPoint);
        this.finalResultPoint = normalizedPoint;
        this.url = `https://pokeapi.co/api/v2/pokemon/${this.finalResultPoint}`;
},
    async getPokemonImage(){
        const response = await fetch(this.url,options)
        .then(response => response.json());
        console.log(response);
        this.pokemonImage = response.sprites.front_default;

        // this.pokemonImage = response;
    },
  },
  created() {
    this.normalizePoint();
    this.getPokemonImage();
  },
}
</script>
