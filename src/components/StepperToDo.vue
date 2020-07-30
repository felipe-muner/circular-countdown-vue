<template>
  <div>
    <v-container>
      <v-alert type="error" v-show="showAlertError">
        I'm an error alert.
      </v-alert>
      <v-stepper v-model="e6" vertical>
        <v-stepper-step :complete="e6 > 1" step="">
          Select an app
          <small>Summarize if needed</small>
        </v-stepper-step>

        <v-stepper-content step="1">
          <v-card color="grey lighten-1" class="mb-12" height="200px">
            <v-container>
              <v-row>
                <v-col cols="12" md="4">
                  <v-text-field
                    v-model="formOne.fieldOne"
                    label="Write here to validate"
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
          <v-btn
            color="primary"
            :disabled="!formOne.fieldOne"
            @click="validateStep1"
            >Continue</v-btn
          >
          <v-btn text>Cancel</v-btn>
        </v-stepper-content>

        <v-stepper-step :complete="e6 > 2" step=""
          >Configure analytics for this app</v-stepper-step
        >

        <v-stepper-content step="2">
          <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
          <v-btn color="primary" @click="e6 = 3">Continue</v-btn>
          <v-btn text @click="e6--">Cancel</v-btn>
        </v-stepper-content>

        <v-stepper-step :complete="e6 > 3" step=""
          >Select an ad format and name ad unit</v-stepper-step
        >

        <v-stepper-content step="3">
          <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
          <v-btn color="primary" @click="e6 = 4">Continue</v-btn>
          <v-btn text>Cancel</v-btn>
        </v-stepper-content>

        <v-stepper-step step="">View setup instructions</v-stepper-step>
        <v-stepper-content step="4">
          <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
          <v-btn color="primary" @click="e6 = 1">Continue</v-btn>
          <v-btn text>Cancel</v-btn>
        </v-stepper-content>
      </v-stepper>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      e6: 1,
      formOne: {
        fieldOne: "",
      },
      showAlertError: false,
    };
  },
  methods: {
    validateStep1() {
      if ("" !== this.formOne.fieldOne) {
        this.showAlertError = false;
        this.e6++;
      } else {
        this.showAlertError = true;
        alert("please fill the form before go ahead");
      }
    },
    validateStep2() {},
  },
};
</script>

<style>
.v-stepper__wrapper {
  height: auto !important;
}
</style>
