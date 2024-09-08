# Sistema de Gerenciamento de Pacientes

O projeto foi feito com base no código disponibilizado pelo docente Claudio Ulisse na disciplina de Programação para Internet no Instituto Federal de Brasília.

Fonte do código original: [claulis/CRUD at avançado (github.com)](https://github.com/claulis/CRUD/tree/avançado)

## Funcionalidades

### 1. Listar Pacientes (`GET /pacientes`)
Esta funcionalidade exibe uma lista de todos os pacientes cadastrados no banco de dados. Cada paciente possui nome, idade, CPF, data e hora marcadas para consulta. Se não houver pacientes cadastrados, o sistema exibe uma mensagem informando que a lista está vazia.

### 2. Adicionar Paciente (`GET /pacientes/add` e `POST /pacientes/add`)
- **GET /pacientes/add**: Esta rota exibe um formulário para adicionar um novo paciente ao sistema. O formulário solicita os seguintes campos: nome, idade, CPF, data e hora marcadas para consulta.
  
- **POST /pacientes/add**: Após o preenchimento do formulário, esta rota recebe os dados e os valida. A validação do CPF é feita utilizando a biblioteca `cpf-cnpj-validator`. Se o CPF for válido, o paciente é adicionado ao banco de dados. Se o CPF for inválido ou houver algum erro, o sistema notifica o usuário e não realiza a adição.

### 3. Editar Paciente (`GET /pacientes/update` e `POST /pacientes/update`)
- **GET /pacientes/update**: Esta rota exibe uma lista de pacientes para que o usuário selecione qual deseja atualizar. Ao selecionar, o usuário pode editar as informações do paciente.
  
- **POST /pacientes/update**: Esta rota recebe os novos dados do paciente selecionado e realiza a validação do CPF. Se o CPF for válido, as informações do paciente são atualizadas no banco de dados. Caso contrário, o sistema exibe uma mensagem de erro.

### 4. Apagar Paciente (`GET /pacientes/delete` e `POST /pacientes/delete`)
- **GET /pacientes/delete**: Esta rota exibe um formulário para que o usuário insira o CPF do paciente que deseja remover.
  
- **POST /pacientes/delete**: Esta rota busca o paciente no banco de dados pelo CPF fornecido. Se o paciente for encontrado, ele é removido do banco de dados. Caso o CPF não corresponda a nenhum paciente, o sistema notifica o usuário sobre o erro.

## Validações
O sistema realiza a validação de CPF em várias operações, garantindo que apenas CPFs válidos sejam cadastrados ou editados. A validação é feita utilizando a biblioteca `cpf-cnpj-validator`, que é amplamente reconhecida para essa tarefa.

## Tratamento de Erros
O sistema lida com diferentes tipos de erros, como falhas de conexão ao banco de dados, CPFs inválidos e pacientes não encontrados. Em todos os casos, mensagens de erro adequadas são exibidas ao usuário para que ele possa corrigir os problemas.

## Tecnologias Utilizadas
- **Node.js**: Ambiente de execução para o JavaScript no servidor.
- **Express**: Framework web para Node.js, utilizado para criar o servidor e definir as rotas.
- **Sequelize**: ORM para Node.js, utilizado para interagir com o banco de dados.
- **EJS**: Motor de templates para renderizar as páginas HTML.
- **cpf-cnpj-validator**: Biblioteca para validação de CPFs.
