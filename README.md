# Full Cycle 3.0 - Continuos Integration

- O que eh?

  - Eh o processo de integrar modificacoes do codebase de forma continua e automatizada,
    evitando assim errors humanos de verificacao, garantindo mais agilidade e seguranca no processo de
    desenvolvimento de um software.

- Principais processos
  - Execucao de testes
  - Linter
  - Verificacoes de qualidade de codigo
  - Verificacoes de seguranca
  - Geracao de artefatos prontos para o processo de deploy
  - Identificacao da proxima versao a ser gerada do software
  - Geracao de tags e release

- Status check
  - Eh a garantia que uma Pull Request nao podera ser mergeada ao repositorio sem antes
    ter passado pelo processo de CI ou mesmo o processo de Code Review.

- Ferramentas populares
  - Jenkins
  - Github Actions
  - Circle CI
  - AWS Code Build
  - Azure DevOps
  - Google Cloud Build
  - GitLab Pipelines / CI

- Vamos trabalhar com Github Actions
  - O que eh Github Actions
    - O Github Actions eh um automatizador de workflow de desenvolvimento de software.
      Ele utiliza ps principais eventos gerado pelo Github para que possamos executar
      tarefas dos mais variados tipos, incluindo processos de CI.

- Dinamica
  - Workflow
    - Sao conjunto de processos definidos por voce. Ex: Fazer o Build + rodar os testes de aplicacao
    - Eh possivel ter mais do que um workflow por repositorio
    - Definidos em arquivos `.yml` em: `.github/workflows`
    - Possui um ou mais `Jobs`
    - Eh iniciado baseado nos eventos do Github ou atraves de agendamento
  
  - Evento  
    `on:push`

  - Filtros
    ```
    branchs:
      - master
    ```
  - Ambiente 
    `runs-on: ubuntu`
    
  - Acoes
    ```
    steps:
      - uses: action/run-composer
      - run: npm run prod
    ```

  - Actions
    - Eh a acao que de fato sera executada em um Steps de um Job em um Workflow.
      Ela pode ser criada do zero ou ser reutilizada de actions pre-existentes.
  - Action pode ser desenvolvida:
    - JavaScript
    - Docker Image