# Lab 01: Unprotected Admin Functionality

🎯 **Objetivo:**  
Acessar uma funcionalidade administrativa não protegida e demonstrar que é possível excluir um usuário (no caso, `carlos`) sem autenticação.

---

## 🔍 Descrição e resolução passo a passo

A aplicação apresenta uma loja online chamada **"We Like to Shop"**, com uma home simples, botões de login e navegação básica. Nosso objetivo é descobrir se existe uma página de administração acessível diretamente, sem autenticação.

### 🧪 Etapas realizadas:

1. Acessei a aplicação e naveguei entre a home, produtos e a página de login.
2. Testei manualmente algumas URLs comuns de painel admin, como:
   - `/admin`
   - `/administrator`

   Nenhuma delas funcionou.

3. Em seguida, tentei acessar o arquivo **`/robots.txt`**, que revelou a seguinte informação:
User-agent: *
Disallow: /administrator-panel


Esse arquivo informa ao Google e outros buscadores que não devem indexar certas rotas. Isso acabou **expondo justamente a rota do painel administrativo**, que deveria ser protegida.

4. Acessei a URL:  
`https://<lab-url>.web-security-academy.net/administrator-panel`

Nessa página, encontrei uma seção com usuários listados (Carlos e Wiener), e opções de deletar.

5. Cliquei no botão **Delete** ao lado do usuário `carlos`.

6. Recebi a confirmação da resolução do laboratório com a mensagem:  
**"Congratulations, you solved the lab!"**

---

## 📌 Observações técnicas

- A vulnerabilidade estava relacionada ao **acesso não autenticado** de uma funcionalidade crítica (painel admin).
- O uso indevido do arquivo `robots.txt` acabou expondo essa funcionalidade.
- Em um cenário real, isso **não configura uma falha no `robots.txt`, mas sim na falta de autenticação adequada para funções administrativas.**

---

## ✅ Conclusão

Este laboratório demonstrou como um simples acesso ao arquivo `robots.txt` pode revelar páginas sensíveis. Em testes de segurança reais, esse tipo de análise pode ser o primeiro passo para uma escalada de privilégios ou ataque mais sério.

---

> ⚠️ Todos os testes foram realizados em ambiente autorizado da [Web Security Academy](https://portswigger.net/web-security). Nunca apliquei essas técnicas fora de ambientes legais e autorizados.
