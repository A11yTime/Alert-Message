<template>
  <div class="border">
    <h3>Role alert implementation for screen reader</h3>
    <div>
        <button class="button primary" @click="buttonClicked('Primary')">Primary <span aria-hidden="true" >Button</span></button>
        <button class="button secondary" @click="buttonClicked('Secondary')">Secondary <span aria-hidden="true">Button</span></button>
        <button class="button tertiary" @click="buttonClicked('Tertiary')">Tertiary <span aria-hidden="true">Button</span></button>
        <p v-if="clickedButton" role="alert">You clicked the {{ clickedButton }} button.</p>
    </div>
  </div>
</template>
<script>
export default{
    data(){
        return {
            clickedButton: ''
        }
    },
    methods: {
      buttonClicked(type) {
        this.clickedButton = type;
      }
    }
}
</script>
<style scoped>
  .border {
    background-color: rgb(218, 245, 248);
    padding: 10px;
    margin: 20px;
  }
.button {
  display: inline-block;
  padding: 10px 20px;
  margin: 5px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  transition: background-color 0.3s;
}
.primary {
  background-color: #007bff;
  color: #fff;
}
.secondary {
  background-color: #6c757d;
  color: #fff;
}
.tertiary {
  background-color: #f8f9fa;
  color: #212529;
  border: 1px solid #ccc;
}
</style>