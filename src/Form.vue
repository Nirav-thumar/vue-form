<template>
  <p>{{ formData }}</p>
  <form @submit.prevent="handleFormSubmit">
    <div>
      <label for="name">Name : </label>
      <input type="text" id="name" v-model="formData.fullName" />
    </div>

    <div>
      <label for="email">Email : </label>
      <input type="email" id="email" v-model="formData.email" />
    </div>

    <div>
      <label for="dob">Birth Date : </label>
      <input type="date" id="dob" v-model="formData.dob" />
    </div>

    <div>
      <label for="password">Password : </label>
      <input type="password" id="password" v-model="formData.password" />
    </div>

    <div>
      <label for="message">Message : </label>
      <textarea id="message" cols="30" rows="2" v-model="formData.message"></textarea>
    </div>

    <div>
      <label for="houseRentAllowance">houseRentAllowance : </label>
      <input type="checkbox" id="houseRentAllowance" v-model="formData.houseRentAllowance" />
    </div>

    <div>
      <label for="driving">driving : </label>
      <input
        type="checkbox"
        id="driving"
        v-model="formData.driving"
        true-value="yes"
        flase-value="no"
      />
    </div>

    <div>
      <span>Hobbies : </span>
      <label for="cooking">cooking </label>
      <input type="checkbox" id="cooking" v-model="formData.hobbies" value="cooking" />

      <label for="reading">reading </label>
      <input type="checkbox" id="reading" v-model="formData.hobbies" value="reading" />

      <label for="gaming">gaming </label>
      <input type="checkbox" id="gaming" v-model="formData.hobbies" value="gaming" />
    </div>

    <div>
      <span>Gender : </span>
      <label for="Male">Male </label>
      <input type="radio" id="Male" v-model="formData.gender" value="male" />

      <label for="feMale">Female </label>
      <input type="radio" id="feMale" v-model="formData.gender" value="female" />
    </div>

    <div>
      <span>Job Post :</span>
      <select v-model="formData.jobPost">
        <option disabled value="" selected>Please select one</option>
        <option value="Vue js Developer">Vue js Developer</option>
        <option value="React js Developer">React js Developer</option>
        <option value="Angular js Developer">Angular js Developer</option>
      </select>
    </div>

    <div>
        <span>State :</span>
        <select v-model="formData.state">
            <option disabled value="">Please select one</option>
            <option :value="state.value" v-for="(state,index) in stateOption" :key="index">{{state.text}}</option>
        </select>
    </div>

    <div>
      <span>Job Location :</span>
      <select v-model="formData.jobLocation" multiple size=2>
        <option disabled  value="none" hidden selected>Please select atleast one</option>
        <option value="Banglore">Banglore</option>
        <option value="Rajkot">Rajkot</option>
        <option value="Pune">Pune</option>
      </select>
    </div>

    <div>
        <label for="fees">Fees : </label>
        <input type="text" id='fees' v-model.number="formData.fees">
    </div>

<p>{{formData.fees}}</p>
 

    <button type="submit">Submit</button>
  </form>
</template>
 
 
<script setup>
import { ref, reactive, computed } from 'vue'
const stateOption = ref([
    {text:"Gujrat",value:'Gujrat'},
    {text:"Goa",value:'Goa'},
    {text:"Maharastra",value:'Maharastra'},
    {text:"West Bengal",value:'West Bengal'},
    {text:"Uttar Pradesh",value:'Uttar Pradesh'},
    {text:"Jarkhand",value:'Jarkhand'},

])

function handleFormSubmit() {
  console.log('form submitted', formData)
}

const formData = reactive({
  fullName: '',
  email: '',
  dob:'',
  password: '',
  message: '',
  houseRentAllowance: 'true',
  driving: 'no',
  hobbies: [],
  gender: '',
  jobPost: '',
  state:'',
  jobLocation: [],
  fees:''
})
</script>
 
<style scoped>
</style>