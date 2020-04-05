<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" max-width="600">
      <template v-slot:activator="{ on }">
        <v-btn color="success" class="mt-4 mb-3" dark v-on="on"
          >Add Project</v-btn
        >
      </template>
      <v-card>
        <v-card-title class="headline">Add a new Project</v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-form>
                  <v-col cols="12">
                    <ValidationProvider
                      v-slot="{ errors }"
                      name="Name"
                      rules="required|max:10"
                    >
                      <v-text-field
                        v-model="name"
                        :counter="10"
                        :error-messages="errors"
                        label="Name"
                        required
                      ></v-text-field>
                    </ValidationProvider>
                    <v-text-field
                      label="Title*"
                      v-model="title"
                      prepend-icon="mdi-briefcase"
                      :rules="inputRules"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-textarea
                      prepend-icon="mdi-pencil"
                      name="input-7-1"
                      label="content"
                      hint="what the project is about"
                      auto-grow
                      dense
                      v-model="content"
                    >
                    </v-textarea>
                  </v-col>
                  <v-col cols="6">
                    <v-menu
                      v-model="momentMenu"
                      :close-on-content-click="false"
                      max-width="290"
                    >
                      <template v-slot:activator="{ on }">
                        <v-text-field
                          :value="momentDateFormat"
                          clearable
                          prepend-icon="mdi-calendar-clock"
                          label="Due date"
                          readonly
                          v-on="on"
                          @click:clear="date = null"
                        ></v-text-field>
                      </template>
                      <v-date-picker
                        v-model="date"
                        @change="momentMenu = false"
                      ></v-date-picker>
                    </v-menu>
                  </v-col>
                </v-form>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-btn class="ml-5 success mb-1" dark text @click="submit"
            >Add project</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
import moment from 'moment';
export default {
  data() {
    return {
      dialog: false,
      title: '',
      content: '',
      date: new Date().toISOString().substr(0, 10),
      momentMenu: false,
      inputRules: []
    };
  },
  computed: {
    momentDateFormat() {
      return this.date ? moment(this.date).format('dddd, MMMM Do YYYY') : '';
    }
  },
  methods: {
    submit() {
      this.dialog = false;
    }
  }
};
</script>

<style scoped>
.p-remove {
  padding: 0;
}
</style>
