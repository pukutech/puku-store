<template>
    <v-app>
        
        
       <v-btn
          fab
          bottom
          right
          color="pink"
          dark
          fixed
          @click="dialog1 = true"
        >
          <v-icon>add</v-icon>
        </v-btn>

        <v-dialog v-model="dialog1" width="800px">
         <v-toolbar dark class="primary" height="40px">
             <v-spacer></v-spacer>
              <v-btn  icon @click.native="dialog1 = false" dark>
                <v-icon >close</v-icon>
              </v-btn>
            </v-toolbar>
          <v-card>
            <v-card-title
              class="grey lighten-4 py-4 title"
            >
              Create contact
            </v-card-title>
            <v-container grid-list-sm class="pa-4">
              <v-layout row wrap>
                <v-flex xs12 align-center justify-space-between>
                  <v-layout align-center>
                    <v-avatar size="40px" class="mr-3">
                      <img
                        src=""
                        alt=""
                      >
                    </v-avatar>
                    <v-text-field                    
                    placeholder="Name"
                    ></v-text-field>
                  </v-layout>
                </v-flex>
                <v-flex xs6>
                  <v-text-field
                    prepend-icon="business"
                    placeholder="Company"
                  ></v-text-field>
                </v-flex>
                <v-flex xs6>
                  <v-text-field
                    placeholder="Job title"
                  ></v-text-field>
                </v-flex>
                <v-flex xs12>
                  <v-text-field
                    prepend-icon="mail"
                    placeholder="Email"
                  ></v-text-field>
                </v-flex>
                <v-flex xs12>
                  <v-text-field
                    type="tel"
                    prepend-icon="phone"
                    placeholder="(000) 000 - 0000"
                    mask="phone"
                  ></v-text-field>
                </v-flex>
                <v-flex xs12>
                  <v-text-field
                    prepend-icon="notes"
                    placeholder="Notes"
                  ></v-text-field>
                </v-flex>
              </v-layout>
            </v-container>
            <v-card-actions>
              <v-btn flat color="primary">More</v-btn>
              <v-spacer></v-spacer>
              <v-btn flat color="primary" @click="dialog= false">Cancel</v-btn>
              <v-btn flat @click="dialog= false">Save</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>

        
    </v-app>
</template>

<script>
export default {
    data() {
    return {
      dialog: false,
      dialog1: false,
      drawer_left: null,
      drawer: null,
      drawer:false,
      itemz:[],
    }
  }, 
  props: {
    source: String
  }
}
</script>

<style>

</style>
