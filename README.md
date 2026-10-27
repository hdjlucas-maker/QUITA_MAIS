# Quita+ 📈

**O inverso do Tigrinho.** Uma jornada gamificada para ajudar você a vencer dívidas, controlar impulsos financeiros e construir hábitos melhores.

## Sobre o projeto

Aplicativos financeiros podem parecer complexos ou desmotivadores. O Quita+ transforma educação financeira em uma experiência interativa: cada desafio concluído, hábito construído e valor guardado ajuda o usuário a avançar no próprio ritmo.

O objetivo não é prometer resultados financeiros, mas incentivar escolhas mais conscientes com metas simples, acompanhamento de progresso e motivação.

## Funcionalidades

- Login com Google
- Dashboard com nível, XP, sequência diária e valores guardados
- Onboarding para registrar o foco financeiro e o prazo desejado
- Desafios financeiros com prazos, dificuldade e recompensas
- Registro de valores guardados e histórico de depósitos
- Chefes, conquistas e ranking global
- Coach motivacional com mensagens contextuais geradas localmente (funciona offline, sem custo e sem expor credenciais de API)
- Interface responsiva para celular e desktop
- Aplicação instalável (PWA)
- Persistência de dados com Firebase Authentication e Cloud Firestore

## Tecnologias

- HTML5, CSS3 e JavaScript
- Firebase Authentication
- Cloud Firestore
- Progressive Web App (PWA)

## Como executar

1. Local: sirva os arquivos por um servidor HTTP (`python3 -m http.server`).
2. Produção: `firebase deploy --only hosting` (app no ar em `https://quita-mais-app.web.app`).
3. Login com Google: ativado no console (Authentication → Sign-in method → Google). O domínio de hosting do Firebase já vem autorizado automaticamente no Auth.
4. Regras do Firestore: `firebase deploy --only firestore:rules`.

> Não publique credenciais privadas no código do cliente. As chaves de configuração do Firebase usadas no navegador devem ser protegidas pelas regras do Firestore e pelas configurações de domínio autorizado.

## Objetivo

Unir educação financeira, gamificação, experiência do usuário e motivação comportamental para tornar a organização financeira mais acessível e envolvente.

## Autor

Desenvolvido por **Lucas Correa**.
