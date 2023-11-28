<h2><a href= "https://www.mackenzie.br">Universidade Presbiteriana Mackenzie</a></h2>
<h3><a href= "https://www.mackenzie.br/graduacao/sao-paulo-higienopolis/ciencia-da-computacao">Ciência da Computação</a></h3>

<font size="+12"><center>
<h1>Sistema de Presenças de uma Escola</h1>
</center></font>

**Conteúdo**

- [Autores](#autores)
- [Descrição do projeto](#descrição-do-projeto)
- [Análise de requisitos funcionais e não-funcionais](#análise-de-requisitos-funcionais-e-não-funcionais)
- [Diagrama de casos de uso](#diagrama-de-casos-de-uso)
- [Descrição dos casos de uso](#descrição-dos-casos-de-uso)
- [Diagrama de sequencia](#diagrama-de-sequencia)
- [Diagrama de classes](#diagrama-de-classes)
- [Diagrama de Componentes](#diagrama-de-componentes)
- [Decisões de arquitetura](#decisões-de-arquitetura)
- [Diagrama de implantação](#diagrama-de-implantação)
- [Referências](#referências)

# Autores

* Caio Alexandre V.B. de Andrade
* Diego Oliveira Aluizio
* Nicolas Fernandes Melnik

# Descrição do projeto

A tarefa de computar a presença dos alunos em uma escola ainda é feita totalmente no papel. Assim, é notório que nos dia atuais faz-se necessário a criação de um sistema que controle as presenças dos aalunos, de modo a facilitar a vida de todos (funcionários da escola e alunos). Deste modo, nosso grupo recebeu uma proposta para desenvolver este Sistema de Presenças e os nossos resultados estarão disponíveis neste repositório.

# Análise de requisitos funcionais e não-funcionais

<h3>Requisitos funcionais</h3>
<ol>
    <li>Colocar/Remover falta para os alunos que não responderem a chamada de presença.</li>
    <li>A chamada deve ocorrer todos os dias e em dois momentos (inicio do dia e após o intervalo).</li>
    <li>Gerar relatórios de faltas agrupados por data, ano do ensino, turma, professor, disciplina ou aluno.</li>
    <li>Avisar os pais/responsáveis por e-mail caso o comparecimento às aulas, dadas até o momento, estiverem abaixo de 80%.</li>
    <li>Se o aluno não comparecer em pelo menos 75% do total de aulas do ano será reprovado.</li>
    <li>Cada professor deve ter um username e uma senha para entrar no sistema.</li>
</ol>

<h3>Requisitos não-funcionais</h3>
<ol>
    <li>O sistema deve ser fácil e intuitivo.</li>
    <li>O sistema deve ser implementado em web: HTML, CSS e Java Script.</li>
    <li>O sistema deve utilizar um banco de dados.</li>
    <li>O sistema deve permitir acessos simultâneos.</li>
    <li>O sistema deve ser acessível a todos (fonte ajustável, etc).</li>
    <li>O sistema deve ser acessado de qualquer navegador web, incluindo dispositivos móveis.</li>
    <li>O sistema deve ser responsivo na web e mobile.</li>
    <li>Os relatórios gerados devem ser enviados para os responsáveis semestralmente.</li>
    <li>O username de cada professor deve conter 8 dígitos (cada professor tem uma identificação única).</li>
    <li>A senha de cada professor deve conter no minímo 8 dígitos alfanuméricos (verificar se a senha é forte).</li>
</ol>

# Diagrama de casos de uso

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/10d649d2-f1fa-4311-9aac-ad8e9cdbfcb3" width="700px" />
</div>

# Descrição dos casos de uso

## Caso de Uso: Efetuar Login

**Referência:** US_01

**Descrição Geral:** Esse caso de uso se trata do professor efetuar o login no sistema.

**Atores:** Professor.

**Pré-condição:** Professor deve receber suas credenciais da diretoria da escola.

**Pós-condição:** O professor consegue acessar o sistema.

**Fluxo Básico (Professor acessa o sistema):**
<ol>
    <li>O professor insere suas credenciais (username e senha);</li>
    <li>O sistema verifica as credenciais e autentica o professor;</li>
    <li>O professor entra no Sistema.</li>
</ol>

**Fluxo Alternativo (Professor não consegue acessar o sistema):**
<ol>
    <li>O professor insere suas credenciais (username e senha);</li>
    <li>O sistema não consegue verificar as credenciais informadas (bug ou erro de digitação);</li>
    <li>O Professor deve executar a ação novamente.</li>  
</ol>

## Caso de Uso: Alterar Senha

**Referência:** US_02

**Descrição Geral:** Esse caso de uso se trata do professor alterar sua senha.

**Atores:** Professor.

**Pré-condição:** O professor está autenticado no sistema.

**Pós-condição:** A senha do professor é alterada no sistema.

**Fluxo Básico (Professor troca de senha):**
<ol>
    <li>O professor acessa a opção de alterar senha no sistema;</li>
    <li>O professor fornece a senha atual e a nova senha;</li>
    <li>O sistema verifica a senha atual, atualiza a senha e confirma a alteração.</li>
</ol>

**Fluxo Alternativo (Professor não consegue trocar de senha):**
<ol>
    <li>O professor insere senha atual incorreta;</li>
    <li>O sistema exibe uma mensagem de erro;</li>
    <li>O Professor deve executar a ação novamente.</li>  
</ol>

## Caso de Uso: Fazer Chamada

**Referência:** US_03

**Descrição Geral:** Esse caso de uso se trata do professor realizar a chamada em uma turma.

**Atores:** Professor.

**Pré-condição:** O professor está logado no sistema.

**Pós-condição:** A chamada da turma é registrada no sistema.

**Fluxo Básico (Professor faz a chamada):**
<ol>
    <li>O professor seleciona a turma e a data para a chamada;</li>
    <li>O sistema exibe a lista de alunos da turma;</li>
    <li>O professor marca a presença/ausência de cada aluno;</li>
    <li>O sistema registra as informações de presença/ausência.</li>
</ol>

**Fluxo Alternativo (Aluno teve imprevisto e chegou após a chamada):**
<ol>
    <li>O professor seleciona a turma do aluno e a data;</li>
    <li>O sistema exibe a lista de alunos da turma, já com os dados salvos da chamada;</li>
    <li>O professor marca a presença deste aluno;</li>  
    <li>O sistema atualiza as informações de presença/ausência.</li>
</ol>

**Fluxo Alternativo (Professor marcou algo errado):**
<ol>
    <li>O professor seleciona a turma e a data;</li>
    <li>O sistema exibe a lista de alunos da turma, com a última alteração salva;</li>
    <li>O professor corrige o que precisa;</li>  
    <li>O sistema atualiza as informações de presença/ausência.</li>
</ol>

## Caso de Uso: Gerar Relatórios

**Referência:** US_04

**Descrição Geral:** Esse caso de uso se trata do professor gerar relatórios de presenças.

**Atores:** Professor.

**Pré-condição:** O professor está logado no sistema e fez a chamada.

**Pós-condição:** Os relatórios são gerados com as informações.

**Fluxo Básico (Professor gera relatórios):**
<ol>
    <li>Para confirmar que a chamada foi feita, professor clica no botão gerar relatório;</li>
    <li>O sistema gera relatórios de faltas agrupados por data, ano do ensino, turma, professor, disciplina ou aluno.</li>
</ol>

**Fluxo Alternativo (Professor não conseguiu gerar relatórios):**
<ol>
    <li>O professor clica no botão gerar relatório;</li>
    <li>O sistema não gera os relatórios por motivos de bug;</li>
    <li>O professor deve executar a ação novamente.</li>  
</ol>

## Caso de Uso: Enviar Notificação por E-mail aos Pais/Responsáveis

**Referência:** US_05

**Descrição Geral:** Este caso de uso trata da maneira pela qual a escola irá avisar os pais ou responsáveis caso o comparecimento do aluno às aulas, até o momento, esteja abaixo de 80%.

**Atores:** Professor, Pais/Responsáveis.

**Pré-condição:** Foram gerados relatórios de presença do aluno.

**Pós-condição:** As notificações são enviadas aos pais/responsáveis.

**Fluxo Básico (Notificação é enviada):**
<ol>
    <li>O sistema gera um relatório de comparecimento do aluno até o momento;</li>
    <li>O sistema calcula a porcentagem de comparecimento do aluno em relação ao número total de aulas ministradas;</li>
    <li>Envia a notificação se o resultado obtido for menor que 80%, para que os pais/responsáveis tomem as medidas necessárias.</li>
    <li>O sistema registra a data e hora do envio da notificação.</li>
</ol>

**Fluxo Alternativo (Erro no envio da notificação por E-mail):**
<ol>
    <li>Ocorreu um erro durante o envio da notificação por e-mail;</li>
    <li>O sistema registra o erro;</li>
    <li>O sistema tenta reenviar a notificação, até que seja enviado com sucesso.</li>  
</ol>

# Diagrama de sequencia

## Diagrama Sequencial do Caso de Uso US_01:

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/47ea40e6-3d2b-449f-b748-538bae492061" width="700px" />
</div>

## Diagrama Sequencial do Caso de Uso US_02:

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/44d5b746-ebff-4eda-96b1-5fdbba93aed9" width="700px" />
</div>

## Diagrama Sequencial do Caso de Uso US_03:

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/69f4205e-9707-41b5-bda3-8963e64b7de9" width="700px" />
</div>

## Diagrama Sequencial do Caso de Uso US_04:

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/ed528ed6-4bd1-43fc-bf12-90363ba3bb15" width="700px" />
</div>

## Diagrama Sequencial do Caso de Uso US_05:

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/eedb1fa3-6ee9-47af-b509-303395f87ab3" width="700px" />
</div>

# Diagrama de classes

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/5fc9ebbf-5a95-4dff-95a8-6fdf84bdcb89" width="700px" />
</div>

# Diagrama de Componentes

<div align="center">
<img src="https://github.com/profdscrodrigo/UML-Classroom-FCI/assets/117850844/cde611fc-f936-4a00-bb4b-bb51517c2a78" width="700px" />
</div>

# Decisões de arquitetura

## Tecnologias Utilizadas

O sistema de presenças foi desenvolvido utilizando as seguintes tecnologias:

- *Linguagem de Programação:* C# para o lado do servidor (.NET Core)
- *Banco de Dados:* MySQL para armazenar dados de presenças e usuários
- *Framework Web:* ASP.NET Core para simplificar o desenvolvimento do servidor web

## Estrutura do Projeto

A estrutura do projeto está organizada da seguinte forma:

- *src:* Contém os arquivos de código-fonte, incluindo modelos, controladores e rotas.
- *wwwroot:* Armazena os arquivos estáticos, como HTML, CSS e scripts JavaScript do lado do cliente.
- *config:* Contém configurações do banco de dados, autenticação e outras configurações do sistema.

## Integração de Banco de Dados

A interação com o banco de dados MySQL é feita por meio do Entity Framework Core (EF Core) para garantir a persistência dos dados de presenças, professores e alunos.

## Arquitetura Cliente-Servidor

O sistema segue uma arquitetura cliente-servidor. A comunicação entre o cliente e o servidor é baseada em requisições HTTP utilizando o protocolo RESTful.

## Segurança

Para garantir a segurança da aplicação, implementamos as seguintes medidas:

- *Autenticação e Autorização:* Cada professor tem um username e senha para acessar o sistema. A autenticação é realizada de forma segura.
- *Proteção contra Ataques:* Implementamos medidas contra ataques comuns, como validação de entrada para prevenir injeção de SQL.
- *HTTPS:* A aplicação utiliza HTTPS para criptografar a comunicação entre cliente e servidor.

## Escalabilidade e Desempenho

Considerações específicas foram feitas para garantir a escalabilidade e desempenho da aplicação:

- *Acessos Simultâneos:* O sistema foi projetado para suportar acessos simultâneos de vários professores.
- *Responsividade:* A interface do sistema é responsiva, funcionando de forma eficaz em navegadores web e dispositivos móveis.
- *Relatórios Semestrais:* Os relatórios de presenças são gerados e enviados aos responsáveis quando comparecimento às aulas, dadas até o momento, estiverem abaixo de 80%.

# Diagrama de implantação

*&lt;Diagrama para exibir o relacionamento de hardware e software no projeto&gt;*

# Referências

<ol>
    <li>Até o momento, só foram utilizados materiais disponibilizados pelo professor no moodle da disciplina.</li>
</ol>
