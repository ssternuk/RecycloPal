<template>
  <v-app>
    <div class="home">
      <v-card color="#">
        <v-img
          width="100%"
          height="100%"
          alt="RecyloPal Logo"
          src="../assets/logoandname.png"
        ></v-img
      ></v-card>
      <br />
      <v-card color="#FAD5D1">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <h1>Recycling, made simple.</h1>
                  <br />
                  Easy access to helpful info on local recycling rules.
                  <br /><br />
                  <v-btn color="#5FBE41"
                    ><router-link to="/location" tag="button"
                      >Get started</router-link
                    ></v-btn
                  >
                  <br />
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <h1>Making a difference.</h1>
                  <br />
                  Lets save the world, one bottle at a time!
                  <br />
                  <br />
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <h1>Did you know?</h1>
                  <br />
                  <v-card color="#3F7F2B" dark>
                    <v-icon large>mdi-bottle-soda-classic-outline</v-icon>
                    Recycling a single plastic bottle will save enough energy to
                    power a lightbulb for three hours or more.
                    <br /> </v-card
                  ><br />
                  <v-card color="#3F7F2B" dark>
                    <v-icon large>mdi-delete-empty</v-icon>
                    The average recycling contamination rate is 25%, or 1 in 4
                    items.
                    <br /> </v-card
                  ><br />
                  <v-card color="#3F7F2B" dark>
                    <v-icon large>mdi-recycle</v-icon>
                    53% of people find it easier to throw something in the bin,
                    rather than recycle it
                    <br /> </v-card
                  ><br />

                  <br />
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <h1>Our partners</h1>
                  <br />
                  We work with some great partners, you could be one!
                  <br />
                  <br />
                  <img
                    width="30%"
                    height="30%"
                    src="@/assets/purplebrian.png"
                  />
                  <br /><br />
                  <img
                    width="30%"
                    height="30%"
                    src="@/assets/sainsapples.png"
                  /><br /><br />
                  <v-btn color="#5FBE41"
                    ><router-link to="/location" tag="button"
                      >Get started</router-link
                    ></v-btn
                  >
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
