<template>
  <div>
    <div id="title">
      <p>{{title}}</P>
    </div>
    <form action="https://desafio-node.vercel.app/api/ingressantes" method="post" enctype="application/x-www-form-urlencoded">
        <label>Nome</label><br>
        <input type="text" id="nome" name="nome" required="required"><br>
        
        <label>Curso</label><br>
        <select id="curso" name="curso" required="required">
          <option  disabled value=""></option>
          <option value="Matemática">Matemática</option>
          <option value="Letras">Letras</option>
          <option value="Geografia">Geografia</option>
        </select><br>
        
        <label>Estado</label><br>
        <select v-model="estado" id="estado" nome="estado" required="required">
          <option  disabled value=""></option>
          <option value="São Paulo">São Paulo</option>
          <option value="Rio de Janeiro">Rio de Janeiro</option>
          <option value="Minas Gerais">Minas Gerais</option>
        </select><br>
        
        <label>Cidades</label><br>
        <select id="cidade" nome="cidade" required="required">
          <option disabled value=""></option>
          <option v-if="estado == 'São Paulo'" value="Mogi das Cruzes">Mogi das Cruzes</option>
          <option v-if="estado == 'São Paulo'" value="Suzano">Suzano</option>
          <option v-if="estado == 'São Paulo'" value="Poá">Poá</option>
          <option v-if="estado == 'São Paulo'" value="Guararema">Guararema</option>
          <option v-if="estado == 'Rio de Janeiro'" value="Angra dos Reis">Angra dos Reis</option>
          <option v-if="estado == 'Rio de Janeiro'" value="Niterói">Niterói</option>
          <option v-if="estado == 'Rio de Janeiro'" value="Itaboraí">Itaboraí</option>
          <option v-if="estado == 'Minas Gerais'" value="Belo Horizonte">Belo Horizonte</option>
          <option v-if="estado == 'Minas Gerais'" value="Monte Azul">Monte Azul</option>
          <option v-if="estado == 'Minas Gerais'" value="Muzambinho">Muzambinho</option>
        </select><br>
        
        <button id="voltar" type="">Voltar</button>

        <button id="submit" type="Submit">Gravar</button>
    </form>      
  </div>
</template>

<script>
  export default{
    name:"Form",
    data(){
      return{
        title:"Cadastro de Ingressantes",
         estado:"",
      }
    }
   }
   
</script>

<style scoped>

div{
  width: 400px;
  height: 500px;
  background-color: #FFF;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 10px;
  border-style: solid;
  border-color: #5470af;
  border-width: 2px;
}

label{
  margin-left: 10px;
  font-size: 1em;
  text-align:end;
}

select{
   margin: 0;      
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  width: 375px;
  height: 50px;
  margin-bottom: 15px;
  margin-top: 2px;
  border-radius: 10px;
  background-color: #FFF;
  border-color: #5470af;
  border-width: 2px;

  align-items: center;
  cursor: pointer;

  background-image:
    linear-gradient(60deg, transparent 50%, rgb(255, 255, 255) 50%),
    linear-gradient(120deg, rgb(250, 250, 253) 50%, transparent 50%),
    linear-gradient(to right, #5470af, #5470af);
  background-position:
    calc(100% - 23px) calc(1em + 5px),
    calc(100% - 13px) calc(1em + 5px),
    99.4% 50%;
  background-size:
    10px 15px,
    10px 15px,
    42px 42px;
  background-repeat: no-repeat;
 
}





input{
  width: 370px;
  height: 50px;
  margin-bottom: 15px;
  margin-top: 2px;
  border-radius: 10px;
  background-color: #FFF;
  border-color: #5470af;
  border-width: 2px;
  
  
}

#title{
  background-color: #4473c5;
  height: 50px;
  width: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 5px;
  outline-color: #5470af;


}
p{
  color: #FFF;
	font-size: 1.4em;
}
#submit{
  height: 50px;
  width: 170px;
  position: relative;
  left: 85px;
  top: 20px;
  background-color:#6fda48;
  border-radius: 10px;
  border-width: 2px;
  border-color:#618c3d ;
  color: #FFF;
  font-size: 1.5em;
}
#voltar{
  height: 35px;
  width: 120px;
  position: relative;
  top: 25px;
  color: #FFF;
  font-size: 1em;
  background-color: #ffc003;
  border-radius: 10px;
  border-width: 2px;
  border-color: #bca251;
}
</style>
