# ESTADOS-SP

<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>Teste</title>
</head>

<body>
	<!--Importando Script Jquery-->
	<script type="text/javascript" src="https://code.jquery.com/jquery-3.2.1.min.js"></script>

	<!--Formulário-->
	<form>
		<label for="cep">CEP</label>
		<input id="cep" type="text" required/>
		<label for="logradouro">Logradouro</label>
		<input id="logradouro" type="text" required/>
		<label for="numero">Número</label>
		<input id="numero" type="text" />
		<label for="complemento">Complemento</label>
		<input id="complemento" type="text"/>
		<label for="bairro">Bairro</label>
		<input id="bairro" type="text" required/>
		<label for="uf">Estado</label>
		
    <select id="uf">
			<option value="SP">Adamantina</option>
			<option value="SP">Adolfo</option>
			<option value="SP">Aguaí</option>
			<option value="SP">Aguaí</option>
			<option value="SP">Aguas de lindoia</option>
      <option value="SP">Aguas de sao pedro</option>
      <option value="SP">Agudos</option>
      <option value="SP">Alambari</option>
      <option value="SP">Alfredo Marcondes</option>
      <option value="SP">Altair</option>
      <option value="SP">Altinopolis</option>
      <option value="SP">Alto Alegre</option>
      <option value="SP">Aluminio</option>
      <option value="SP">Alvares Florence</option>
      <option value="SP">Alvares Machado</option>
     	    
		>
		</select>
	</form>
	
	<script type="text/javascript">
		$("#cep").focusout(function(){
			//Início do Comando AJAX
			$.ajax({
				//O campo URL diz o caminho de onde virá os dados
				//É importante concatenar o valor digitado no CEP
				url: 'https://viacep.com.br/ws/'+$(this).val()+'/json/unicode/',
				//Aqui você deve preencher o tipo de dados que será lido,
				//no caso, estamos lendo JSON.
				dataType: 'json',
				//SUCESS é referente a função que será executada caso
				//ele consiga ler a fonte de dados com sucesso.
				//O parâmetro dentro da função se refere ao nome da variável
				//que você vai dar para ler esse objeto.
				success: function(resposta){
					//Agora basta definir os valores que você deseja preencher
					//automaticamente nos campos acima.
					$("#logradouro").val(resposta.logradouro);
					$("#complemento").val(resposta.complemento);
					$("#bairro").val(resposta.bairro);
					$("#cidade").val(resposta.localidade);
					$("#uf").val(resposta.uf);
          $("#estado").val(responta.localidade);
					//Vamos incluir para que o Número seja focado automaticamente
					//melhorando a experiência do usuário
					$("#numero").focus();
				}
			});
		});
	</script>
</body>
</html>
