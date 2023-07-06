<template>
  <table class="options__list">
    <tr>
      <th>Name:</th>
      <th>Value:</th>
    </tr>
    <tr v-for="option in options" :key="option">
      <td>{{ option.name }}</td>
      <td>{{ option.value }}</td>
    </tr>
  </table>
  <div class="options">
    <select
      class="options__select"
      placeholder="Select an option"
      v-model="selected"
      v-on:click="this.something = ''"
      required
    >
      <option value="" disabled selected hidden>Select your option</option>
      <option v-for="option in options" :key="option" :value="option">{{ option.name }}</option>
    </select>
    <form class="option__edit" v-on:submit="submitForm()">
      <h2>{{ selected ? selected.name : 'Nothing selected' }}</h2>
      <input
        type="text"
        class="option__value-input"
        v-model="something"
        :placeholder="selected ? selected.value : ''"
      />
      <button class="option__button-save">Save</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: null,
      something: null,
      options: [
        { name: 'Option 1', value: 'Value 1' },
        { name: 'Option 2', value: 'Value 2' },
        { name: 'Option 3', value: 'Value 3' },
        { name: 'Option 4', value: 'Value 4' },
        { name: 'Option 5', value: 'Value 5' },
        { name: 'Option 6', value: 'Value 6' },
        { name: 'Option 7', value: 'Value 7' },
        { name: 'Option 8', value: 'Value 8' },
        { name: 'Option 9', value: 'Value 9' },
        { name: 'Option 10', value: 'Value 10' },
        { name: 'Option 11', value: 'Value 11' },
        { name: 'Option 12', value: 'Value 12' },
        { name: 'Option 13', value: 'Value 13' },
        { name: 'Option 14', value: 'Value 14' },
        { name: 'Option 15', value: 'Value 15' },
        { name: 'Option 16', value: 'Value 16' },
        { name: 'Option 17', value: 'Value 17' },
        { name: 'Option 18', value: 'Value 18' },
        { name: 'Option 19', value: 'Value 19' },
        { name: 'Option 20', value: 'Value 20' }
      ]
    }
  },
  methods: {
    submitForm() {
      event.preventDefault()
      this.selected.value = this.something
      console.log(this.options)
      this.something = ''
    }
  }
}
</script>
