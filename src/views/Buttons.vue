<template>
  <v-container>
    <v-card class="pa-3">
      <v-row>
        <v-col cols="auto">
          <v-btn color="primary">
            button
          </v-btn>
        </v-col>
        <v-col cols="auto">
          <v-btn color="error">
            button
          </v-btn>
        </v-col>
        <v-col cols="auto">
          <v-btn
            depressed
            color="normal"
          >
            button
          </v-btn>
        </v-col>
        <v-col cols="auto">
          <v-btn disabled>
            button
          </v-btn>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
export default {
  
}
</script>

<style scoped>

</style>