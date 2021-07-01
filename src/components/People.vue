<template>
  <div class="container">
    <h1>Comentários</h1>
    <hr />
    <Form v-on:add-todo="addPerson"></Form>
    <div class="list-group">

    <h1>Tabela:</h1>
        <table class="table">
          <thead>
            <tr>
              <th scope="col">nome</th>
              <th scope="col">Email</th>
              <th scope="col">Deletar</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(person, index) in allPeople" v-bind:key="index">
              <td>{{ person.name }}</td>
              <td>{{ person.email }}</td>
              <div>
                <a href="#" title="Excluir" v-on:click.prevent="removePerson(index)">X</a>
            </div>
            </tr>
          </tbody>
        </table>

    </div>
    <hr />
  </div>
</template>

<script>
import Form from './Form';
export default {
  components: {
    Form
  },
  data() {
    return {
      people: []
    }
  },
  methods: {
    addPerson(person) {
      this.people.push(person);
    },
    removePerson(index) {
      this.people.splice(index, 1);
    }
  },
  computed: {
    allPeople(){
        return this.people.map(person => ({
            ...person,
            name: person.name+' '+person.lastname
        }))
    }
  },
}
</script>