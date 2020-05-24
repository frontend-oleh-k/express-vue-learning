<template>
  <form class="form">
    <v-text-field
      v-model="email"
      :error-messages="emailErrors"
      label="E-mail"
      required
      type="email"
      @input="$v.email.$touch()"
      @blur="$v.email.$touch()"
    ></v-text-field>
    <v-text-field
      v-model="password"
      :error-messages="passwordErrors"
      label="Password"
      type="password"
      required
      @input="$v.password.$touch()"
      @blur="$v.password.$touch()"
    ></v-text-field>
    <v-checkbox
      v-model="checkbox"
      label="Remember me?"
      required
    ></v-checkbox>
    <v-btn class="mr-4" @click="submit">Login</v-btn>
  </form>
</template>

<script>
import { validationMixin } from 'vuelidate';
import {
  required, maxLength, email, minLength,
} from 'vuelidate/lib/validators';

export default {
  mixins: [validationMixin],

  validations: {
    email: { required, maxLength: maxLength(255), email },
    password: { required, minLength: minLength(6), maxLength: maxLength(100) },
  },

  data: () => ({
    email: '',
    password: '',
    checkbox: false,
  }),

  computed: {
    passwordErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      if (!this.$v.password.required) {
        errors.push('Password is required');
      }
      if (!this.$v.password.maxLength) {
        errors.push('Password must be at most 100 characters long');
      }
      if (!this.$v.password.minLength) {
        errors.push('Password must be at least 6 characters long');
      }
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      if (!this.$v.email.email) {
        errors.push('Must be valid e-mail');
      }
      if (!this.$v.email.required) {
        errors.push('E-mail is required');
      }
      if (!this.$v.email.maxLength) {
        errors.push('Email must be at most 255 characters long');
      }
      return errors;
    },
  },

  methods: {
    submit() {
      console.log(this.$data);
      this.$v.$touch();
    },
  },
};
</script>

<style lang="scss" scoped>
  .form {
    max-width: 560px;
    padding: 0 20px;
    margin: 50px auto;
  }
</style>
