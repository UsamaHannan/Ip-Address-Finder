<template>
  <div>
    <v-container class="mb-3">
      <v-card>
        <v-container>
          <h2 class="mb-2">
            <v-icon class="mb-1">mdi-shield-half-full</v-icon> Security
          </h2>
          <v-row>
            <v-col class="ma-3">
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Abuser
              </p>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Cloud
                Provider
              </p>
              <p><v-icon class="mb-1">mdi-close-circle-outline</v-icon> Tor</p>
            </v-col>
            <v-col>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Anonymous
              </p>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Tor exit
                node
              </p>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Proxy
              </p>
            </v-col>
            <v-col>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Attacker
              </p>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Relay
              </p>
            </v-col>
            <v-col>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Bogon
              </p>
              <p>
                <v-icon class="mb-1">mdi-close-circle-outline</v-icon> Threat
              </p>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "MainSecurity",

  data: () => ({}),
};
</script>
