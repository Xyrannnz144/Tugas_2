<!-- index.html -->
<template>
  <div>
    <h1 :class="{ 'header': true, 'header-large': isLarge }">Welcome to my page</h1>
    <p :style="{ 'color': textColor }">This is a paragraph of text</p>
    <input type="text" v-model="inputValue" @input="updateText">
    <button @click="toggleSize">Toggle header size</button>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLarge: false,
      textColor: 'black',
      inputValue: '',
      items: [
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' }
      ]
    }
  },
  methods: {
    updateText(event) {
      this.textColor = event.target.value;
    },
    toggleSize() {
      this.isLarge =!this.isLarge;
    }
  }
}
</script>