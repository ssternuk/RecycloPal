<template>
  <v-app>
    <div class="home">
        <v-card color="#1F7087">
        <v-img width="100%" height="100%"
          alt="RecyloPal Logo"
          src="../assets/logoandname.png"
        ></v-img
      ></v-card>
      <v-card color="#FAD5D1">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                <h1>Where can I recycle?</h1><br />
                Scan the QR code at your venue or search for your location
                <br /><br />
                <img
                        src="@/assets/QRCode.png"
                      />
                <br />
                <br />
                Find out what you can recycle and how to recycle it
                <br /><br />
                <img width="90%" height="90%"
                        src="@/assets/bins.png"
                      />
                <br />
                <br />
                You can even rate how good the recycling at your location is 
                <br /><br />
                <img width="90%" height="90%"
                        src="@/assets/stars.png"
                      />
                <br />
                <br /> 
                <br /> 
                <v-btn color="#5FBE41"><router-link to="/location" tag="button">Search your location here</router-link></v-btn>
                <br /><br /><br /></div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
 
      <v-card color="#FAD5D1">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                <h1>What can I recycle?</h1>
                <br />
                Simply scan a product's barcode or search for your product in our system
                <br /><br />
                <img width="90%" height="90%"
                        src="@/assets/scanning.jpg"
                      />
                <br />
                <br />
                Find out whether it is recyclable in your location
                <br /><br />
                <img width="90%" height="90%"
                        src="@/assets/location.png"
                      />
                <br />
                <br />
                Gain awareness on how you can help the enviroment by recycling your item
                <br /> 
                <br /> 
                <v-btn color="#5FBE41"><router-link to="/location" tag="button">Scan your rubbish here</router-link></v-btn>
                <br /> 
                <br /> 
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </div>
  </v-app>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
};
</script>
