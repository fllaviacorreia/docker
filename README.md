# Docker Compose - Setup Simples para Projetos Locais

## 🚀 Sobre este projeto

Configurar um ambiente de desenvolvimento local nunca deveria ser tão complicado. Se você já perdeu horas instalando bancos de dados, ajustando permissões e configurando serviços para rodar só para um projeto pessoal, então este repositório é para você.

Com este docker-compose.yml, você pode ter PostgreSQL, MySQL e Adminer rodando em poucos segundos, sem dor de cabeça. O foco aqui não é criar a solução mais robusta do mundo, mas sim ter algo funcional rapidamente para testes e desenvolvimento local.

## 🎯 Motivação

Trabalhar em projetos locais deveria ser simples, mas a realidade é bem diferente:

"Preciso testar algo no PostgreSQL, mas não quero instalar tudo de novo."

"MySQL está quebrado na minha máquina e não quero passar por toda aquela configuração de novo."

"Configurar usuários, permissões e conexões de banco sempre consome tempo demais."

"Só quero algo que funcione para focar no código!"

Este setup resolve esses problemas com um simples comando.

## 🛠 Tecnologias

    - Docker
    - Docker Compose
    - PostgreSQL
    - MySQL
    - Adminer

## 📦 Como Usar

### Clone o repositório:

    - HTTPS
    
```git clone https://github.com/fllaviacorreia/docker.git```

    - SSH

```git clone git@github.com:fllaviacorreia/docker.git```

    - Entre na pasta

```cd docker```


### Crie o arquivo .env com as configurações:

```cp .env.example .env```

(Edite o .env se quiser mudar alguma variável.)


### Suba os containers:

```docker compose up -d```


### Acesse os serviços:

Para criar bancos utilizando o Adminer, acesse http://localhost:{SUA_PORTA_DO_ENV} e faça login utilizando as credenciais configuradas no seu .env


### Quando terminar, derrube os containers:

```docker compose down```


## 🛠 Personalização

Quer adicionar mais serviços? É só editar o docker-compose.yml e incluir o que precisar, como Redis, MongoDB, ou até mesmo um backend Node.js.


## ⚡ Conclusão

Se você quer algo rápido e sem burocracia para seus projetos locais, este setup vai te ajudar a economizar tempo e sanidade. Pare de perder horas configurando tudo e volte a focar no código! 🚀