<template>
  <v-ons-page>
    <v-ons-toolbar>
      <div class="left">
        <v-ons-back-button/>
      </div>
      <div class="center">決済履歴</div>
    </v-ons-toolbar>
  </v-ons-page>
</template>

<script>
import { mapActions } from "vuex";
export default {
  methods: {
    ...mapActions("app", ["getTransaction"])
  },
  async mounted() {
    await this.getTransaction();
  }
};
</script>
