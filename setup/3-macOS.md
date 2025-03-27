# 📘Instalação no macOS

## 1. Pré-requisitos

### 1.1 Docker Desktop

Para usuários macOS, a maneira mais simples de instalar Docker é através do Docker Desktop:
1. Baixe o Docker Desktop através do site oficial: [Docker Desktop](https://docs.docker.com/desktop/mac/install/).
2. Após baixar, abra o arquivo e arraste o Docker para a pasta Applications.
3. Abra o Docker Desktop na pasta Applications e siga as instruções iniciais.

> ⚠️ **Dica:** Confirme que o Docker está rodando corretamente ao ver o ícone ativo na barra superior do sistema.

### 1.2 Git

Você precisará do Git para clonar o repositório oficial do Superset. Instale o Git através do Homebrew com o seguinte comando:

```bash
brew install git
```

> ⚠️ **Alternativa:** Baixe o Git pelo instalador em [git-scm.com](https://git-scm.com/downloads).

---

## 2. Clonando o Repositório do Apache Superset

No terminal, clone o repositório oficial e acesse o diretório criado:

```bash
git clone --depth=1 https://github.com/apache/superset.git
cd superset
```

---

## 3. Ajustando a Versão do PostgreSQL

Para garantir compatibilidade, ajuste a versão do PostgreSQL para `postgres:15` executando:

```bash
sed -i '' 's/postgres:16/postgres:15/' docker-compose.yml
```

---

## 4. Adicionando Suporte a Fontes de Dados Externas

Adicione a biblioteca "sqlalchemy-bigquery" aos requisitos locais:

```bash
echo "sqlalchemy-bigquery" >> ./docker/requirements-local.txt
```

---

## 5. Build e Inicialização do Superset

### 5.1 Construindo os Containers

Execute no terminal:

```bash
docker compose build
```

### 5.2 Subindo os Containers

Após o build, suba os containers:

```bash
docker compose up
```

---

## 6. Acessando o Apache Superset

Abra no navegador:

```
http://localhost:9000
```

**Credenciais padrão:**
- **Usuário:** `admin`
- **Senha:** `admin`

> ⚠️ Recomenda-se alterar a senha após o primeiro login.

---

## 7. Solução de Problemas

Caso tenha problemas, siga estas etapas:

1. **Verifique os logs:**

```bash
docker compose logs -f
```

2. **Confira se a porta 9000 está ocupada:**

```bash
lsof -i :9000
```

3. **Cheque permissões:**

```bash
sudo chown -R $(whoami):staff ~/superset
```

4. **Recursos mínimos recomendados:**
- Pelo menos **4GB de RAM** disponíveis.

### Deu tudo errado? Calma!

Para seguir com o curso sem precisar esquentar a cabeça com instalações, você pode criar uma conta na plataforma [Preset](https://preset.io/), que oferece uma solução hospedada e gerenciada do Apache Superset! 

> Com o Preset, você tem acesso imediato a um ambiente configurado e otimizado para a criação de dashboards, sem a necessidade de lidar com a instalação, configuração ou manutenção da infraestrutura. E para um único usuário ela é gratuita🤩.

---

## 📚 Referências

- [Superset Documentation - Docker Install](https://superset.apache.org/docs/installation/installing-superset-using-docker-compose)
- [Artigo do Yavar no Medium sobre Superset com Docker](https://medium.com/yavar/apache-superset-docker-installation-9e4cc58224fd)