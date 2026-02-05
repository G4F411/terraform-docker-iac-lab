# Terraform Docker — Infrastructure as Code (IaC) | Laboratório Local

## Visão Geral

Este repositório apresenta um laboratório prático de Infrastructure as Code (IaC)
utilizando Terraform com o provider Docker. O foco do projeto é a automação de
infraestrutura em ambiente local, sem dependência de provedores de nuvem, simulando
um fluxo real de trabalho utilizado por times de infraestrutura e DevOps.

O projeto demonstra domínio conceitual e prático de IaC, incluindo versionamento de
infraestrutura, gerenciamento de estado, ciclo de vida de recursos e aplicação de
boas práticas adotadas no mercado.

O ambiente foi executado em Linux utilizando WSL 2 no Windows, garantindo
compatibilidade com ambientes corporativos e aderência a práticas comuns da área.

---

## Objetivo do Projeto

Demonstrar, na prática, como o Terraform pode ser utilizado para:

* Provisionar infraestrutura de forma declarativa
* Gerenciar containers Docker como recursos de infraestrutura
* Garantir reprodutibilidade do ambiente
* Aplicar boas práticas de versionamento e segurança
* Simular um fluxo real de trabalho de infraestrutura automatizada

Este laboratório representa um cenário frequentemente utilizado como base em
ambientes corporativos antes da adoção de soluções em nuvem.

---

## Conceitos Aplicados

* Infrastructure as Code (IaC)
* Provisionamento declarativo
* Providers do Terraform
* Gerenciamento de estado (terraform.tfstate)
* Ciclo de vida de recursos (create / update / destroy)
* Versionamento com Git
* Boas práticas de segurança (uso de .gitignore)
* Docker como camada de infraestrutura

---

## Tecnologias Utilizadas

| Tecnologia     | Finalidade                                        |
| -------------- | ------------------------------------------------- |
| Terraform      | Provisionamento e gerenciamento da infraestrutura |
| Docker         | Execução de containers                            |
| Nginx          | Serviço web utilizado no container                |
| Git            | Controle de versão                                |
| GitHub         | Hospedagem e portfólio do projeto                 |
| WSL 2 (Ubuntu) | Ambiente Linux para execução local                |

---

## Arquitetura do Projeto

A infraestrutura criada por este projeto consiste em:

* Uma imagem Docker oficial do Nginx
* Um container Docker gerenciado pelo Terraform
* Mapeamento da porta 8080 do host para a porta 80 do container

Fluxo simplificado da arquitetura:

```
Terraform
   ↓
Docker Provider
   ↓
Container Nginx
   ↓
http://localhost:8080
```

---

## Estrutura do Repositório

```
terraform-docker-iac-lab/
├── main.tf                # Definição dos recursos Docker
├── provider.tf            # Configuração do provider Docker
├── .terraform.lock.hcl    # Controle de versão do provider
├── .gitignore             # Exclusão de arquivos sensíveis
└── README.md              # Documentação do projeto
```

---

## Como Executar o Projeto

### Pré-requisitos

* Docker instalado e em execução
* Terraform (versão 1.x ou superior)
* Git
* Ambiente Linux (Linux nativo ou WSL 2)

---

### Inicialização

Inicializar o Terraform e baixar os providers necessários:

```
terraform init
```

---

### Planejamento

Visualizar o plano de execução sem aplicar alterações:

```
terraform plan
```

---

### Aplicação da Infraestrutura

Criar os recursos definidos no código Terraform:

```
terraform apply
```

Após a confirmação, o container Nginx será iniciado automaticamente.

O serviço poderá ser acessado pelo navegador através do endereço:

```
http://localhost:8080
```

---

### Remoção da Infraestrutura

Destruir completamente os recursos provisionados:

```
terraform destroy
```

Este comando garante a limpeza total do ambiente, reforçando o conceito de
infraestrutura descartável e reproduzível.

---

## Boas Práticas Aplicadas

* O arquivo terraform.tfstate não é versionado
* Uso de .gitignore para evitar vazamento de informações sensíveis
* Separação clara de responsabilidades entre os arquivos Terraform
* Infraestrutura totalmente reproduzível
* Nenhuma dependência de serviços em nuvem ou cartão de crédito

---

## Possíveis Evoluções

* Utilização de variáveis (variables.tf)
* Definição de outputs (outputs.tf)
* Provisionamento de múltiplos containers
* Criação de redes Docker customizadas
* Persistência de dados utilizando volumes
* Migração do mesmo projeto para ambientes em nuvem (AWS ou Azure)

---

## 
Projeto desenvolvido como laboratório prático de Terraform, Docker e Infrastructure
as Code, com foco em aprendizado contínuo, portfólio profissional e preparação para
ambientes corporativos.
