# Fake Shop

Este repositório contém a automação de deploy da aplicação Fake Shop utilizando GitHub Actions, Docker e Kubernetes.

## Desafio
O objetivo deste projeto é otimizar o processo de deploy do Fake Shop, criando uma pipeline CI/CD no GitHub Actions. A pipeline automatiza os seguintes processos:

Criação da imagem Docker: A pipeline cria uma imagem Docker da aplicação.

Publicação no Docker Hub: A imagem Docker é publicada no Docker Hub.

Deploy no Kubernetes: Utilizando o kubectl, a aplicação é implantada no Kubernetes.

## Pré-requisitos
Antes de executar a pipeline, você precisa configurar o ambiente com algumas ferramentas e contas:

GitHub: Certifique-se de que você tem um repositório no GitHub.

Docker: Aplique suas credenciais para publicar a imagem no Docker Hub.

Digital Ocean: A conta Digital Ocean é necessária para o deploy no Kubernetes.

Kubernetes: O acesso ao seu cluster Kubernetes deve estar configurado, e você deve ter os arquivos de manifesto para o deploy.

## Estrutura do Projeto
.github/workflows/main.yml: O arquivo que contém a definição da pipeline CI/CD.

Dockerfile: A configuração para a criação da imagem Docker.

Kubernetes Manifests: Arquivos de manifesto para o deploy no Kubernetes.

Como Executar
### 1. Configuração do Docker Hub
Crie uma conta no Docker Hub.

Configure suas credenciais do Docker Hub como segredos no GitHub (por exemplo, DOCKER_USERNAME e DOCKER_PASSWORD).

### 2. Configuração do Kubernetes
Configure o acesso ao seu cluster Kubernetes utilizando o kubectl.

Armazene o contexto do Kubernetes como segredo no GitHub, se necessário (exemplo: KUBE_CONFIG).

### 3. Definição da Pipeline
O arquivo .github/workflows/ci-cd.yml contém a configuração da pipeline:

Build Docker Image: A pipeline começa criando a imagem Docker a partir do Dockerfile no repositório.

Push Docker Image: A imagem gerada é empurrada para o Docker Hub.

Deploy to Kubernetes: Após o push, o kubectl é utilizado para aplicar os manifestos de Kubernetes e realizar o deploy da aplicação.

### 4. Executando a Pipeline
A pipeline será executada automaticamente sempre que houver uma atualização no código. Qualquer alteração no repositório disparará a pipeline configurada em GitHub Actions.

Para visualizar o progresso ou verificar possíveis erros da pipeline, acesse a aba "Actions" no seu repositório no GitHub.

## Contribuições
Se você tiver sugestões ou melhorias para este projeto, sinta-se à vontade para abrir uma "issue" ou enviar um "pull request".

## Variáveis de Ambiente
DB_HOST	=> Host do banco de dados PostgreSQL.

DB_USER => Nome do usuário do banco de dados PostgreSQL.

DB_PASSWORD	=> Senha do usuário do banco de dados PostgreSQL.

DB_NAME	=>	Nome do banco de dados PostgreSQL.

DB_PORT	=>	Porta de conexão com o banco de dados PostgreSQL.
