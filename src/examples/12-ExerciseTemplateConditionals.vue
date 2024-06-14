<script>
export default {
  data() {
    return {
      editMode: false,
      displayText: 'You can edit me!!!',
      inputText: ''
    }
  },
  methods: {
    exitEditMode() {
      this.editMode = false;
      this.displayText = this.inputText;
    },
    saveChanges() {
      this.exitEditMode();
    }
  }
}
</script>


<template>
  <div id="app">
    <h1>Edit ME!</h1>

    <div class="editable-container" @click="editMode = true">
      <div class="editable-text" v-if="!editMode">
        <p>{{ displayText }}</p>
      </div>
      <input v-else type="text" v-model="inputText" @blur="exitEditMode" class="edit-input">
    </div>

    <button v-if="editMode" @click="saveChanges">Salvar</button>
  </div>
</template>



<style scoped>
h1{
  font-size: 45px;
  text-align: center;
  color: red;
}
.editable-text {
  cursor: pointer;
  padding: 10px;
  text-align: center;
  border: 1px solid #ccc;
  display: inline-block;
  margin-bottom: 10px;
}

.editable-container{
  text-align: center;
  padding-top: 20px;
}

</style>
