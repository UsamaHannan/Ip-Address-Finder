<template>
  <div>
    <v-app-bar app color="dark" dark>
      <v-toolbar-title
        ><img
          class="mt-2"
          src="../assets/logo6.png"
          alt=""
          width="120px"
          height="70px"
      /></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn text>Home</v-btn>
        <v-btn text>Docs</v-btn>
        <v-btn text
          ><v-icon color="green">mdi-circle-medium</v-icon>Status</v-btn
        >
        <v-btn text>FAQ</v-btn>
        <v-btn text>Login</v-btn>
      </v-toolbar-items>

      <v-spacer></v-spacer>

      <template v-if="$vuetify.breakpoint.smAndUp">
        <v-btn icon>
          <v-icon>mdi-export-variant</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-delete-circle</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-plus-circle</v-icon>
        </v-btn>
      </template>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "MainHeader",

  data: () => ({}),
};
</script>
