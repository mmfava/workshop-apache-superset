Este guia rápido vai te ajudar a configurar e executar o Superset na sua máquina local em **3 passos simples**. Note que é necessário ter o [Docker](https://www.docker.com), [Docker Compose](https://docs.docker.com/compose/), e [Git](https://git-scm.com/) instalados.

<div style="background-color: #D4AF47; padding: 10px; border-left: 6px solid #856404;">
  <strong>Atenção:</strong> Embora recomendemos usar o `Docker Compose` para um início rápido em um ambiente tipo sandbox e para outros casos de uso de desenvolvimento, <strong>não recomendamos esta configuração para produção</strong>. Para este propósito, consulte nossa página [Instalando no Kubernetes](/docs/installation/kubernetes/).
</div>

### 1. Obtenha o Superset

```bash
git clone https://github.com/apache/superset
```
### 2. Inicie a última versão oficial do Superset

```bash
# Entre no repositório que você acabou de clonar
$ cd superset

# Configure o repositório para o estado associado à última versão oficial
$ git checkout tags/4.1.2

# Inicie o Superset usando Docker Compose
$ docker compose -f docker-compose-image-tag.yml up
```

Isso pode levar um momento, pois o Docker Compose irá baixar as imagens dos containers necessárias e carregará alguns exemplos. Quando todos os containers forem baixados e a saída se estabilizar, você estará pronto para fazer login.

<div style="background-color: #D4AF47; padding: 10px; border-left: 6px solid #856404;">
  <strong>Atenção:</strong> Se você receber uma mensagem de erro como <strong>validating superset\docker-compose-image-tag.yml: services.superset-worker-beat.env_file.0</strong> must be a string, você precisa atualizar sua versão do <strong>docker-compose</strong>.
</div>

Observe que o `docker-compose` está em processo de depreciação e você deve usar `docker compose` em seu lugar.

### 3. Faça login no Superset

Agora acesse [http://localhost:8088](http://localhost:8088) e faça login com a conta padrão criada:

```bash
usuário: admin
senha: admin
```

#### 🎉 Parabéns! O Superset está agora funcionando na sua máquina! 🎉

### Finalizando

Quando terminar de usar o Superset, você pode parar e excluir como qualquer outro ambiente de container:

```bash
docker compose down
```

<div style="background-color: #D4AF47; padding: 10px; border-left: 6px solid #856404;">
  <strong>Atenção:</strong> Você pode usar o mesmo ambiente mais de uma vez, pois o Superset irá persistir os dados localmente. No entanto, certifique-se de parar adequadamente todos os processos executando o comando `stop` do Docker Compose. Fazendo isso, você pode evitar corrupção e/ou perda de dados.
</div>
