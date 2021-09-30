<template>
  <header>
    <h1>
      ToDo App
    </h1>
  </header>
  <main>
    <section>
      <label class="input-container container">
        <input
          v-model="inputField"
          type="text"
          placeholder="search or add"
        ><button @click="addTask">Add</button>
      </label>
    </section>
    <section class="container">
      <ul>
        <li
          v-for="(task, index) in tasks"
          :key="task"
          class="li-element"
        >
          {{ task }}<button
            class="remove"
            @click="removeTask(index)"
          >
            X
          </button>
        </li>
      </ul>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      tasks: [],
      inputField: '',
    };
  },
  methods: {
    addTask() {
      this.tasks.push(this.inputField);
      this.inputField = '';
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  font-family: 'Roboto';
}

h1 {
  width: 100%;
  padding: 2rem;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 2.5rem;
  text-align: center;
}
.container {
  width: 100%;
  margin: 0 auto;
  max-width: 475px;
}
.input-container {
  display: block;
  position: relative;
}
.input-container input {
  width: 475px;
  height: 40px;
  padding: 1rem;
  border: none;
  border-radius: 50px;
  background-color: #EAEAEA;
}
input::placeholder {
  text-transform: uppercase;
  color: #C2C2C2;
  font-size: 0.7rem;
  font-weight: bold;
}
input:focus {
  outline: none;
}
.input-container button {
  position: absolute;
  top: 0;
  right: 0;
  width: 100px;
  height: 100%;
  border: none;
  border-radius: 0 50px 50px 0;
  background-color: #c4c4c4;
  cursor: pointer;
  font: inherit;
  font-weight: bold;
  text-transform: uppercase;
  font-size: 0.8rem;
}
button:hover {
  background-color: #9e9e9e;
}
.container ul {
  margin: 2.5rem 0 0 0;
  list-style: none;
}
.li-element {
  position: relative;
  width: 475px;
  height: 40px;
  margin: 1rem 0;
  padding: 1rem 1.8rem;
  border: none;
  border-radius: 50px;
  background-color: #F2F2F2;
  text-align: left;
  line-height: 10px;
  text-transform: uppercase;
  font-size: 0.8rem;
}
.remove {
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  width: 40px;
  height: 40px;
  background-color: #c4c4c4;
  border-radius: 0 50px 50px 0;
  font: inherit;
  font-weight: bold;
  font-size: 0.8rem;
  text-transform: uppercase;
}

</style>
