<!DOCTYPE html>
<html lang=“pt-BR”>
<head>
<meta charset=“UTF-8”>
<title>Simulação da Copa do Mundo</title>
<style>
body {font-family: Arial, sans-serif; margin: 20px; }
h1 {color: darkgreen; }
button{ margin-top: 15px; padding: 10px }
.resultado { margin-top: 20px; font-weight: bold; }
</style>
</head>
<body>
<h1>Simulação da Copa do Mundo</h1>
<p>Probalididades iniciais (quanto maior, mais chance de vencer):</p>
<table id=“tabela”>
<tr><th>Seleção</th><th>Probabilidade(%)</th></tr>
<tr><td><input type=“text” value=”Brasil”></td><td><input type=“number”value=“25”></td></tr>
<tr><td><input type=“text” value=“Argentina”></td><input type=“number”value=“20”></td></tr>
<tr><td><input type=“text” value=“França”></td><input type=“number”value=“18”></td></tr>
<tr><td><input type=“text” value=“Alemanha”></td><input type=“number”value=“15”></td></tr>
<tr><td><input type=“text” value=“Portugal”></td><input type=“number”value=“50”></td></tr>
</table>

</button onclick=“simular()”>Simular Copa</button>

<div id=“resultado” class=“resultado”></div>

<script>
function escolherVencedor(selecao1, prob1, selecao2, prob2){
const total = prob1 + prob2;
const sorteio = Math random()*total;
return sorteio <prob1 ? selecao1 : selecao2;
}
function simular(){
const tabela = document.getElementByld(“tabela”);
let selecoes = [];

for(let i =1; < tabela.rows.length; i++) {
const nome = tabela.rows[i].cells[0].childre [0].value);
selecoes.push({nome.prob});
}
let frase = selecoes;
let texto = “”;


while(frase.length > 1){
texto +•”<h3>Fase com” + fase.length + “ seleções</h3>”;
let novaFase =[];
for (let i = 0; i < fase.length; i += 2) {
if (i+1 <fase.length) {
const vencedor= escolherVencedor(fase[i].nome, fase[i].prob,fase[i+1].nome,fase[i+1].prob);
texto += fase[i].nome+ ”vs” + fase[i+1].nome+”<b>”+ vencedor + “</b><br>”;
novaFase.push({nome: vencedor, prob: 50}); //probabilidade ajustada
} else {
novaFase.push(fase[i]); // caso de numero ímpar
}
}
fase = novaFase;
}
texto += “<h2>Campeão: “ +fase[0].nome +”</h2>”;
document.getElementByld(“resultado”).innerHTML = texto;
}
</script>
</body>
</html>
