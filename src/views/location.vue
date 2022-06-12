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
      <v-card color="#F4A79F" dark
        ><v-card-text style="font-size: 30px; color: #3f7f2b"
          >Can I recycle this?</v-card-text
        ></v-card
      >
      <div id="form-wrapper">
        <form id="select-address-form">
          <v-text-field
            color="#ffffff"
            label="Type your address here"
          ></v-text-field>
          <v-btn color="#5FBE41" @click="searchAddress">Search</v-btn>
        </form>
        <form id="if-address-selected" v-if="addressSelected === true">
          <v-select
            v-model="select"
            :items="addressitems"
            label="Select Address"
            @change="addressDropdownSelect"
            @input="$v.select.$touch()"
            @blur="$v.select.$touch()"
          ></v-select>
        </form>
        <form v-if="addressDropdownSelected === true">
          <div>
            You are in the
            <div style="font-size: 20px">Brent Council</div>
          </div>
          <v-container>
            <div>What are you recycling?</div>
            <v-chip-group v-model="recycleType" @change="recycleTypeSelect">
              <v-chip x-large> Plastic</v-chip>
              <v-chip x-large>Metal</v-chip>
              <v-chip x-large>Glass</v-chip>
              <v-chip x-large>Paper</v-chip>
              <v-chip x-large>Other</v-chip>
            </v-chip-group>
          </v-container>
        </form>
        <form v-if="recycleTypeSelected === true">
          <v-container>
            <div>What type of plastic?</div>
            <v-chip-group v-model="plasticType" @change="plasticTypeSelect">
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec1.png"
                ></v-img
                >PETE</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec2.png"
                ></v-img
                >HDPE</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec3.png"
                ></v-img
                >PVC</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec4.png"
                ></v-img
                >LDPE</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec5.png"
                ></v-img
                >PP</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec6.png"
                ></v-img
                >PS</v-chip
              >
              <v-chip x-large
                ><v-img
                  width="50px"
                  alt="RecyloPal Logo"
                  src="../assets/Rec7.png"
                ></v-img
                >OTHER</v-chip
              >
            </v-chip-group>
          </v-container>
        </form>
        <div v-if="plasticTypeSelected === true">
          Good news! You can recycle this item in Brent! Please put this item in
          your bin with a blue lid.
          <img width="20%" src="@/assets/brent-bin.jpg" />
        </div>
      </div>
    </div>
  </v-app>
</template>
<script>
import { validationMixin } from "vuelidate";
import { required } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],

  validations: {
    select: { required },
    spend: { required },
    time: { required },
    distance: { required },
    days: { required },
  },
  data: () => ({
    addressSelected: false,
    addressitems: [
      "1 Main Street, HA0 1AA",
      "2 Main Street, HA0 1AA",
      "3 Main Street, HA0 1AA",
      "4 Main Street, HA0 1AA",
    ],
    addressDropdownSelected: false,
    recycleTypeSelected: false,
    plasticTypeSelected: false,
  }),

  computed: {
    selectErrors() {
      const errors = [];
      if (!this.$v.select.$dirty) return errors;
      !this.$v.select.required &&
        errors.push("Please select an address from the list");
      return errors;
    },
    selectPlasticsErrors() {
      const errors = [];
      if (!this.$v.select.$dirty) return errors;
      !this.$v.select.required && errors.push("Please select a plastic type");
      return errors;
    },
  },
  methods: {
    searchAddress() {
      this.$v.$touch();
      this.addressSelected = true;
    },
    addressDropdownSelect() {
      this.addressDropdownSelected = true;
    },
    recycleTypeSelect() {
      this.recycleTypeSelected = true;
    },
    plasticTypeSelect() {
      this.plasticTypeSelected = true;
    },
  },
};
</script>
