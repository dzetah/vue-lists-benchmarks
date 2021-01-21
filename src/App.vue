<template>
  <div id="app">
    <h1>Current list: {{ selectedListName }}</h1>
    <div class="list-selector">
      <button @click="selectList('none')" :class="{ selected: isSelected('none') }">None</button>
      <button @click="selectList('basic')" :class="{ selected: isSelected('basic') }">Basic</button>
      <button @click="selectList('functional')" :class="{ selected: isSelected('functional') }">Functional</button>
      <button @click="selectList('dynamic')" :class="{ selected: isSelected('dynamic') }">Dynamic</button>
    </div>
    <component :is="selectedList" msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import BasicList from './components/basic-list/BasicList'
import FunctionalList from './components/functional-list/FunctionalList'
import DynamicList from './components/dynamic-list/DynamicList'

export default {
  name: 'App',
  data() {
    return {
      selectedListName: 'basic',
      lists: {
        basic: BasicList,
        functional: FunctionalList,
        dynamic: DynamicList
      }
    }
  },
  computed: {
    selectedList() {
      return this.lists[this.selectedListName]
    }
  },
  methods: {
    isSelected(name) {
      return this.selectedListName === name
    },
    selectList(name) {
      this.selectedListName = name
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.list-selector {
  display: flex;
  justify-content: center;
}
.list-selector > button {
  width: 100px;
  margin: 12px;
  border: none;
  border-radius: 4px;
}
.list-selector > button.selected {
  color: white;
  background-color: #2c3e50;
}

.list {
  max-height: 500px;
  overflow-y: scroll;
  border: 1px solid #2c3e50;
}
</style>
