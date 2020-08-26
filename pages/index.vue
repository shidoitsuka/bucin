<template>
  <v-container>
    <v-card class="mx-auto" width="300" max-height="300" outlined>
      <v-list-item two-line>
        <v-list-item-content>
          <v-card-text>{{ stories[currentPage] }}</v-card-text>
        </v-list-item-content>
      </v-list-item>
      <hr />
      <v-card-actions>
        <v-btn text :disabled='currentPage == 0' @click="currentPage--">Prev</v-btn>
        <v-spacer></v-spacer>
        <v-btn text @click="currentPage == 25 ? '' : currentPage++" :to="currentPage == stories.length - 1 ? '/landing' : '#'">Next</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
import stories from "~/assets/stories.js";
export default {
  data() {
    return {
      stories,
      currentPage: 0
    };
  }
};
</script>

<style lang="scss">
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
