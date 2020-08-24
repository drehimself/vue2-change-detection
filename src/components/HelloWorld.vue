<template>
  <div class="hello">
    <h2>Object Change Detection</h2>
      <div>
        <button @click="addFieldToObject">Add field to Object</button>
        <button @click="deleteFieldFromObject">Delete field from Object</button>
        <button @click="useSetToAddField">Use Set to Add field</button>
      </div>
      <div class="mt">
        {{ personObject }}
      </div>

      <h2>Array Change Detection</h2>
      <div>
        <button @click="changeArrayUsingIndex">Change Array using index</button>
        <button @click="changeArrayLength">Change Array length</button>
        <button @click="pushToArray">Push to Array</button>
      </div>
      <div class="mt">
        {{ peopleArray }}
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      personObject: {
        name: 'Andre',
      },
      peopleArray: [
        'Andre', 'Bob', 'Sally'
      ]
    }
  },
  methods: {
    addFieldToObject() {
      this.personObject.age = 36
    },
    deleteFieldFromObject() {
      delete this.personObject.age
    },
    useSetToAddField() {
      this.$set(this.personObject, 'height', '6ft')
    },
    changeArrayUsingIndex() {
      this.peopleArray[0] = 'Aaron'
    },

    changeArrayLength() {
      this.peopleArray.length = 1
    },

    pushToArray() {
      this.peopleArray.push('William')
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mt {
  margin-top: 8px;
}

</style>
