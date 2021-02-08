<template>
  <div class="rsvp">
    <div id="myModal" class="modal" v-if="success">
      <div class="modal-content">
        <div class="modal-body">
          <p>Thank you for letting us know!</p>
        </div>
      </div>
    </div>
    <div class="center">
      <p class="p1 f2">Hope you can make it!</p>
      <p>We will be closely monitoring COVID restrictions and will adhere to provincial guidlines for our wedding.</p>
      <p>Please respond by April 23, 2021</p>
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
            name="firstname"
            v-model="form.firstname"
        /></label>
        <label
          >Last Name<input
            type="text"
            class="control"
            name="lastname"
            v-model="form.lastname"
        /></label>
        <label>
          How Many in Your Party<input
            type="number"
            class="control"
            name="num"
            v-model.number="form.num"
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
// import axios from "axios";

export default {
  name: "RSVP",
  data() {
    return {
      form: {
        firstname: "",
        lastname: "",
        num: 0,
        email: "",
        attending: "",
        diet: "",
      },
      success: false,
    };
  },
  methods: {
    resetForm() {
      this.$set(this.form, "firstname", "");
      this.$set(this.form, "lastname", "");
      this.$set(this.form, "num", 0);
      this.$set(this.form, "email", "");
      this.$set(this.form, "attending", "");
      this.$set(this.form, "diet", "");
    },
    encode(data) {
      return Object.keys(data)
        .map(
          (key) => encodeURIComponent(key) + "=" + encodeURIComponent(data[key])
        )
        .join("&");
    },
    handleSubmit(event) {
      event.preventDefault();
      fetch("/", {
        method: "POST",
        headers: { "Content-Type": "application/x-www-form-urlencoded" },
        body: this.encode({
          "form-name": event.target.getAttribute("name"),
          ...this.form,
        }),
      })
        .then(() => {
          this.success = true
          setTimeout(() => this.success = false, 3000)
        })
        .catch((error) => alert(error));
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
.p1{
  font-family: 'Poiret One', cursive;
}
.f2{
  font-size: 2rem;
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
  border-radius: 0.25rem;
  font-family: 'Trirong';
}
.hidden {
  display: none;
}

.modal {
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0, 0, 0);
  background-color: rgba(0, 0, 0, 0.4);
  -webkit-animation-name: fadeIn;
  -webkit-animation-duration: 0.4s;
  animation-name: fadeIn;
  animation-duration: 0.4s;
}

.modal-content {
  position: fixed;
  bottom: 0;
  background-color: #fefefe;
  width: 100%;
  -webkit-animation-name: slideIn;
  -webkit-animation-duration: 0.4s;
  animation-name: slideIn;
  animation-duration: 0.4s;
}

.modal-body {
  padding: 2px 16px;
  display: flex;justify-content: center;
}

/* Add Animation */
@-webkit-keyframes slideIn {
  from {
    bottom: -300px;
    opacity: 0;
  }
  to {
    bottom: 0;
    opacity: 1;
  }
}

@keyframes slideIn {
  from {
    bottom: -300px;
    opacity: 0;
  }
  to {
    bottom: 0;
    opacity: 1;
  }
}

@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>