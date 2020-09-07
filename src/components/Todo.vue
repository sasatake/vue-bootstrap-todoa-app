<template>
  <div id="content">
    <b-jumbotron
      header="sample todo app"
      header-level="4"
      lead="with vue.js"
      bg-variant="light"
      class="text-center"
    >
      <b-button v-b-modal.todo-form variant="info">Create Task</b-button>
    </b-jumbotron>

    <b-container>
      <b-row>
        <b-table hover :items="items"></b-table>
      </b-row>
    </b-container>

    <b-modal
      id="todo-form"
      title="Add Task"
      ok-title="Add"
      v-on:ok="createTask"
    >
      <b-form-group label="Task">
        <b-form-input
          v-model="form.text"
          placeholder="Enter your task"
        ></b-form-input>
      </b-form-group>
      <b-form-group label="Start Date">
        <b-form-datepicker v-model="form.start_date"></b-form-datepicker>
      </b-form-group>
      <b-form-group label="End Date">
        <b-form-datepicker v-model="form.end_date"></b-form-datepicker>
      </b-form-group>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {},
  data() {
    return {
      form: {
        text: "",
        start_date: "",
        end_date: "",
      },
      items: [
        { text: "タスク", start_date: "2019-09-02", end_date: "2020-09-02" },
      ],
    };
  },
  methods: {
    createTask: function() {
      this.items.push({ ...this.form });
      this.clearForm();
    },
    clearForm: function() {
      this.form.text = "";
      this.form.start_date = "";
      this.form.end_date = "";
    },
  },
};
</script>

<style scoped></style>
