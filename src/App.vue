<script setup>
import InputComponent from "./components/InputComponent.vue";
</script>

<script>
export default {
  data() {
    return {
      config: {
        type: "default",
        placeholder: "Your name",
      },
    };
  },
};
</script>


<template>
  <!-- Defalut -->
  <p>Default</p>
  <InputComponent :config="config" :type="'default'" />

  <!-- Hover -->
  <p>Hover</p>
  <InputComponent :config="config" :type="'hover'" />

  <!-- Filled -->
  <p>Filled</p>
  <InputComponent :config="config" :type="'filled'" :value="'Michael Browk'" />

  <!-- Disabled -->
  <p>Disabled</p>
  <InputComponent :config="config" :type="'disabled'" :disabled="true" />

  <!-- Disabled Filled -->
  <p>Disabled Filled</p>
  <InputComponent
    :config="config"
    :type="'disabledFilled'"
    :disabled="true"
    :value="'Michael Browk'"
  />

  <!-- ReadOnly -->
  <p>ReadOnly</p>
  <InputComponent
    :config="config"
    :type="'ReadOnly'"
    :readOnly="true"
    :value="'Michael Browk'"
  />

  <!-- Error -->
  <p>Error</p>
  <InputComponent
    :config="config"
    :type="'error'"    
    :backgroundColor="'#f5c6cb'"
  />

  <!-- Error Filled -->
    <p>Error Filled</p>
    <InputComponent
      :config="config"
      :type="'errorFilled'"          
      :backgroundColor="'#f5c6cb'"
    />

  <!-- Success -->
  <p>Success</p>
  <InputComponent :config="config" :value="'Michael Browk'" :type="'success'" :backgroundColor="'#CBECD9'" :icon='`<i class="fa-solid fa-check"></i>`'/>

  <!-- Description -->
  <p>Description</p>
  <InputComponent :config="config" :type="'description'" :description="'Something to say to the user'" />

  <!-- Autofill -->
  <p>Autofill</p>
  <InputComponent :config="config" :type="'Autofill'" :backgroundColor="'#FFF5C0'" :icon='`<i class="fa-solid fa-check"></i>`' :value="'Michael Browk'"/>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap");
body {
  font-family: "Roboto", sans-serif;
}
</style>
