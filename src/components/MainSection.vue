<template>
  <div>
    <div class="d-flex justify-center ma-4 mb-6 mt-6">
      <v-card width="900">
        <div class="d-flex justify-center mt-2">
          <img src="../assets/marker.png" alt="" width="50px" height="70px" />
        </div>

        <h1 class="d-flex justify-center ma-1">API Demo</h1>
        <h5 class="d-flex justify-center">Search any IP address/domain</h5>
        <div class="ma-5 d-flex justify-center">
          <div class="container1">
            <div class="search-box">
              <input
                type="text"
                class="search-input"
                @keyup.enter="
                  (loader = 'loading4'), geolocation(), updateValue()
                "
                placeholder="Query IP/Domain"
                v-model="ip"
                :loading="loading4"
                :disabled="loading4"
              />

              <v-btn
                depressed
                color="dark"
                class="search-button"
                :loading="loading4"
                :disabled="loading4"
                @click="(loader = 'loading4'), geolocation(), updateValue()"
              >
                <i class="fas fa-search"></i>
                <template v-slot:loader>
                  <span class="custom-loader">
                    <v-icon light>mdi-cached</v-icon>
                  </span>
                </template>
              </v-btn>
            </div>
          </div>
        </div>
      </v-card>
    </div>
    <div>
      <v-container>
        <v-card>
          <v-row>
            <v-col>
              <v-container>
                <v-card class="mx-auto example">
                  <v-simple-table
                    dark
                    v-show="token"
                    fixed-header
                    height="550px"
                  >
                    <template>
                      <thead>
                        <tr>
                          <th class="text-left">Attribute</th>
                          <th class="text-left">Data</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr>
                          <td>Query</td>
                          <td>{{ query }}</td>
                        </tr>
                        <tr>
                          <td>Status</td>
                          <td>{{ status }}</td>
                        </tr>
                        <tr>
                          <td>Country</td>
                          <td>{{ country }}</td>
                        </tr>
                        <tr>
                          <td>City</td>
                          <td>{{ city }}</td>
                        </tr>
                        <tr>
                          <td>Latitude</td>
                          <td>{{ lat }}</td>
                        </tr>
                        <tr>
                          <td>Longitude</td>
                          <td>{{ lon }}</td>
                        </tr>
                        <tr>
                          <td>Timezone</td>
                          <td>{{ timezone }}</td>
                        </tr>
                        <tr>
                          <td>Isp</td>
                          <td>{{ isp }}</td>
                        </tr>
                        <tr>
                          <td>Organization</td>
                          <td>{{ org }}</td>
                        </tr>
                        <tr>
                          <td>Zip</td>
                          <td>{{ zip }}</td>
                        </tr>
                        <tr>
                          <td>CountryCode</td>
                          <td>{{ countryCode }}</td>
                        </tr>
                        <tr>
                          <td>Region</td>
                          <td>{{ region }}</td>
                        </tr>
                        <tr>
                          <td>RegionName</td>
                          <td>{{ regionName }}</td>
                        </tr>
                        <tr>
                          <td>as</td>
                          <td>{{ as }}</td>
                        </tr>
                      </tbody>
                    </template>
                  </v-simple-table>
                </v-card>
              </v-container>
            </v-col>
            <v-col>
              <v-container>
                <v-card class="mx-auto d-flex justify-center">
                  <iframe
                    width="550"
                    height="550"
                    frameborder="0"
                    scrolling="no"
                    marginheight="0"
                    marginwidth="0"
                    :src="
                      'https://maps.google.com/maps?q=' +
                      lat +
                      ',' +
                      lon +
                      '&hl=es&z=14&amp;output=embed'
                    "
                  >
                  </iframe>
                </v-card>
              </v-container>
            </v-col>
          </v-row>
        </v-card>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainSection",
  data() {
    return {
      loader: null,
      loading: false,

      loading4: false,
      query: "",
      status: "",
      country: "",
      countryCode: "",
      region: "",
      regionName: "",
      city: "",
      zip: "",
      lat: "",
      lon: "",
      timezone: "",
      org: "",
      isp: "",
      as: "",
      token: false,
    };
  },

  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => (this[l] = false), 3000);

      this.loader = null;
    },
  },

  methods: {
    updateValue() {
      this.ip = null;
    },

    geolocation() {
      this.token = true;
      fetch(`http://ip-api.com/json/${this.ip}`)
        .then((response) => response.json())
        .then((data) => {
          console.log(data);
          this.query = data.query;
          this.status = data.status;
          this.country = data.country;
          this.countryCode = data.countryCode;
          this.region = data.region;
          this.regionName = data.regionName;
          this.city = data.city;
          this.zip = data.zip;
          this.lat = data.lat;
          this.lon = data.lon;
          this.timezone = data.timezone;
          this.isp = data.isp;
          this.org = data.org;
          this.as = data.as;
        });
    },
  },
};
</script>

<style>
.custom-loader {
  animation: loader 1s infinite;
  display: flex;
}

@keyframes loader {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}

.example::-webkit-scrollbar {
  display: none !important;
}

body {
  background-color: #f2f2f2;
  font-family: sans-serif;
}
.search-box {
  width: 100%;
  position: relative;
  display: flex;
  justify-content: center;
}
.search-input {
  width: 100%;
  padding: 10px;
  border: 4px solid rgba(0, 0, 0, 0.87);
  border-radius: 10px 0 0 10px;
  border-right: none;
  outline: none;
  font-size: 20px;
  color: black;
  background: none;
}
.search-button {
  text-align: center;
  height: 60px !important;
  width: 60px !important;
  outline: none !important;
  cursor: pointer;
  border: 4px solid rgba(0, 0, 0, 0.87);
  border-radius: 0 10px 10px 0;
  border-left: none;
  background: none;
  font-size: 20px !important;
  border-left: 4px solid rgba(0, 0, 0, 0.87);
}
.container1 {
  width: 60%;
}
.search-button:hover {
  background-color: black !important;
  color: white;
}
</style>
