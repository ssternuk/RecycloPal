<template>
  <v-app>
    <div class="home">
        <v-card color="#ED6C5F">
        <v-img
          width="100%"
          height="100%"
          alt="RecyloPal Logo"
          src="../assets/logoandname.png"
        ></v-img
      ></v-card>

      <v-card color="#1F7087" dark
        ><v-card-text style="font-size: 30px; color: #ffffff"
          >Contact us</v-card-text
        ></v-card
      >                <div style="padding: 0px 2px 5px 2px">
                  If you have any further questions about how RecyloPal can help you as 
                  an individual or a business, get in contact today!
                </div>
      <v-card color="#1F7087">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#4ea3bb" dark>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-office-building-marker</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  RecycloPal Limited, <br />
                  NodeCode House <br />
                  EC2 6HP <br />
                </div>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-email</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  hello@recylopal.co.uk
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
    name: "ContactUs",
    components: {},
  };
</script>
