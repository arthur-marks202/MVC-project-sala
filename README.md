## 🧱 Model
O model é a parte do sistema que conversa direto com o meu banco de dados. Ele sabe buscar, salvar, atualizar ou excluir as informações quando for preciso. Pegando um exemplo do projeto, o arquivo professor.js cuida disso, deixando essa parte dos dados organizada e separada da lógica do resto da aplicação

## 🧠 Controller
Basicamente o controller é o cérebro por trás das ações. Ele vai compreender o que o usuário está tentando fazer (como cadastrar ou editar um professor), converar com o model para executar tal tarefa e então decide o que mostrar de volta. 

## 🌐 Endpoint
Agora o endpoint funciona como um caminho que leva até uma funcionalidade da sua aplicação. Por exemplo, quando alguém acessa esse caminho usando um método como (GET) ou (POST), o sistema vai entender que precisa executar uma ação, como mostrar dados, salvar um novo cadastro, atualizar algo ou excluir uma informação.
