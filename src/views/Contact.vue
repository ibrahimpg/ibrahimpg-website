<template>
  <div class="container">
    <div style="width: 600px; text-align: center;"><br><br>

      <div class="mobileSpace"></div>

      <p>
        Submit a form if you would like to get in touch with me or
        <a href="mailto:ibrahimpg@outlook.com">email me directly.</a>
        You can also contact me on
        <a href="https://github.com/ibrahimpg" target="_blank">Github</a>
        or
        <a href="https://www.linkedin.com/in/ibrahimpg/">LinkedIn.</a>
        if you prefer.
      </p>

      <br>

      <div>
        <form v-on:submit.prevent="onSubmit">
          <input type="text" name="name" required v-model="name" placeholder="Name..." class="inputs" />
          <input type="email" name="email" required v-model="email" placeholder="Email..." class="inputs" />
          <textarea name="message" required v-model="message" placeholder="Message..." class="inputs" maxlength="5000" style="height: 200px; resize: none;" />
          <input type="submit" v-bind:value="response" />
        </form>
      </div>

    <br><br></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
      response: '',
    };
  },
  methods: {
    onSubmit() {
      fetch('https://form-handler.herokuapp.com', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ name: this.name, email: this.email, message: this.message }),
      })
        .then(res => res.json())
        .then((data) => {
          this.response = data.msg;
          this.name = '';
          this.email = '';
          this.message = '';
        })
        .catch(() => this.response = 'Error!');
    },
  },
};
</script>

<style scoped>

.inputs {
  width:100%;
  padding: 10px;
  margin: 10px 0;
  background-color: rgba(255,255,255,0.2);
  outline: none;
  border: none;
  transition: 0.3s ease;
  border-left: 2px solid rgba(255,255,255,0.2);
  color: white;
}

input[type=submit] {
  padding: 10px 40px;
  background-color: rgba(255,255,255,0.2);
  outline: none;
  border: none;
  border-left: 2px solid rgba(255,255,255,0.2);
  color: white;
}

::placeholder { color: white; }

.inputs:focus { border-left: 2px solid #EB5160; }

input[type=submit]:active { border-left: 2px solid #EB5160; }

</style>
