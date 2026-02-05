Terraform Docker Infrastructure as Code (IaC) – Local Lab

Este repositório contém um laboratório prático de Infrastructure as Code (IaC) utilizando Terraform com o provider Docker, focado na automação de infraestrutura em ambiente local, sem dependência de cloud providers.

O projeto foi desenvolvido com o objetivo de demonstrar domínio conceitual e prático de IaC, incluindo versionamento de infraestrutura, controle de estado, ciclo de vida de recursos e boas práticas adotadas no mercado.

   Objetivo do Projeto

Demonstrar, na prática, como o Terraform pode ser utilizado para:

Provisionar infraestrutura de forma declarativa

Gerenciar containers Docker como recursos de infraestrutura

Garantir reprodutibilidade do ambiente

Aplicar boas práticas de versionamento e segurança

Simular um fluxo real de trabalho de infraestrutura automatizada

Este laboratório representa um cenário realista, frequentemente utilizado como base em ambientes corporativos antes da adoção de cloud.

 Conceitos Aplicados

Infrastructure as Code (IaC)

Provisionamento declarativo

Providers do Terraform

Gerenciamento de estado (terraform.tfstate)

Ciclo de vida de recursos (create / update / destroy)

Versionamento com Git

Boas práticas de segurança (uso de .gitignore)

Docker como camada de infraestrutura

   Tecnologias Utilizadas
Tecnologia	Finalidade
Terraform	Provisionamento e gerenciamento da infraestrutura
Docker	Execução dos containers
Nginx	Serviço web utilizado no container
Git	Controle de versão
GitHub	Hospedagem e portfólio

 Arquitetura do Projeto

A infraestrutura criada por este projeto consiste em:

Uma imagem Docker oficial do Nginx

Um container Docker gerenciado pelo Terraform

Porta 8080 do host mapeada para a porta 80 do container

Fluxo simplificado:

Terraform
   ↓
Docker Provider
   ↓
Container Nginx
   ↓
http://localhost:8080

  Estrutura do Repositório
terraform-docker-iac-lab/
├── main.tf                # Definição dos recursos (container Docker)
├── provider.tf            # Configuração do provider Docker
├── .terraform.lock.hcl    # Controle de versão do provider
├── .gitignore             # Exclusão de arquivos sensíveis
└── README.md              # Documentação do projeto

   Como Executar o Projeto
   Pré-requisitos

Docker instalado e em execução

Terraform instalado

Git instalado

   Inicialização

Inicializar o Terraform e baixar os providers:

terraform init

   Planejamento

Visualizar o plano de execução (sem aplicar alterações):

terraform plan

   Aplicação da Infraestrutura

Criar os recursos definidos:

terraform apply


Após a confirmação, o container Nginx será iniciado.

Acesse no navegador:

http://localhost:8080


  Remoção da Infraestrutura

Destruir completamente os recursos provisionados:

terraform destroy

Esse comando garante limpeza total do ambiente, reforçando o conceito de infraestrutura descartável.


   Boas Práticas Aplicadas

terraform.tfstate não é versionado

Uso de .gitignore para evitar vazamento de informações sensíveis

Separação clara de responsabilidades entre arquivos

Infraestrutura totalmente reproduzível

Nenhuma dependência de cloud ou cartão de crédito

   Possíveis Evoluções

Uso de variáveis (variables.tf)

Outputs (outputs.tf)

Múltiplos containers

Redes Docker customizadas

Persistência com volumes

Migração do mesmo projeto para AWS ou Azure

Projeto desenvolvido como laboratório prático de Terraform, Docker e Infrastructure as Code, com foco em aprendizado, portfólio e preparação para ambientes corporativos.
