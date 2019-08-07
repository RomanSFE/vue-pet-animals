<template>
  <div class="home">
    <div>
      <h2>Pet Animals App</h2>
      <p>Add Your Pets From This Button</p>
      <button @click="togglePetForm" class="btn btn-primary">Add Pet</button>

      <b-form @submit.prevent="handleSubmit" v-if="petForm">

      <b-form-group id="input-group-2" label="Pets Name:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="formData.name"
          required
          placeholder="Enter name"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="species:" label-for="input-3">
        <b-form-select
          id="input-3"
          type="text"
          v-model="formData.species"
          :options="['cats', 'dogs']"
          required
        ></b-form-select>
      </b-form-group>

      <b-form-group id="input-group-4" label="Pets Age:" label-for="input-4">
      <b-form-input
          id="input-4"
          type="number"
          v-model="formData.age"
          required
          placeholder="Enter age"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-5" label="Pets Gender:" label-for="input-5">
      <b-form-select
          id="input-5"
          type="text"
          v-model="formData.gender"
          :options="['Male', 'Female']"
          required
          placeholder="Enter Gender"
        ></b-form-select>
      </b-form-group>

      <b-form-group id="input-group-6" label="Pets Color:" label-for="input-6">
        <b-form-input
          id="input-6"
          type="text"
          v-model="formData.color"
          required
          placeholder="Enter Color"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-7" label="Pets Weight:" label-for="input-7">
        <b-form-input
          id="input-7"
          type="number"
          v-model="formData.weight"
          required
          placeholder="Enter Weight"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-8" label="Pets Location:" label-for="input-8">
        <b-form-input
          id="input-8"
          type="text"
          v-model="formData.location"
          required
          placeholder="Enter Location"
        ></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import {mapActions} from 'vuex'

export default {
  name: 'home',
  data(){
    return{
      petForm: false,
      formData: {
        name: '',
        age: 0,
        gender: null,
        color: '',
        weight: '',
        location: '',
        species: null
      }
    }
  },
  methods: {
    ...mapActions([
      'addPet'
    ]),
    togglePetForm(){
      this.petForm = !this.petForm
    },
    handleSubmit() {
      const {species, name, age, gender, color, weight, location} = this.formData
      const payload = {
        species,
        pet: {
          name,
          age,
          gender,
          color,
          weight,
          location
        }
      }
      this.addPet(payload)

    //for reset
      this.formData = {
        name: '',
        age: 0,
        gender: null,
        species: null,
        color: '',
        weight: '',
        location: ''
      }
    }
  }
}
</script>

<style lang="css">
  .home p {
    color: #fb7575;
    font-weight: 500;
    font-size: 18px;
}

.home h2 {
    color: #38d888;
    font-weight: 700;
}
</style>
