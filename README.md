# Terraform Hello World

## Introdução

O [Terraform](https://www.terraform.io/) é uma ferramenta para construir, alterar e controlar a infraestrutura de TI de forma segura e eficiente.

O Terraform pode gerenciar provedores de serviços existentes e populares como OpenStack, Azure, AWS, Digital Ocean, entre outros, bem como soluções internas personalizadas.

A infraestrutura que o Terraform pode gerenciar inclui componentes de baixo nível, como instâncias de computação, armazenamento e redes, bem como componentes de alto nível, como entradas DNS, recursos SaaS, etc.

Infraestrutura usada neste projeto:

![Infraestrutura](./images/app-helloworld-aws.png)

## Instalar o Terraform CLI (Command Line Interface)

1. Siga o passo-a-passo da página [https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).
    
2. Teste a instalação pelo terminal digitando o comando abaixo.

   ```
   terraform --version
   ```

## Clone o repositório que contém o código Terraform

1. Na sua máquina clone o repositório

   ```
   git clone https://github.com/kledsonhugo/app-helloworld-aws.git
   ```

## Configurar o acesso do Terraform à uma conta AWS

1. Dentro do diretório *terraform/*, crie o diretório *.aws/*.

2. Dentro do diretório *terraform/.aws/*, crie o arquivo *credentials*, inclua o conteúdo de exemplo abaixo e substitua pelas infos da sua conta AWS.
   
   ```
   [iac]
   aws_access_key_id = *********************
   aws_secret_access_key = *********************
   ```

3. Dentro do diretório *terraform/.aws/*, crie o arquivo *config* e inclua o conteúdo abaixo.

   ```
   [profile iac]
   region = us-east-1
   output = json
   ```

## Inicializar o Terraform

1. Abra o terminal, acesse o diretório "terraform" e execute o comando abaixo.

   ```
   terraform init
   ```

   - O texto em verde *Terraform has been successfully initialized!* será mostrado indicando que o Terraform inicializou corretamente.

## Criar os recursos de TI na AWS

1. Valide que não existem erros no código Terraform.

   ```
   terraform validate
   ```

2. Crie os recursos de TI na AWS.

   ```
   terraform apply
   ```

3. Verifique as informações dos recursos de TI criados na AWS.

   ```
   terraform show
   ```

## Validar pelo portal AWS os recursos de TI criados

1. Abra o portal AWS e valide a configuração dos recursos de TI criados (VPC, Internet Gateway, SubRede, Tabela de Roteamento, Security Group e EC2).

## Remover recursos de TI

1. Destruir os recursos de TI criados na AWS.

   ```
   terraform apply -destroy
   ```

# Terraform Hello World Vídeo

[![Terraform Hello World](https://github.com/kledsonhugo/app-helloworld-aws/blob/main/images/terraform-hello-world.png?raw=true)](https://www.youtube.com/watch?v=mGRTK2Isp3Y "Terraform Hello World")