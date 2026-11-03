# Guia Prático de Velas Comestíveis Gourmet – Landing Page

Landing Page de alta conversão para o **Guia Prático de Velas Comestíveis Gourmet**.

---

## 🚀 Configurações Rápidas no `index.html`

### 1. 📺 Vídeo do YouTube (Formato Vertical 9:16)
Abra o `index.html` e vá até a linha ~870 (seção `<script>`):
```javascript
const YOUTUBE_VIDEO_URL_OU_ID = 'SEU_VIDEO_ID';
```
Você pode colar tanto o **ID** quanto a **URL completa** do seu vídeo ou YouTube Shorts:
- `dQw4w9WgXcQ`
- `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
- `https://youtu.be/dQw4w9WgXcQ`
- `https://www.youtube.com/shorts/dQw4w9WgXcQ`

O script extrai o ID automaticamente e inicializa o player vertical com autoplay mudo, loop e controles limpos.

---

### 2. 📊 Pixel da Meta (Facebook Ads)
No `<head>` do `index.html` (linha ~25):
```javascript
const META_PIXEL_ID = 'SEU_PIXEL_ID_AQUI';
```
Basta substituir `'SEU_PIXEL_ID_AQUI'` pelo número do seu Pixel do Facebook (ex: `'123456789012345'`).
- A página já dispara o evento padrão `PageView`.
- Todos os cliques nos botões de compra disparam automaticamente o evento `InitiateCheckout` com o valor de R$ 37,00.

---

### 3. ⏱️ Delay de 4 Minutos no Botão Abaixo do Vídeo
- O botão abaixo do vídeo fica oculto nos primeiros **4 minutos (240 segundos)** para garantir a retenção da VSL.
- **Como testar sem esperar os 4 minutos:**
  Basta abrir a página no navegador adicionando `?teste` no final da URL:
  ```
  index.html?teste
  ```
- O navegador também grava no `localStorage` que o usuário já assistiu, evitando que um refresh acidental esconda o botão novamente.

---

### 4. 💳 Botão Abaixo do Preço (Sempre Visível)
- O card de oferta com o preço (**R$ 37,00**) possui um botão de destaque sempre visível logo abaixo do preço:
  `SIM! QUERO APRENDER A FAZER VELAS COMESTÍVEIS`
- Aponta diretamente para o checkout da Cakto: `https://pay.cakto.com.br/DASzMjB`

---

## 📦 Como Publicar no GitHub e Vercel

1. **Inicializar o repositório:**
   ```bash
   git init
   git add .   # adiciona index.html, README.md e a pasta images/
   git commit -m "Landing page Velas Comestíveis Gourmet"
   git branch -M main
   git remote add origin <URL-DO-SEU-REPOSITORIO>
   git push -u origin main
   ```

2. **Deploy na Vercel:**
   - Acesse [vercel.com](https://vercel.com) e faça login.
   - Clique em **Add New** → **Project** e importe o repositório do GitHub.
   - Como é uma página estática pura (HTML + CSS + JS), o deploy é instantâneo sem configurações adicionais.

