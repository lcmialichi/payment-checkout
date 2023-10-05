<template>
    <v-card
      class="mx-auto my-12"
      max-width="680"
    >
    <v-container >
      <v-row no-gutters>
          <v-col v-for="input,index in inputs" :key="input.title" :cols="addCol(index) ? 6 : 0" class="ma-0 pa-0">
            <BasicInput
                v-if="input.status"
                :id="index"
                :label=input.label
                :placeHolder=input.placeHolder
                size="100"
                @value="refreash"
            />
          </v-col>
      </v-row>
    </v-container>
    </v-card>
  </template>
  
  <script>
 import BasicInput from '@/components/Inputs/basicInput';
  export default {
    name: 'UserForm',
    components:{
        BasicInput
    },
    props: {
      name: {
        type: Boolean,
        default: false
      },
      email: {
        type: Boolean,
        default: false
      },
      phone: {
        type: Boolean,
        default: false
      },
      cep: {
        type: Boolean,
        default: false
      },
      address: {
        type: Boolean,
        default: false
      },
      number: {
        type: Boolean,
        default: false
      },
      complement: {
        type: Boolean,
        default: false
      },
      neighborhood: {
        type: Boolean,
        default: false
      },
      city: {
        type: Boolean,
        default: false
      },
      state: {
        type: Boolean,
        default: false
      },
    },
    data(){
      return {
          inputs: [
            {title: "name", label: "Nome", placeHolder:"Digite seu nome completo", status: this.name, value: ""},
            {title: "email", label: "E-mail", placeHolder:"Digite seu email", status: this.email, value: ""},
            {title: "phone", label: "Telefone", placeHolder:"(00) x0000-0000", status: this.phone , value: ""},
            {title: "cep", label: "CEP", placeHolder:"Digite seu cep", status: this.cep , value: ""},
            {title: "address", label: "Endereço", placeHolder:"Digite seu endereco", status: this.address , value: ""},
            {title: "number", label: "Número", placeHolder:"Número", status: this.number , value: ""},
            {title: "complement", label: "Complemento", placeHolder:"Digite seu complemento", status: this.complement, value: ""},
            {title: "neighborhood", label: "Bairro", placeHolder:"Digite seu bairro", status: this.neighborhood , value: ""},
            {title: "city", label: "Cidade", placeHolder:"Digite sua cidade", status: this.city, value: ""},
            {title: "state", label: "Estado", placeHolder:"", status: this.state, value: ""}
       ],
       multipleInLine: [
         2,3,5,6,8,9
       ]
      }
    },
    methods: {
        addCol(index){
          return this.multipleInLine.includes(index)
        },
        refreash(evt, id){
          this.inputs[id].value = evt
          this.$emit('inputs', this.inputs);
        }
    },
    mounted(){
     this.inputs = Object.values(
        this.inputs.filter(
          function(item){
            return item.status
          } 
        )
      )
    }
  }
  </script>
  