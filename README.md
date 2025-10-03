<!DOCTYPE html>
<html>
<head><title>Sistema de Login</title>
<link rel="stylesheet" href="./css/cadastro.css">

</head>
<body>
<form>
 <div class="container">
<div class="cadastro-form">
  <fieldset>
  <p><h2>Cadastro</h2></p><!-- Esse é um titulo-->
  <input type="text" placeholder ="Nome"  >
  <input type="text" placeholder ="Endereço">
  <input type="tel" placeholder ="(99) 9999-9999"  >
  <input type="email" placeholder ="email" required>
  <input type="password" placeholder="senha" required>  
  <input type="password" placeholder="Confirmar senha" required>  


  <p><h2>Cadastro do Pet</h2></p>
  <input type="text" placeholder ="Nome do Pet">
  <div id="pets-container">
    <div class="pet-block">
  <label>Sexo do Pet</label>
  <label><input type="radio" id="macho" name="sexo" value="macho">Macho</label>
  <label><input type="radio" id="femea" name="sexo" value="femea">Femea</label>

  <label>Porte do Pet</label>
  <label><input type="radio" id="pequeno" name="porte" value="pequeno">Pequeno</label>
  <label><input type="radio" id="medio" name="porte" value="medio">medio</label>
  <label><input type="radio" id="grande" name="porte" value="medio">Grande</label>
  
  
  <select id="raca">
 <option value="disabled selected hidden>Escolha uma raça"></option>
<option value="raca-do-amor">Raça do amor</option>
<option value="labrador">Labrador</option>
<option value="poodle">Poodle</option>

  </select></br> </br> 
  <div id="pet"></div>
  <button type="submit">Cadastrar</button>
  <button type="reset">Limpar</button>
  <button type="button" onclick="adicionarPet()">&#10133Adicionar PET</button>

  </fieldset>
</div>
</div> 
</form>
</body>

<script>

 let contadorPets = 1;

 function adicionarPet() {
  const container = document.getElementById('pets-container');
  const pets = document.getElementById('pets');

  const blocos = container .getElementsByClassName ('pet-block');
  const ultimoBloco = blocos [blocos.length - 1];

  const novoBloco = ultimoBloco.cloneNode(true);
  novoBloco.querySelectorAll('input, select').forEach(el => {
    if (el.type !== 'radio' && el.type !== 'file') el.value ='';
    if (el.type !== 'radio'){
      el.name =el.name.replace(/_\d+$/,`_${contadorPets}`);
      el.checked = false;


    
   }
 });

 pets.appendChild(novoBloco);
 contadorPets++;

 }
</script>
</html>

