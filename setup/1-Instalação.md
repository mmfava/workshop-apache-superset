
# 📘Tutorial de Instalação

Este guia foi elaborado para auxiliar usuários de todos os níveis a instalar o Apache Superset em sistemas Linux utilizando Docker. Para usuários Windows, recomenda-se o uso do **WSL** (*Windows Subsystem for Linux*) – veja as instruções em [WSL Windows](2-WSL.md).

> **Importante:**  
> - Execute os comandos na ordem apresentada no terminal.
> - Este tutorial utiliza Docker para simplificar a instalação, mas se você preferir instalar de outra forma, consulte a [documentação oficial do Superset](https://superset.apache.org/docs/installation).

---

## 1. Pré-requisitos

### 1.1 Docker e Docker Compose

Utilizaremos o Docker para isolar a instalação do Superset. Siga estes passos para instalar o Docker e o Docker Compose a partir dos repositórios oficiais do Ubuntu:

1. **Atualize os repositórios e instale dependências:**

```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg lsb-release
```

2. **Adicione a chave GPG e configure o repositório do Docker:**

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
 sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo tee /etc/apt/sources.list.d/docker.list > /dev/null <<EOF
deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable
EOF

```

3. **Instale o Docker e os componentes necessários:**

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

4. **(Opcional) Configure o Docker para ser executado sem `sudo`:**

```bash
sudo usermod -aG docker $USER
```

   > ⚠️ **Atenção:** Após executar este comando, reinicie sua sessão (logout/login ou reinicie o sistema) para que as permissões entrem em vigor.

> **Dica:** Caso prefira uma instalação gráfica, você pode optar pelo [Docker Desktop](https://docs.docker.com/desktop/).

### 1.2 Git

O Git será utilizado para clonar o repositório oficial do Superset. Instale-o com o seguinte comando:

```bash
sudo apt install git
```

> ⚠️ **Alternativa:** Baixe o Git pelo instalador em [git-scm.com](https://git-scm.com/downloads) se preferir.

---

## 2. Clonando o Repositório do Apache Superset

No terminal, clone o repositório oficial e acesse o diretório criado:

```bash
git clone --depth=1 https://github.com/apache/superset.git
cd superset
```

---

## 3. Ajustando a Versão do PostgreSQL

Por padrão, o arquivo `docker-compose.yml` pode estar configurado para utilizar a imagem `postgres:16`. Para garantir compatibilidade, a linha para `postgres:15` com a execução do comando:

```bash
sed -i 's/postgres:16/postgres:15/' docker-compose.yml
```

> **Por que fazer isso?**  
> Algumas versões podem apresentar incompatibilidades. Essa alteração ajuda a evitar problemas durante a inicialização dos containers.

---

## 4. Adicionando Suporte a Fontes de Dados Externas

Para conectar o Superset ao Google BigQuery (ou a outra fonte de dados), adicione a biblioteca "sqlalchemy-bigquery" nos *requirements* da ferramenta:

```bash
echo "sqlalchemy-bigquery" | sudo tee -a ./docker/requirements-local.txt
```

> **Nota:** Para adicionar outras bibliotecas ou conectar a outras fontes de dados, consulte a [documentação de bancos de dados do Superset](https://superset.apache.org/docs/configuration/databases).

---

## 5. Build e Inicialização do Superset 

### 5.1 Construindo os Containers

No diretório do repositório, construa as imagens Docker:

```bash
docker compose build
```

> **Dica:** Esse processo pode demorar alguns minutos, dependendo do seu sistema e conexão de internet.

### 5.2 Subindo os Containers

Após a construção, inicie os containers com:

```bash
docker compose up 
```

---

## 6. Acessando o Apache Superset

Abra o navegador e acesse a seguinte URL:

```
http://localhost:9000
```

**Credenciais padrão para login:**
- **Usuário:** `admin`
- **Senha:** `admin`

> **Recomendação:** Após o primeiro acesso, altere a senha padrão para aumentar a segurança.

### 6.1 Alterando as Credenciais

Para alterar a senha ou criar um novo usuário com privilégios de administrador:
- Navegue até **Settings > List Users**.
- Selecione o usuário desejado para editar ou crie um novo usuário conforme necessário.

---

## 7. Solução de Problemas

Caso encontre dificuldades durante a instalação, siga estes passos:

1. **Verifique os logs dos containers:**

   ```bash
   docker compose logs -f
   ```

2. **Confirme se a porta 9000 está livre:**

   ```bash
   sudo netstat -tulnp | grep ':9000'
   ```

   > Se a porta estiver em uso, ajuste-a no arquivo `docker-compose.yml`.

3. **Cheque as permissões do diretório do Superset:**

   ```bash
   sudo chown -R $USER:$USER ~/superset
   ```

4. **Recursos do Sistema:**

   - Certifique-se de ter pelo menos **4GB de RAM**.
   - Verifique se o Docker está rodando corretamente:

     ```bash
     sudo systemctl status docker
     ```

### Deu tudo errado? Calma!

Para seguir com o curso sem precisar esquentar a cabeça com instalações, você pode criar uma conta na plataforma [Preset](https://preset.io/), que oferece uma solução hospedada e gerenciada do Apache Superset! 

> Com o Preset, você tem acesso imediato a um ambiente configurado e otimizado para a criação de dashboards, sem a necessidade de lidar com a instalação, configuração ou manutenção da infraestrutura. O melhor é que para um único usuário ela é grátis 🤩.

---

## 📚 Referências

- [Superset Documentation - Docker Install](https://superset.apache.org/docs/installation/installing-superset-using-docker-compose)
- [Artigo do Yavar no Medium sobre Superset com Docker](https://medium.com/yavar/apache-superset-docker-installation-9e4cc58224fd)
