# Dashboard de Planejamento de Viagem — PWA para GitHub Pages

Este pacote transforma o dashboard em um PWA instalável para celular usando GitHub Pages.

## Arquivos do projeto

- `index.html`: dashboard principal.
- `manifest.webmanifest`: configura nome, ícones, tema e modo de abertura do app.
- `service-worker.js`: cria cache offline básico.
- `icons/icon-192.png` e `icons/icon-512.png`: ícones usados na instalação.
- `.nojekyll`: evita processamento Jekyll no GitHub Pages.

## Passo a passo para publicar no GitHub Pages

### 1. Crie um repositório no GitHub

1. Acesse GitHub.
2. Clique em **New repository**.
3. Sugestão de nome: `dashboard-viagem-pwa`.
4. Escolha **Public**.
5. Clique em **Create repository**.

### 2. Envie os arquivos

Opção simples pelo navegador:

1. Abra o repositório criado.
2. Clique em **Add file** > **Upload files**.
3. Envie todos os arquivos e pastas deste pacote:
   - `index.html`
   - `manifest.webmanifest`
   - `service-worker.js`
   - `.nojekyll`
   - pasta `icons/`
4. Clique em **Commit changes**.

### 3. Ative o GitHub Pages

1. No repositório, vá em **Settings**.
2. No menu lateral, clique em **Pages**.
3. Em **Build and deployment**, escolha:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`
   - **Folder**: `/root`
4. Clique em **Save**.

### 4. Acesse o link publicado

Depois de alguns minutos, o GitHub mostrará um link parecido com:

```text
https://seu-usuario.github.io/dashboard-viagem-pwa/
```

Abra esse link no celular.

### 5. Instale no celular

#### Android / Chrome

1. Abra o link no Chrome.
2. Toque nos três pontos do navegador.
3. Toque em **Adicionar à tela inicial** ou **Instalar app**.
4. Confirme.

#### iPhone / Safari

1. Abra o link no Safari.
2. Toque no botão de compartilhar.
3. Toque em **Adicionar à Tela de Início**.
4. Confirme.

## Observações importantes

- O PWA precisa estar publicado em HTTPS. O GitHub Pages já fornece HTTPS.
- Os dados do dashboard continuam salvos no navegador do usuário, via armazenamento local.
- Se você atualizar arquivos no GitHub, o app pode manter cache antigo por um tempo. Para forçar atualização, altere o nome do cache em `service-worker.js`, por exemplo de `dashboard-viagem-pwa-v1` para `dashboard-viagem-pwa-v2`.
- Para testar antes de publicar, rode localmente com um servidor, por exemplo:

```bash
python -m http.server 8000
```

Depois acesse:

```text
http://localhost:8000
```


## Nome e ícone do PWA

Ao instalar no celular, o app aparecerá com o nome **Viagens** e com ícone de avião.
