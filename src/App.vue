<template>
  <div class="background">
    <div class="container grid-xs px-0 py-0 bg-gray s-rounded cartao">
      <div class="background-img ">
       <a class="text-light">Formulario </a>
       <a class="text-light">para  compra de Pacote de Adesivos</a>
       <p class="text-light bold">Pacote de Adesivos</p>   
       <img src="./assets/logo.svg"  class="img-responsive ... img-logo" alt="..."/>
       
         </div>
      <form @submit.prevent="addTodo(todo)">
        <div class="form-group">
          <div class="form-group">
            <label class="form-label text-dark bold">Quais adesivos?</label>
            <label class="form-checkbox form-inline">
              <input type="checkbox"   value="React" v-model="checkedNames"/><i class="form-icon text-dark"></i> React
            </label>
            <label class="form-checkbox form-inline">
              <input type="checkbox"  value="Vue" v-model="checkedNames"/><i class="form-icon text-dark"></i> Vue
            </label>
            <label class="form-checkbox form-inline">
              <input type="checkbox" value="Angular" v-model="checkedNames"/><i class="form-icon"></i
              >Angular
            </label>
          </div>
          <span c>Adesivos selecionados: {{ checkedNames }}</span>
          <select class="form-select " v-model="selected" >
            <option>Escolha a forma de pagamento:</option>
            <option>Cartão de credito</option>
            <option>Boleto Bancario</option>
            <option>Pix</option>
          </select>
          <span>Selecionado: {{ selected }}</span>
        </div>
        <p class="tile-subtitle bold">Quantidade:</p>
        <div class="input-group">
          <button class="btn btn-primary bold"  v-on:click="counter -= 1">-</button>
         <span class="text-dark padding">{{ counter }}</span>
          <button class="btn btn-primary bold" v-on:click="counter += 1">+</button>

        </div>
        <p class="tile-subtitle bold">Observações:</p>
        <div class="input-group">
          <textarea
            type="text"
            v-model="todo.description"
            class="form-input input-color"
            placeholder="Alguma duvida? Recado?"
          ></textarea>
        </div>
        <div class="btn-align ">
        <button class="btn btn-primary  input-group-btn  bold" v-on:click="greet">Enviar</button>
        </div>
  
      </form>
      
    </div>
  </div>
</template>

<script>

export default {
  
  name: "app",
  components: { },
   el: '...',
  data() {

    return {  counter: 0,selected: '',checkedNames: [], todos: [], todo: { checked: false } };
  },
  methods: {
    greet: function (event) {
      // `this` dentro de métodos aponta para a instância Vue
      alert('Adesivos selecionados: ' + this.checkedNames + '!' +"\n" +'Quantidade:' + this.counter 
       +"\n" + 'Forma de pagamento:'+ this.selected +"\n" + 'Observações:' + this.todo.description)
      // `event` é o evento DOM nativo
      if (event) {
        console.log(event.target.tagName)
      }
    }
    
  },
};
</script>

<style scoped>
.img-logo {

   max-width: 150px;
  margin: 0 auto;
  
    object-position: right;
}
.background{
  background-color:#8A2BE2;
  padding-top: 1rem;

}
.cartao{
  border-radius: 5px;
  box-shadow: 2px 9px 0px 6px rgb(56, 56, 56);;
}
.bold{
  font-weight: bold
}
.padding{
  padding-left: 10px;
  padding-right: 10px;
}
.btn-align{
  text-align: right;
  
}
.input-color{
  background-color: #DCE2E8;
}
.background-img{
 
  background-color:#2F3676;
  border-bottom-left-radius:40%;
  border-bottom-right-radius:40%;
}
</style>
