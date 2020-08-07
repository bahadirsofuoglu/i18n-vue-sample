<template>
  <div>
    <div>
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <label>{{ $t("name") }}</label>
        <b-form-group id="input-group-1" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form1.name"
            type="name"
            required
          ></b-form-input>
        </b-form-group>
        <label>{{ $t("surname") }}</label>
        <b-form-group id="input-group-2" label-for="input-2">
          <b-form-input
            id="input-2"
            v-model="form1.surname"
            required
          ></b-form-input>
        </b-form-group>
        <label>{{ $t("gender") }}</label>
        <b-form-group id="input-group-3" label-for="input-3">
          <b-form-select
            id="input-3"
            v-model="form1.gender"
            :options="gender"
            required
          ></b-form-select>
        </b-form-group>

        <b-form-group id="input-group-4">
          <b-form-checkbox-group v-model="form1.checkadult" id="checkboxes-4">
            <b-form-checkbox value="adult">{{ $t("adult") }}</b-form-checkbox>
            <b-form-checkbox value="under age">{{
              $t("!adult")
            }}</b-form-checkbox>
          </b-form-checkbox-group>
        </b-form-group>
      </b-form>
    </div>
    <div>
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <label>{{ $t("E-mail") }}</label>
        <b-form-group id="input-group-1" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            required
          ></b-form-input>
        </b-form-group>
        <label>{{ $t("adress") }}</label>
        <b-form-group id="input-group-2" label-for="input-2">
          <b-form-textarea
            id="input-2"
            v-model="form.adress"
            required
          ></b-form-textarea>
        </b-form-group>
        <label>{{ $t("name") }}</label>

        <b-form-group id="input-group-4">
          <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
            <b-form-checkbox value="okudum">{{ $t("read") }}</b-form-checkbox>
            <b-form-checkbox value="onaylıyorum">{{
              $t("certify")
            }}</b-form-checkbox>
          </b-form-checkbox-group>
        </b-form-group>

        <b-button type="submit" variant="primary">{{ $t("submit") }}</b-button>
        <b-button type="reset" variant="danger">{{ $t("reset") }}</b-button>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form1: {
        name: "",
        surname: "",
        gender: null,
        checkadult: [],
      },
      gender: [{ text: "Select one", value: null }, "female", "male", "custom"],

      form: {
        email: "",
        adress: "",
        food: null,
        checked: [],
      },
      foods: [
        { text: "Select One", value: null },
        "Carrots",
        "Beans",
        "Tomatoes",
        "Corn",
      ],
      show: true,
    };
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault();
      alert(JSON.stringify(this.form1) + JSON.stringify(this.form));
    },
    onReset(evt) {
      evt.preventDefault();
      // Reset our form values
      // this.form.email = "";
      // this.form.name = "";
      // this.form.food = null;
      // this.form.checked = [];
      // this.form1.name = "";
      // this.form1.surname = "";
      // this.form1.gender = null;
      // this.form1.checkadult = [];
      // Trick to reset/clear native browser form validation state

      Object.assign(this.$data, this.$options.data()); // copy data

      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>
