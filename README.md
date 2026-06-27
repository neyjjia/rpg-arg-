# PROJETO ÂNCORA

## 📁 Estrutura do projeto

```
.
├── index.html              → Página inicial (terminal de senha)
├── css/
│   └── style.css           → Toda a aparência do site (cores no topo do arquivo)
├── js/
│   ├── passwords.js        → ⭐ As senhas ficam AQUI (edite este arquivo)
│   ├── auth.js             → Lógica de verificação da senha
│   └── effects.js          → Efeitos: CRT, cursor, texto digitando, áudio
├── pages/
│   ├── _modelo.html        → Modelo para criar novas páginas (duplique este)
│   ├── documento01.html    → Página secreta de exemplo (senha: ancora)
│   └── documento02.html    → Página secreta de exemplo (senha: vigia-13)
├── assets/
│   └── images/             → Todas as imagens (logo, evidências, documentos)
└── README.md
```

---

## 🔑 Senhas de exemplo

| Senha      | Abre                    |
|------------|-------------------------|
| `ancora`   | `pages/documento01.html`|
| `vigia-13` | `pages/documento02.html`|

> As senhas **não** diferenciam maiúsculas de minúsculas.

---

## ✏️ Como personalizar

### Alterar / adicionar senhas
Abra **`js/passwords.js`**. Cada linha liga uma senha a uma página:

```js
const passwords = {
  "ancora": "pages/documento01.html",
  "vigia-13": "pages/documento02.html",
  "novasenha": "pages/documento03.html",   // ← adicione assim
};
```

A senha é o lado esquerdo; o caminho da página é o lado direito.

### Criar uma nova página secreta
1. Copie **`pages/_modelo.html`** e renomeie (ex.: `documento03.html`).
2. Edite os textos, títulos e imagens marcados no arquivo.
3. Em `js/passwords.js`, crie uma senha apontando para o novo arquivo.

— você pode criar dezenas de páginas repetindo esses passos.

### Trocar imagens
Coloque o novo arquivo em **`assets/images/`** e, no HTML da página, troque o
`src` da imagem. Você pode simplesmente **substituir** um arquivo existente
mantendo o mesmo nome — assim nem precisa editar o código.

```html
<img src="../assets/images/evidencia-01.png" alt="Descrição" />
```

### Trocar / adicionar música
1. Coloque o arquivo `.mp3` em **`assets/`**.
2. No HTML da página, descomente o bloco `<audio>` (está no fim do `_modelo.html`)
   e aponte o `src` para a sua música.
3. Um botão de **ligar/desligar som** aparece sozinho no canto da tela.

```html
<audio id="trilha" loop>
  <source src="../assets/minha-musica.mp3" type="audio/mpeg" />
</audio>
```

### Mudar as cores / tema
Abra **`css/style.css`**. No topo, em `:root`, estão todas as cores:

```css
--cor-fundo: #0a0e0c;     /* fundo */
--cor-destaque: #39ff6a;  /* verde fósforo */
--cor-alerta: #ff3b3b;    /* erros */
```

Mude esses valores e o site inteiro acompanha.

### Efeito de texto digitando
Adicione `data-typing` a qualquer elemento. Opcionalmente, controle a
velocidade (ms por letra) com `data-velocidade`:

```html
<p data-typing data-velocidade="40">Esse texto será digitado letra a letra.</p>
```

---
