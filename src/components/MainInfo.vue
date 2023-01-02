<template>
  <div>
    <v-container class="mt-2">
      <v-card class="mx-auto">
        <v-container>
          <v-row>
            <v-col>
              <h2 class="mb-2">
                <v-icon class="mb-1">mdi-wifi</v-icon> Connections
              </h2>

              <v-row>
                <v-col class="ma-3">
                  <h4>IP address type</h4>
                  <br />
                  <h4>Route</h4>
                  <br />
                  <h4>ASN</h4>
                  <br />
                  <h4>ASN type</h4>
                  <br />
                  <h4>Organization</h4>
                  <br />
                  <h4>Domain</h4>
                </v-col>
                <v-col class="ma-3">
                  <p>IPv4</p>
                  <p>62.24.64.0/20</p>
                  <p>AS16019 Vodafone Czech Republic A.S.</p>
                  <p>isp</p>
                  <p class="mb-1">
                    <a href="">Vodafone Czech Republic A.S.</a>
                  </p>
                  <br />
                  <p>vodafone.cz</p>
                </v-col>
              </v-row>
            </v-col>
            <v-col>
              <h2 class="mb-2">
                <v-icon class="mb-1">mdi-domain</v-icon> Company
              </h2>

              <v-row>
                <v-col class="ma-3">
                  <h4>Name</h4>
                  <br />
                  <h4>Domain</h4>
                  <br />
                  <h4>Type</h4>
                  <br />
                </v-col>
                <v-col>
                  <p><a href="">Vodafone Internet Catv</a></p>
                  <p>upcbroadband.cz</p>
                  <p>isp</p>
                </v-col>
                <v-card class="ma-6" color="#bb2155" dark max-width="500">
                  <v-card-title> </v-card-title>

                  <v-card-text
                    color="black"
                    class="text-h5 font-weight-bold d-flex align-content-center cardtext"
                  >
                    Access all Ipregistry data with just one line of code using
                    our API.
                  </v-card-text>

                  <v-card-actions class="d-flex justify-center">
                    <v-btn depressed color="black"> Sign Up </v-btn>
                  </v-card-actions>
                </v-card>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "MainInfo",

  data: () => ({}),
};
</script>

<style>
.cardtext {
  color: white !important;
}
</style>
