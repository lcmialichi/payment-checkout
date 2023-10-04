<template>
    <v-card
      class="mx-auto my-12"
      max-width="680"
    >
    <v-container >
      <v-row no-gutters>
          <v-col v-for="input,index in inputs" v-bind:key="input" :cols="addCol(index) ? 6 : 0" class="ma-0 pa-0">
            <BasicInput
                v-if="input.status"
                :label=input.title
                :placeHolder=input.placeHolder
                size="100"
          
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
            {title: "name", label: "Nome", placeHolder:"Digite seu nome completo", status: this.name},
            {title: "email", label: "E-mail", placeHolder:"Digite seu email", status: this.email},
            {title: "phone", label: "Fone", placeHolder:"(00) x0000-0000", status: this.phone },
            {title: "cep", label: "CEP", placeHolder:"Digite seu cep", status: this.cep },
            {title: "address", label: "Endereço", placeHolder:"Digite seu endereco", status: this.address },
            {title: "number", label: "Número", placeHolder:"Número", status: this.number },
            {title: "complement", label: "Complemento", placeHolder:"Digite seu complemento", status: this.complement},
            {title: "neighborhood", label: "Bairro", placeHolder:"Digite seu bairro", status: this.neighborhood },
            {title: "city", label: "Cidade", placeHolder:"Digite sua cidade", status: this.city},
            {title: "state", label: "", placeHolder:"", status: this.state}
       ],
       multipleInLine: [
         2,3,5,6,9,10
       ]    
      }
    },
    methods: {
        addCol(index){
          return this.multipleInLine.includes(index)
        }
      
    },
    mounted(){
     this.inputs = Object.values(this.inputs.filter(function(item){
        return item.status
      }))
    }
  }
  </script>
  