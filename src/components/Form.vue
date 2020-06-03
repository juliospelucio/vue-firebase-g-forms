<template>
<v-container>
    <v-layout text-center wrap>
      <v-flex xs12>

        <v-form
          ref="form"
          class="mt-4"
          style="text-align:center;"
          action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSc7OgfVBSVJNJQMzQ8LH1xnUgi0tQvudopdyOB1pQraENV_ug/formResponse"
          target="_blank"
          method="POST"
          id="mG61Hd" >
          
          <v-text-field
            name="entry.293187218"
            id="name"
            prepend-inner-icon="mdi-account"
            v-model="name"
            label="Name"
            :rules="nameRules"
            outlined
            shaped
            hint="Enter Your Name"
            clearable
            required
            color="orange"
            type="text"
          ></v-text-field>

          <v-text-field
            name="entry.621278995"
            prepend-inner-icon="mdi-email"
            id="email"
            v-model="email"
            :rules="emailRules"      
            label="Email"
            hint="For example, abc@gmail.com"
            clearable
            required
            color="orange"
            type="text"
            outlined
            shaped
          ></v-text-field>

          <v-text-field
            name="entry.936819236"
            prepend-inner-icon="mdi-phone"
            id="phone"
            :v-model="{phone}"
            :rules="phoneRules"            
            label="Phone Number"
            hint="For example, 123 456 789"
            clearable
            required
            color="orange"
            prefix="+251 "
            outlined
            shaped
          ></v-text-field>

          <v-textarea
            name="entry.333762946"
            id="message"
            v-model="message"            
            label="Your Message"
            hint="Write Down Your Thoughts and we'll get to you"
            outlined
            shaped
            clearable
            auto-grow
            counter="400"
            color="orange"
            type="text"
          ></v-textarea>

          <v-btn
            class="mr-4 elevation-5"
            type="submit"
            @click="validate"
          >Submit</v-btn>

          <v-btn class="mr-4 elevation-5" @click="reset">Reset Form</v-btn>
        </v-form>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>

export default {

  name: "Form",

  data: () => ({

    name: "",
    email: "",
    message: "",
    phone: "",

    nameRules: [v => !!v || "Name is required"],
    phoneRules: [v => !!v || "Number is required"],
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
    ]
    
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    }
  }
};
</script>