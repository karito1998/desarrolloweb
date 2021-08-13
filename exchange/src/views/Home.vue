<template>
  <main>
    <px-assets-table v-bind:assets="assets" />
  </main>
</template>

<script>
// @ is an alias to /src
import api from "@/api";
import PxAssetsTable from "@/components/PxAssetsTable.vue";

export default {
  name: "Home",
  components: { PxAssetsTable },

  data() {
    return {
      assets: [],
    };
  },
  created() {
    api.getAssets().then((assets) => (this.assets = assets));
  },
};
</script>
