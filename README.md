# 🎟️ Documentação do Projeto Ingressos na Federal

Seja bem-vindo(a) à documentação pública do sistema de ingressos do IFSP Cubatão. Originalmente esse projeto foi iniciado por [Leonardo](https://github.com/oleonardosilva) e [Gustavo](https://github.com/gustavofg1pontes), ambos ex-diretores de informática do Grêmio Estudantil (2023-2025).

Esse projeto viabiliza a organização de eventos como a **Festa JunIF** e o **HallowIF**, que, com o apoio da comunidade interna e externa, arrecadam fundos para ações estudantis. O sistema permite o cadastro, a organização e a compra de ingressos por uma plataforma web segura.

> O código está disponível em dois repositórios:
> 
> - [tickets-api (backend)](https://github.com/ifspcbt-devspace/tickets-api)
>     
> - [ifsp-eventos-web (frontend)](https://github.com/ifspcbt-devspace/ifsp-eventos-web)
>     


## 💡 Objetivo da Documentação

Este material foi criado para orientar novos colaboradores — especialmente os alunos do IFSP — a entender e manter o projeto ativo, evitando seu abandono e promovendo a continuidade da solução como ferramenta oficial de eventos estudantis.


## 🚧 Tecnologias Utilizadas

- [Docker](https://docs.docker.com/get-started/) — Criação e execução dos serviços em containers
    
- [Spring Boot](https://spring.io/projects/spring-boot) — Framework Java para o backend
    
- [Gradle](https://docs.gradle.org/current/userguide/userguide.html) — Ferramenta de build da API
    
- [Next.js](https://nextjs.org/docs) — Framework React para o frontend
    
- [PostgreSQL](https://www.postgresql.org/docs/) — Banco de dados relacional
    
- [GitHub Actions](https://docs.github.com/actions) — Integração contínua e deploy automatizado
    
- [GitHub Container Registry (GHCR)](https://docs.github.com/packages/working-with-a-github-packages-registry/working-with-the-container-registry) — Repositório de imagens Docker
    
- [Observabilidade com Prometheus e Grafana](https://grafana.com/docs/grafana/latest/) — Monitoramento do sistema (já configurado no backend)
    


## ▶️ Como Executar o Projeto Localmente

### 1. Clonar os repositórios

```bash
git clone https://github.com/ifspcbt-devspace/tickets-api
git clone https://github.com/ifspcbt-devspace/ifsp-eventos-web
```


### 2. Criar rede Docker

Antes de subir qualquer container, crie a rede que será compartilhada entre os serviços:

```bash
docker network create ifspcbt
```


### 3. Executar o Backend (`tickets-api`)

A API pode ser executada de duas formas:

#### ✅ Forma recomendada: via `docker-compose.local.yml` (para desenvolvimento)

Essa opção permite rodar o backend localmente e inclui o PostgreSQL e os containers de observabilidade (Prometheus, Grafana etc).

```bash
cd tickets-api/observability
docker compose up -d
cd ..
# Execute sem o '--build' caso não tenha sido feita alguma alteração
docker compose -f docker-compose.local.yml up -d --build
```

> ⚠️ **Importante:** Sempre execute com os containers de observabilidade para evitar erros de conexão no console.


### 4. Executar o Frontend (`ifsp-eventos-web`)

> **⚠️ Atenção:** o frontend **não precisa** ser executado com Docker em ambiente local. Utilize Node.js diretamente. Além disso, não esqueça de configurar no .env as variáveis de ambiente. Para mais informações consulte o readme do projeto.

```bash
cd ifsp-eventos-web
npm install
npm run dev
```

> A aplicação será iniciada em `http://localhost:3000`.


## 🤝 Como Contribuir

1. Faça um fork do repositório
    
2. Crie uma branch com o nome da sua funcionalidade ou correção
    
3. Ao concluir, envie um _Pull Request_ explicando claramente o que foi alterado
    
4. Sempre utilize a branch `dev` para desenvolvimento
    


## 📌 Notas Finais

- Leia os READMEs específicos de cada repositório para entender detalhes complementares de execução e configuração:
    
    - [tickets-api README](https://github.com/ifspcbt-devspace/tickets-api/blob/master/README.md)
        
    - [ifsp-eventos-web README](https://github.com/ifspcbt-devspace/ifsp-eventos-web/blob/main/README.md)
        

---

O sucesso desse projeto depende da continuidade dele por vocês. Cada contribuição ajuda a manter ativa uma ferramenta real que apoia eventos, cultura e integração estudantil.

**Vamos manter esse legado vivo!** 🧑‍💻💚
