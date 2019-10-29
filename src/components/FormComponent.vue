<template>
  <v-container>

    <v-card class="pa-4">
      <v-card-title>Sample Forms</v-card-title>

      <v-switch
              :input-value=items[0].active
              :label="`${items[0].id}`"
      ></v-switch>

      <v-switch
              color="amber"
              :input-value=items[1].active
              :label="`${items[1].id}`"
      ></v-switch>

      <v-checkbox
              v-model="checkbox"
              :label="`Checkbox 1: ${checkbox.toString()}`"
      ></v-checkbox>
      <v-radio-group v-model="radioGroup">
        <v-radio
                v-for="n in 3"
                :key="n"
                :label="`Radio ${n}`"
                :value="n"
        ></v-radio>
      </v-radio-group>


    </v-card>
  </v-container>
</template>

<script>
export default {

    data () {
      return {
        items: [
          { id: "id 001", active: true },
          { id: "id 002", active: false },
        ],
        checkbox: true,
        radioGroup: 1,
      }
    },

};

</script>
