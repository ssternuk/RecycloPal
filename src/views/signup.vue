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
    </div>
    <div id="form-wrapper" v-if="finish === false">
      <form>
        <v-card color="#F4A79F" dark
          ><v-card-text style="font-size: 30px; color: #3f7f2b"
            >Register your business</v-card-text
          ></v-card
        >
        <v-text-field
          v-model="comname"
          :error-messages="comnameErrors"
          label="Company Name"
          dark
          required
          @input="$v.comname.$touch()"
          @blur="$v.comname.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="name"
          :error-messages="nameErrors"
          label="Name"
          dark
          required
          @input="$v.name.$touch()"
          @blur="$v.name.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="email"
          :error-messages="emailErrors"
          label="Company E-mail"
          dark
          required
          @input="$v.email.$touch()"
          @blur="$v.email.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="Postcode"
          :error-messages="postcodeErrors"
          label="Postcode"
          dark
          required
          @input="$v.Postcode.$touch()"
          @blur="$v.Postcode.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="Address"
          :error-messages="addressErrors"
          label="Address"
          dark
          required
          @input="$v.Address.$touch()"
          @blur="$v.Address.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="Password"
          :error-messages="passwordErrors"
          label="Password"
          dark
          required
          @input="$v.Password.$touch()"
          @blur="$v.Password.$touch()"
        ></v-text-field>
        <v-text-field
          v-model="ConfPassword"
          :error-messages="confpasswordErrors"
          label="Confirm Password"
          dark
          required
          @input="$v.ConfPassword.$touch()"
          @blur="$v.ConfPassword.$touch()"
        ></v-text-field>
        <br />
        <v-card color="#3F7F2B" dark
          ><v-card-text style="font-size: 30px; color: #ffffff"
            >Add your recycling info</v-card-text
          ></v-card
        >
        <v-card color="#3F7F2B" dark
          ><v-card-text style="font-size: 15px; color: #ffffff"
            >Submit your company’s recycling information to join the Recyclopal
            database. You will recieve a personised QR code that can displayed
            at your business or on your website inlcuding quick and simple
            recycling information tailored specifically to your business.
          </v-card-text></v-card
        >
        <v-text-field
          v-model="recycleinfo"
          label="Add your recycling info"
          dark
          required
          @input="$v.recycleinfo.$touch()"
          @blur="$v.recycleinfo.$touch()"
        ></v-text-field>
        <v-btn color="#5FBE41" @click="back"> Attach images </v-btn>
        <v-checkbox
          v-model="checkbox1"
          :error-messages="checkbox1Errors"
          label="Tick this if your recycling is avaliable to employees only"
          dark
          required
          @change="$v.checkbox1.$touch()"
          @blur="$v.checkbox1.$touch()"
        ></v-checkbox>
        <v-checkbox
          v-model="checkbox2"
          :error-messages="checkbox2Errors"
          label="Do you agree to the T&Cs?"
          dark
          required
          @change="$v.checkbox2.$touch()"
          @blur="$v.checkbox2.$touch()"
        ></v-checkbox>
        <v-btn color="#5FBE41" @click="submit"> Submit </v-btn>
        <br /><br />
        <v-btn color="#5FBE41" @click="clear"> Clear </v-btn>
      </form>
    </div>
    <div id="form-wrapper" v-if="finish === true">
      <v-card color="#5FBE41" dark
        ><v-card-text
          >Thank you for your submission, here is your personal QR code to
          display in your venue!</v-card-text
        ></v-card
      ><br />
      <img width="50%" height="68%" src="@/assets/BusinessQRCode.png" /> <br />
      <v-btn color="#5FBE41" @click="back"> Back </v-btn>
    </div>
  </v-app>
</template>

<script>
import { validationMixin } from "vuelidate";
import { required, maxLength } from "vuelidate/lib/validators";

export default {
  name: "Volunteer",
  mixins: [validationMixin],
  validations: {
    comname: { required },
    name: { required, maxLength: maxLength(10) },
    email: { required },
    postcode: { required },
    address: { required },
    password: { required },
    confpassword: { required },

    checkbox1: {
      checked(val) {
        return val;
      },
    },

    checkbox2: {
      checked(val) {
        return val;
      },
    },
  },

  data: () => ({
    comname: "",
    name: "",
    email: "",
    postcode: "",
    address: "",
    password: "",
    confpassword: "",

    checkbox1: false,
    checkbox2: false,
    finish: false,
  }),

  computed: {
    checkboxErrors() {
      const errors = [];
      if (!this.$v.checkbox.$dirty) return errors;
      !this.$v.checkbox.checked && errors.push("You must agree to continue!");
      return errors;
    },
    comnameErrors() {
      const errors = [];
      if (!this.$v.comname.$dirty) return errors;
      !this.$v.comname.required &&
        errors.push("Please enter your company name");
      return errors;
    },
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.required &&
        errors.push("Please enter the primary contact name");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail address");
      !this.$v.email.required &&
        errors.push("Please enter your primary contact email address");
      return errors;
    },
    postcodeErrors() {
      const errors = [];
      if (!this.$v.postcode.$dirty) return errors;
      !this.$v.postcode.required &&
        errors.push("Please enter your company postcode");
      return errors;
    },
    addressErrors() {
      const errors = [];
      if (!this.$v.address.$dirty) return errors;
      !this.$v.address.required &&
        errors.push("Please enter the first line of the address");
      return errors;
    },
    passwordErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      !this.$v.password.required &&
        errors.push("Please enter a valid password");
      return errors;
    },
    confpasswordErrors() {
      const errors = [];
      if (!this.$v.confpassword.$dirty) return errors;
      !this.$v.confpassword.required &&
        errors.push("Your passwords do not match");
      return errors;
    },
  },

  methods: {
    back() {
      this.$v.$reset();
      this.comname = "";
      this.name = "";
      this.email = "";
      this.postcode = "";
      this.address = "";
      this.password = "";
      this.confpassword = "";
      this.checkbox1 = false;
      this.checkbox2 = false;
      this.finish = false;
    },
    submit() {
      this.$v.$touch();
      this.finish = true;
    },
    clear() {
      this.$v.$reset();
      this.comname = "";
      this.name = "";
      this.email = "";
      this.postcode = "";
      this.address = "";
      this.password = "";
      this.confpassword = "";
      this.checkbox1 = false;
      this.checkbox2 = false;
      this.finish = false;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@200;400&display=swap");
#form-wrapper {
  font-family: "Work Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 10px;
}
</style>
