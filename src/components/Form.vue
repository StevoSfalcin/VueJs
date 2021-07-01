<template>
  <div class="form-todo form-group">
  <p>
            <input placeholder="nome" type="text" name="name"
            class="form-control" v-model="name"/>
        </p>
        <p>
            <input placeholder="Sobrenome" type="text" name="lastname"
            class="form-control" v-model="lastname"/>
        </p>
        <p>
            <input placeholder="Email" type="email" name="email"
            class="form-control" v-model="email"/>
        </p>
        <p>
            <input placeholder="Telefone" type="number" name="phone"
            class="form-control" v-model="phone"/>
        </p>
        <p>
        <label>Tipo de pessoa</label>
        <select class="form-control" id="legalPerson" name="legalPerson">
            <option value="0">Fisica</option>
            <option value="1">Juridica</option>
        </select>
        </p>
        <p>
            <input placeholder="CPF" type="number" name="cpf"
            class="form-control" v-model="cpf"/>
        </p>
        <p>
            <input placeholder="CNPJ" type="number" name="cnpj"
            class="form-control" v-model="cnpj"/>
        </p>
        <button v-on:click="addPerson" type="submit" class="btn btn-primary">Cadastrar</button>
  </div>
</template>

<script>

   export default {
    data() {
      return {
        people: [],
                    name: '',
                    lastname: '',
                    email: '',
                    phone: '',
                    legalPerson: '',
                    cpf: '',
                    cnpj: ''
      }
    },
    methods: {
      addPerson() {
        this.$emit('add-todo', {
           name: this.name,
                lastname: this.lastname,
                email: this.email,
                phone: this.phone,
                legalPerson: this.legalPerson,
                cpf: this.cpf,
                cnpj: this.cnpj
        });
        this.name = '';
            this.lastname = '';
            this.email = '';
            this.phone = '';
            this.cpf = '';
            this.cnpj = '';
      }
    }
  }
</script>