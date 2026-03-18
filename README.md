
# 🐳 Docker Compose - Setup Simples para Projetos Locais

## 🚀 Sobre este projeto

Configurar um ambiente de desenvolvimento local nunca deveria ser tão complicado. Se você já perdeu horas instalando bancos de dados, ajustando permissões e configurando serviços para rodar só para um projeto pessoal, então este repositório é para você.

Com este docker-compose.yml, você pode ter PostgreSQL, MySQL e Adminer rodando em poucos segundos, sem dor de cabeça. O foco aqui não é criar a solução mais robusta do mundo, mas sim ter algo funcional rapidamente para testes e desenvolvimento local.

---

## 🎯 Motivação

Trabalhar em projetos locais deveria ser simples, mas a realidade é bem diferente:

- "Preciso testar algo no PostgreSQL, mas não quero instalar tudo de novo."
- "MySQL está quebrado na minha máquina e não quero passar por toda aquela configuração de novo."
- "Configurar usuários, permissões e conexões de banco sempre consome tempo demais."
- "Só quero algo que funcione para focar no código!"

Este setup resolve esses problemas com um simples comando.

---

## 🛠 Tecnologias

- Docker
- Docker Compose
- PostgreSQL
- MySQL
- Adminer
- Maven 3.X
- Ant build
- Solr

---

## 📂 Estrutura dos arquivos

```
.
├── docker-compose.yml
├── .env
├── .env.example
└── README.md
```

---

## ⚙️ Configuração do ambiente

### 🔑 Variáveis de ambiente (`.env`)

```env
POSTGRES_USER=root
POSTGRES_PASSWORD=root

MYSQL_ROOT_PASSWORD=root

POSTGRES_PORT=5432
MYSQL_PORT=3306
ADMINER_PORT=8080
```

Se desejar, edite as portas ou credenciais no arquivo `.env` para evitar conflitos no seu ambiente local.

---

## 🚢 Como Usar

### 1️⃣ Clone o repositório:

- Usando HTTPS:

```bash
git clone https://github.com/fllaviacorreia/docker.git
```

- Usando SSH:

```bash
git clone git@github.com:fllaviacorreia/docker.git
```

- Entre na pasta:

```bash
cd docker
```

### 2️⃣ Crie o arquivo `.env`:

```bash
cp .env.example .env
```

(Edição opcional, ajuste se quiser mudar portas ou senhas.)

### 3️⃣ Suba os containers:

```bash
docker compose up -d
```

✔️ Isso irá subir:

- PostgreSQL na porta `${POSTGRES_PORT}`
- MySQL na porta `${MYSQL_PORT}`
- Adminer na porta `${ADMINER_PORT}`

---

## 🌐 Acesso ao Adminer

Acesse pelo navegador:

```
http://localhost:${ADMINER_PORT}
```

### 🏗️ Dados de acesso para conexão:

| Banco       | Sistema no Adminer    | Servidor  | Usuário | Senha  |
|--------------|------------------------|-----------|---------|--------|
| PostgreSQL   | PostgreSQL              | postgres  | root    | root   |
| MySQL        | MySQL / MariaDB         | mysql     | root    | root   |

> ⚠️ **Atenção:**  
No campo **"Servidor"**, utilize o nome do serviço do Docker (`postgres` ou `mysql`) e **não** `localhost` ou `127.0.0.1`, pois os containers estão em rede interna.

---

## 🗄️ Volumes persistentes

Os dados dos bancos são salvos nos volumes Docker:

- `postgres_data` → `/var/lib/postgresql/data`
- `mysql_data` → `/var/lib/mysql`

### 📦 Para remover containers e volumes (reset total):

```bash
docker compose down -v
```

---

## 🛠 Personalização

Quer adicionar mais serviços?  
Basta editar o `docker-compose.yml` e incluir outros serviços como:

- Redis
- MongoDB
- PHPMyAdmin
- Backends (Node, Laravel, etc.)

---

## ⚡ Conclusão

Se você quer algo rápido e sem burocracia para seus projetos locais, este setup vai te ajudar a economizar tempo e sanidade.

✨ Pare de perder horas configurando tudo e volte a focar no código! 🚀

---

## 📜 Licença

Este projeto está sob a licença MIT — sinta-se livre para usar, modificar e contribuir. 😄