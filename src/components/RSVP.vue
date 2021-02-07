<template>
  <div class="rsvp">
    <div class="center">
      <p>
        Happy to have you come, Lorem ipsum dolor sit amet, consectetur
        adipiscing elit.
      </p>
      <p>Please respond by (yada yada)</p>
    </div>
    <form
      name="rsvp"
      method="POST"
      data-netlify="true"
      netlify-honeypot="bot-field"
      @submit.prevent="handleSubmit"
    >
      <input type="hidden" name="form-name" value="rsvp" />
      <div>
        <label
          >First Name<input
            type="text"
            class="control"
            name="first-name"
            v-model="form.firstName"
        /></label>
        <label
          >Last Name<input
            type="text"
            class="control"
            name="last-name"
            v-model="form.lastName"
        /></label>
        <label>
          How Many in Your Party<input
            type="number"
            class="control"
            name="number"
            v-model.number="form.numParty"
          />
        </label>
        <label
          >Email<input
            type="email"
            class="control"
            name="email"
            v-model="form.email"
        /></label>
        <label class="attending">
          Attending
          <label>
            Yes
            <input
              type="radio"
              name="attending"
              value="Attending"
              v-model="form.attending"
            />
          </label>
          <label>
            No
            <input
              type="radio"
              name="attending"
              value="Not Attending"
              v-model="form.attending"
            />
          </label>
        </label>
        <label
          >Dietary Restrictions<input
            type="text"
            class="control"
            name="diet"
            v-model="form.diet"
        /></label>
      </div>

      <p>
        <button type="submit">Send</button>
      </p>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "RSVP",
  data() {
    return {
      form: {
        firstName: "",
        lastName: "",
        numParty: 0,
        email: "",
        attending: "",
        diet: "",
      },
    };
  },
  methods: {
    resetForm() {
      this.$set(this.form, "firstName", "");
      this.$set(this.form, "lastName", "");
      this.$set(this.form, "numParty", 0);
      this.$set(this.form, "email", "");
      this.$set(this.form, "attending", "");
      this.$set(this.form, "diet", "");
    },
    encode(data) {
      return Object.keys(data)
        .map(
          (key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join("&");
    },
    handleSubmit() {
      const axiosConfig = {
        header: { "Content-Type": "application/x-www-form-urlencoded" },
      };
      axios.post(
        "/",
        this.encode({
          "form-name": "rsvp",
          ...this.form,
        }),
        axiosConfig
      );
      this.resetForm();
    },
  },
};
</script>

<style>
form div {
  display: grid;
  grid-gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  align-items: center;
}
.rsvp {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  margin: auto;
}
.center {
  text-align: center;
  flex: 1;
}
.control {
  display: block;
  border-radius: 0.25rem;
  padding: 0.75rem 0.5rem;
  margin: auto;
  border: none;
  outline: none;
  width: 100%;
  box-sizing: border-box;
  background-color: var(--control);
  color: var(--bg-primary);
}
.attending {
  display: flex;
  justify-content: space-around;
  height: 100%;
  align-items: center;
}
button[type="submit"] {
  padding: 0.75rem 1rem;
  margin-top: 1rem;
  background-color: var(--btn);
  color: var(--text);
  border: none;
  outline: none;
  color: white;
  font-size: 1.25rem;
}
</style>