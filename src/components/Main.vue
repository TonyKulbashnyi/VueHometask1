<template>
  <v-container>
    <div  v-show="!result">
    <v-row
      class="d-flex justify-center">
      <v-col cols="4">
        <form action="#">
          <v-text-field
            label="email"
            v-model="formData.email"
          />
          <v-text-field
            label="name"
            v-model="formData.name"
          />
          <v-text-field
            label="surname"
            v-model="formData.surname"
          />
          <v-text-field
            label="phone"
            v-model="formData.phone"
          />
          <v-divider />
          <v-btn
            class="primary my-3"
            @click="addGuest"
          >
            addGuest
          </v-btn>
           <v-text-field
            v-for="(guest, index) in formData.guests"
            :key="index"
            label="guest"
            v-model="formData.guests[index]"
            @dblclick="removeGuest(index)"
          />
        </form>
        <v-btn
            align="center"
            class="secondary my-3"
            @click="result = !result"
          >
            showResults
          </v-btn>
      </v-col>
    </v-row>
    </div>
    <div v-show="result">
      <v-row
        class="d-flex justify-center"
      >
        <v-col cols="6">
          <ol>
            <li>
              email: {{formData.email}}
            </li>
            <li>
              name: {{formData.name}}
            </li>
            <li>
              surname: {{formData.surname}}
            </li>
            <li>
              phone: {{formData.phone}}
            </li>
            <li>
              guests:
                <ol>
                  <li
                    v-for="(guest, index) in formData.guests"
                    :key="index"
                  >
                    {{guest}}
                  </li>
                </ol>
            </li>
          </ol>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
  export default {
    name: 'Main',

    data: () => ({
      formData: {
        email: '',
        name: '',
        surname: '',
        phone: '',
        guests: [
          ''
        ]
      },
      result: false
    }),
    methods: {
      addGuest: function () {
        this.formData.guests.push('')
      },
      removeGuest: function (index) {
        this.formData.guests.splice(index, 1)
      }
    }
  }
</script>
