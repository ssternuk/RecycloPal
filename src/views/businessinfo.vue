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
      <v-card color="#FAD5D1">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <h1>How could RecycloPal benefit your business?</h1>
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-trash-can-outline</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Encourage more informed recycling decisions within your
                  business
                </div>
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
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-account-group</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Join a community of businesses moving towards a more recycling
                  aware environment
                </div>
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
                <v-avatar class="ma-3" size="50" tile>
                  <v-icon large>mdi-foot-print</v-icon>
                </v-avatar>
                <div style="padding: 0px 2px 5px 2px">
                  Become more informed about how your business' rubbish
                  decisions impact the environment
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      <v-card color="#FAD5D1">
        <v-container
          ><v-row
            ><v-col>
              <v-card color="#3F7F2B" dark>
                <br/>
                <h3>
                  Start your journey towards a more environmentally aware
                  business
                </h3>

                <v-btn color="#5FBE41"
                  ><br/><br/><router-link to="/signup" tag="button"
                    >Click here to register</router-link
                  ></v-btn
                ><br/><br/>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>

      <v-card color="#ED6C5F" dark
        ><v-card-text style="font-size: 30px; color: #ffffff"
          >Don't just take our word for it! <br />
          <br />
          See what our other corporate partners had to say:</v-card-text
        ></v-card
      >
      <v-card color="#FAD5D1">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-card color="#3F7F2B" dark>
                <div style="padding: 0px 2px 5px 2px">
                  <br/><img
                    width="30%"
                    height="30%"
                    src="@/assets/purplebrian.png"
                  />
                  <br />
                  We love RecycloPal! Our company has been using RecycloPal for
                  6 months now, our favourite feature is that everyone can now
                  make informed choices about what they can recycle in the
                  office or at home.
                </div>
                <br />
                <br />
                <div style="padding: 0px 2px 5px 2px">
                  <img
                    width="30%"
                    height="30%"
                    src="@/assets/sainsapples.png"
                  />
                  <br />
                  Here at Sainsapples we are focused on making recycling easier
                  for the community around us. Thanks to Recyclopal, our
                  community are more aware of the recycling options that we have
                  within our store.
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
