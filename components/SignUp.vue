<template>
  <form>
  
    <label> email</label>
    <input type="email" required v-model="email"/>
    
    <label> pass</label>
    <input type="password" required v-model="pass"/>
  
    <label> Role </label>
    <select v-model ="role">
      <option value = "developer"> Web Deweloper </option>
      <option value = "designer"> Web Designer </option>
    </select>

    <div class = "terms">
      <input type = "checkbox" required v-model = "terms">
      <label> Akceptujac ten warunek oddajesz mi swoje antenki helium </label>
    </div>

    <label> Skills: </label>
    <input type = "text" v-model="tempSkill" @keyup.alt="addSkill">
    <div v-for="skill in skills" :key="skill" class = "pill">
      {{skill}}
    </div>

    <div>
      <input type = "checkbox" required v-model = "names" value = "Radke">
      <label> Radke </label>
    </div>

    <div>
      <input type = "checkbox" required v-model = "names" value = "Szymi">
      <label> Szymi </label>
    </div>

    <div>
      <input type = "checkbox" required v-model = "names" value = "Monke">
      <label> Monke </label>
    </div>

  </form>

<p> Email: {{email}}</p>

<p> Pass: {{pass}}</p>

<p> Role: {{role}}</p>

<p> Terms: {{terms}}</p>

<p> Names: {{names}}</p>

</template>


<script>
export default {
  data() {
    return {
      email: '',
      pass: '',
      role: '',
      terms: false,
      names: [],
      tempSkill: '',
      skills: []
    }
  },
  methods: {
    addSkill(e) {
      if (e.key == ',' && this.tempSkill) {
        this.skills.push(this.tempSkill);
        this.tempSkill = '';
      }
    }
  }
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
}
</style>