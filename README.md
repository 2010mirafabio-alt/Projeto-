Sistema de Votação Eletrónica
Elementos do Grupo

Isaque - Nº Ba2857
Keibilyn - Nº Ba2927
Daniel - Nº Ba2835
Fábio - Nº Ba2853

Turma: 10º GPSI

Descrição do Projeto
Este projeto é um sistema de votação eletrónica executado no terminal, desenvolvido em JavaScript com Node.js. O sistema permite realizar eleições com três candidatos pré-definidos (Ana, Bruno e Carla), registando votos de múltiplos eleitores identificados por ID único.
O programa garante que:

Cada eleitor só pode votar uma vez
Apenas candidatos existentes podem receber votos
Em caso de empate é iniciada automaticamente uma 2ª volta
Os resultados são apresentados com percentagens


Estrutura de Ficheiros
📁 voting-system/
├── app.js
├── candidate.js
├── voteManager.js
├── validation.js
└── results.js

Responsabilidade de Cada Ficheiro

app.js — Ficheiro principal que controla todo o fluxo do programa: inicia a votação, apresenta os resultados e gere a 2ª volta em caso de empate
candidate.js — Gere a lista de candidatos, permite criar candidatos, adicionar votos, consultar a lista e resetar os votos para a 2ª volta
voteManager.js — Regista os votos dos eleitores e mantém a lista de quem já votou, impedindo votos duplicados
validation.js — Valida os dados introduzidos pelo utilizador, verificando se o ID do eleitor e o nome do candidato são válidos
results.js — Calcula o total de votos, as percentagens de cada candidato e determina o vencedor ou identifica empates


Principais Funções

criarCandidato(nome) — Cria um candidato com nome e votos iniciados a 0
adicionarVoto(candidato) — Incrementa o contador de votos de um candidato
resetarVotos() — Reinicia os votos de todos os candidatos para a 2ª volta
registarVoto(idEleitor, nomeCandidato) — Regista o voto de um eleitor, verificando se já votou e se o candidato existe
limparEleitores() — Limpa a lista de eleitores para a 2ª volta
validarDados(idEleitor, nomeCandidato) — Verifica se os dados introduzidos não estão vazios
eleitorJaVotou(idEleitor, eleitoresRegistrados) — Verifica se um eleitor já votou
totalVotos() — Retorna o número total de votos registados
calcularPercentagens() — Calcula a percentagem de votos de cada candidato com duas casas decimais
determinarVencedor() — Determina o vencedor ou deteta empate entre candidatos


Justificação das Decisões Tomadas
O código foi dividido em módulos separados para tornar o projeto mais organizado, legível e fácil de manter. Apesar de o trabalho estar dividido por partes, o grupo trabalhou em conjunto, ajudando-se mutuamente no desenvolvimento de cada módulo.
A verificação de votos duplicados foi implementada através de uma lista de IDs de eleitores que já votaram, garantindo a integridade da eleição.
A 2ª volta automática foi incluída para resolver situações de empate sem intervenção manual, tornando o sistema mais completo e justo.
A validação de dados evita que o programa entre em erro quando o utilizador introduz valores vazios ou inválidos.