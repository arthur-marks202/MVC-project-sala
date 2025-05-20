## 🧱 Model
O model é a parte do sistema que conversa direto com o meu banco de dados. Ele sabe buscar, salvar, atualizar ou excluir as informações quando for preciso. Pegando um exemplo do projeto, o arquivo professor.js cuida disso, deixando essa parte dos dados organizada e separada da lógica do resto da aplicação

## 🧠 Controller
Basicamente o controller é o cérebro por trás das ações. Ele vai compreender o que o usuário está tentando fazer (como cadastrar ou editar um professor), converar com o model para executar tal tarefa e então decide o que mostrar de volta. 

## 🌐 Endpoint
Agora o endpoint funciona como um caminho que leva até uma funcionalidade da sua aplicação. Por exemplo, quando alguém acessa esse caminho usando um método como (GET) ou (POST), o sistema vai entender que precisa executar uma ação, como mostrar dados, salvar um novo cadastro, atualizar algo ou excluir uma informação.

# 🧠 Perguntas para medir aprendizado (responder neste README)
## ***Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto. 
Como o Model, o Controller e a View interagem entre si?***

A arquitetura MVC do projeto organiza o código em três camadas que se comunicam de forma clara. O **Model** é responsável por acessar e manipular os dados no banco, como buscar, inserir ou atualizar informações dos professores.

Já o **Controller** funciona como um intermediário: ele recebe as requisições do usuário, decide o que deve ser feito, aciona o Model quando necessário e encaminha os dados para a View.

A **View** é a parte visual do sistema, onde os dados são exibidos e os formulários são preenchidos pelo usuário. Quando alguém preenche um formulário, a View envia os dados para o Controller, que trata essa informação e repassa para o Model. Depois, o Controller traz os dados de volta e manda para a View apresentar ao usuário.

Esse ciclo permite que cada parte do sistema tenha uma responsabilidade clara, facilitando a manutenção e a organização do código.

## ***Como ocorre o envio e o recebimento de dados no formato JSON neste projeto?
Cite uma rota que responde em JSON e explique seu funcionamento.***

Atualmente, o projeto não envia nem recebe dados diretamente em formato JSON. As rotas estão configuradas para usar formulários HTML com o método `POST`, e as respostas são páginas renderizadas com `EJS`, ou seja, HTML gerado no servidor.

Mesmo assim, é possível criar rotas que retornem dados em JSON. Um exemplo seria:

```js
// No professorController
exports.apiList = async (req, res) => {
  const professores = await Professor.findAll();
  res.json(professores);
};
```
Essa rota pode ser registrada assim:

```js
router.get('/api/professores', professorController.apiList);
```
Quando acessamos /api/professores, o servidor retorna os dados dos professores em JSON. Esse tipo de rota é útil para conectar com sistemas externos ou usar JavaScript no front-end.

## ***Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador?
Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js?***

Usar HTML básico com formulários e tabelas é importante porque oferece uma forma simples, direta e eficaz de **organizar e manipular dados no navegador**, especialmente em aplicações web com foco administrativo ou educacional, como neste projeto.

Formulários permitem que o usuário envie informações (como nome e email) de forma intuitiva, enquanto as tabelas facilitam a visualização estruturada dos dados armazenados, como listas de professores ou alunos.

Mesmo com o avanço de frameworks modernos, essa estrutura continua sendo muito útil em projetos back-end com Node.js porque é **leve, de fácil manutenção e não exige um front-end separado** com React ou Vue, por exemplo. Isso reduz a complexidade, o tempo de desenvolvimento e é ideal para aplicações internas, sistemas de gestão ou MVPs.

Além disso, como o Node.js lida muito bem com **renderização server-side usando EJS**, essa abordagem garante integração fluida entre as rotas, os dados e a interface visual, sem sobrecarregar o servidor nem o navegador.

