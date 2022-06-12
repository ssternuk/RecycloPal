<template>
  <v-footer dark padless>
    <v-card
      color="#ED6C5F"
      flat
      tile
      class="lighten-1 white--text text-center"
      width="100%"
    >
      <v-card-text class="text-lg-h6" color="#FFFFFF" @click="contactus">
        Contact Us
      </v-card-text>
      <v-card-text color="#FFFFFF"
        >©2022 RecycloPal LIMITED. NO RIGHTS RESERVED. RecycloPal LIMITED IS NOT
        A REGISTERED COMPANY IN ENGLAND AND WALES, UNREGISTERED OFFICE
        NODECODE HOUSE.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text color="#FFFFFF">
        {{ new Date().getFullYear() }} — <strong>RecycloPal</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
  export default {
    data: () => ({
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    }),
    methods: {
      contactus() {
        this.$router.push({ name: "contactus" });
      },
    },
  };
</script>
