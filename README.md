<h1 align="center">
    PostgreSQL - Environment
</h1>
<p align="center">
  <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/codedemonbr/PostgreSQL-Environment">

  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/codedemonbr/PostgreSQL-Environment">

  <a href="https://www.codacy.com/gh/codedemonbr/PostgreSQL-Environment/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=codedemonbr/PostgreSQL-Environment&amp;utm_campaign=Badge_Grade">
    <img src="https://app.codacy.com/project/badge/Grade/1f8b30a499ce412f98fa085a579998f5"/>
  </a>

  <img alt="Repository size" src="https://img.shields.io/github/repo-size/codedemonbr/PostgreSQL-Environment">

  <a href="https://github.com/codedemonbr/PostgreSQL-Environment/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/codedemonbr/PostgreSQL-Environment">
  </a>

  <a href="https://github.com/codedemonbr/PostgreSQL-Environment/issues">
    <img alt="Repository issues" src="https://img.shields.io/github/issues/codedemonbr/PostgreSQL-Environment">
  </a>

  <img alt="License" src="https://img.shields.io/github/license/codedemonbr/PostgreSQL-Environment">
</p>

<!-- Index -->

<p align="center">
  <a href="#rocket-technologies">Technologies</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#information_source-how-to-use">How To Use</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#card_index-my-contacts">My Contacts</a>
</p>

## :rocket: Technologies

This project is a challenge proposed by the company bhut. The following technologies were used:

-   [Docker](https://nodejs.org/en/);
-   [Docker Compose](https://www.npmjs.com/package/bcrypt);
-   [PostgreSQL](https://www.postgresql.org/);

## :information_source: How to use

### 1. Clone the repository;

```bash
    #Clone repository
    $ git clone git@github.com:codedemonbr/PostgreSQL-Environment.git

    #Go into the repository
    cd yourRepositoryHere

```

### 2. Edit the .yml file;

You may change password, port, email and others configs.

```yaml
version: "3"

services:
    # Container responsável pelo banco
    postgres-compose:
        image: postgres
        environment:
            POSTGRES_PASSWORD: "Postgres2021!"
        ports:
            - "15432:5432"
        volumes:
            - ~/Documents/PostgreSQL/data:/var/lib/postgresql/data
        networks:
            - postgres-compose-network

    # Container responsável pela administração gráfica (GUI)
    pgadmin-compose:
        image: dpage/pgadmin4
        environment:
            PGADMIN_DEFAULT_EMAIL: "codedemonbr@pm.me"
            PGADMIN_DEFAULT_PASSWORD: "PgAdmin2021!"
        ports:
            - "16543:80"
        depends_on:
            - postgres-compose
        networks:
            - postgres-compose-network

networks:
    postgres-compose-network:
        driver: bridge
```

### 3. Run docker-compose.

```zsh
docker-compose up -d
```

### 4. Get Container Address

```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' id_or_container_name

```

## :card_index: My contacts

```json
{
    "name": "Thiago Henrique dos Santos",
    "email": "henrique.thsantos.ths@gmail.com",
    "github": "https://github.com/codedemonbr",
    "linkedin": "www.linkedin.com/in/codedemonbr",
    "phones": [
        {
            "sp_phone": "+5511986082341"
        },
        {
            "ba_phone": "+5571997115946"
        }
    ]
}
```

---

Made with inner :fire: by Thiago Henrique dos Santos :wave: [Get in touch!](www.linkedin.com/in/codedemonbr)

[nodejs]: https://nodejs.org/
