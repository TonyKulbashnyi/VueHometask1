<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        {{ hello }}
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Main',

    data: () => ({
      hello: 'Hello 🌍 '
    }),
  }
</script>
