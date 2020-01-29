<template>
  <div class="contact">
    <v-container fluid style="overflow: auto; position: fixed; box-sizing: border-box; left: 0px; top: 40px; right: 0px; bottom: 0px; width: 100vw; height: 100vh; background-color: rgba(0, 0, 0, 0.75); color: rgb(232, 232, 232);">
      <h1 style="margin: 10px;">contact</h1>

      <v-row class="mx-left" style="margin: 10px; margin-bottom: 50px;">
        <v-card width="600px">
          <v-form
            style="margin: 20px;"
            ref="form"
          >
            <v-text-field
              v-model="name"
              :counter="10"
              :error-messages="nameErrors"
              label="Name"
              required
              @input="$v.name.$touch()"
              @blur="$v.name.$touch()"
            ></v-text-field>

            <v-text-field
              v-model="email"
              :error-messages="emailErrors"
              label="E-mail"
              required
              @input="$v.email.$touch()"
              @blur="$v.email.$touch()"
            ></v-text-field>

            <v-textarea
              v-model="message"
              :error-messages="messageErrors"
              label="Message"
              required
              @input="$v.message.$touch()"
              @blur="$v.message.$touch()"
            ></v-textarea>
            <div class="text-center">

            <v-btn
              :disabled="disabled"
              text
              @click="submit"
            >
              send
            </v-btn>
            </div>
          </v-form>
        </v-card>
      </v-row>

    </v-container>
  </div>
</template>


<script>
// import Axios from 'axios'
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'


const params = new URLSearchParams();

export default {
  name: "contact",
  mixins: [validationMixin],
  validations: {
    name: { required, maxLength: maxLength(10) },
    email: { required, email },
    message: { required, maxLength: maxLength(200) }
  },
  data: () => ({
    name: '',
    email: '',
    message: '',
    disabled: false,
  }),
  computed: {
    nameErrors () {
      const errors = []
      if (!this.$v.name.$dirty) return errors
      !this.$v.name.maxLength && errors.push('Name must be less than 10 characters')
      !this.$v.name.required && errors.push('Name is required.')
      return errors
    },
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Must be valid e-mail')
      !this.$v.email.required && errors.push('E-mail is required')
      return errors
    },
    messageErrors () {
      const errors = []
      if (!this.$v.message.$dirty) return errors
      !this.$v.message.maxLength && errors.push('Message must be less than 200 characters')
      !this.$v.message.required && errors.push('Message is required')
      return errors
    },
  },
  methods: {
    submit: function() {
      this.$v.$touch()
      if (!this.$v.$invalid){
        this.disabled = true
        console.log("submit start");
        const url = 'https://docs.google.com/forms/u/0/d/e/1FAIpQLSdSCNqa7gfv7X9pOh2S-tByBBiWMfH07xUAMkac-bjmVw5t2A/formResponse'

        params.append('entry.765084666',this.name);
        params.append('entry.1709451944',this.email);
        params.append('entry.520273347',this.message);

        fetch(url,{
          method: "POST",
          mode: "no-cors",
          cache: "no-cache",
          headers: {
              // "Content-Type": "application/json; charset=utf-8",
              "Content-Type": "application/x-www-form-urlencoded",
          },
          body: params,
        })
        .then(response =>{
          console.log("ok")
          console.log(response)
          alert("メッセージを送信しました")
          this.$v.$reset()
          this.name = ''
          this.email = ''
          this.message = ''
          // location.reload();
          this.disabled = false
        })
        .catch(error => {
          console.log("ng")
          console.log(error.response)
          this.disabled = false
        });
      }
    }
  },

};

</script>
