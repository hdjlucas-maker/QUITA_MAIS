# Quita Mais 📈

**O inverso do Tigrinho.** Uma jornada gamificada para vencer dívidas, controlar impulsos financeiros e construir hábitos melhores — no seu ritmo, sem cartão de crédito.

[![Deploy](https://img.shields.io/badge/demo-quita--mais--app.web.app-059669?logo=firebase&logoColor=white)](https://quita-mais-app.web.app)
[![PWA](https://img.shields.io/badge/PWA-instal%C3%A1vel-111C2E?logo=pwa&logoColor=white)](https://quita-mais-app.web.app)
[![Firebase](https://img.shields.io/badge/Firebase-Auth%20%2B%20Firestore-FFCA28?logo=firebase&logoColor=black)](https://console.firebase.google.com/project/quita-mais-app/overview)
[![GitHub](https://img.shields.io/badge/GitHub-hdjlucas--maker%2FQUITA__MAIS-181717?logo=github)](https://github.com/hdjlucas-maker/QUITA_MAIS)

---

## 💡 Sobre

Aplicativos financeiros tradicionais costumam ser cansativos, complexos ou desmotivadores. O **Quita Mais** transforma educação financeira em uma **experiência interativa**: cada desafio vencido, sequência mantida e valor guardado te deixa visivelmente mais forte — com XP, níveis, chefes e conquistas.

O objetivo não é prometer resultados financeiros, mas **incentivar escolhas mais conscientes** com metas simples, progresso visível e motivação no momento certo.

## 🎮 Como funciona

| Sistema | Descrição |
|---|---|
| ⚔️ **Desafios** | 12 desafios financeiros (delivery, cartão, parcelas, bar…) com prazo, dificuldade (Fácil/Médio/Difícil) e recompensa em XP — até 3 simultâneos |
| 🔥 **Streak diário** | Sequência de dias ativos; quebra se você sumir |
| 💰 **Cofre** | Registre o que guardou, com nota e histórico; XP proporcional ao valor |
| 👹 **Chefes** | Cartão Sangrador, Compra por Impulso, Amanhã Eterno — ataque até derrotá-los |
| 🏅 **Conquistas** | 7 medalhas: primeiro depósito, R$500 guardados, 7 dias seguidos, nível 5… |
| 🏆 **Ranking global** | Top 10 guerreiros por XP total, com sua posição destacada |
| 🤖 **Coach** | Mensagens motivacionais contextuais (nome, streak, saldo, desafios) geradas 100% no dispositivo |
| 🛡️ **Classes** | Recruta → Soldado → Guerreiro → Caçador → Dragão → Lenda (avatar evolui com o nível) |

## 🚀 Tecnologias

- **HTML5 + CSS3 + JavaScript (ES Modules)** — sem frameworks, carrega rápido
- **Firebase Authentication** — login com Google
- **Cloud Firestore** — persistência com **transações** (à prova de corridas entre abas/dispositivos)
- **PWA** — instalável, com service worker e funciona offline
- **Google Fonts** — Manrope + DM Sans

## 📱 Testar

**Live:** [quita-mais-app.web.app](https://quita-mais-app.web.app) · ou instale direto do navegador (Adicionar à tela inicial)

1. **Aceitar o desafio** → onboarding de 3 passos (inimigo financeiro, dívida, prazo)
2. **Entrar com Google** → seu progresso fica salvo na nuvem
3. Aceite desafios, guarde valores, derrote chefes e suba no ranking 🏆

## 🛠️ Desenvolvimento

```bash
# servidor local (necessário por causa dos ES Modules e do service worker)
python3 -m http.server 8080
# abre http://localhost:8080
```

### Deploy

```bash
# o Firebase CLI precisa estar logado: firebase login
firebase deploy --only hosting,firestore:rules
```

Configuração de projeto em `firebase.json` + `.firebaserc`. Login com Google e domínios autorizados ficam no console do Firebase (Authentication → Sign-in method).

### Estrutura

```
.
├── index.html              # app completo: telas, estilos e lógica
├── manifest.webmanifest    # identidade PWA
├── sw.js                   # service worker (cache: rede primeiro, offline como reserva)
├── firestore.rules         # segurança: cada usuário só escreve no próprio documento
├── firebase.json           # config de deploy (hosting + rules)
├── .firebaserc             # projeto Firebase (quita-mais-app)
└── icons/                  # ícones 192 / 512 / maskable
```

### Arquitetura em uma frase

- **Escritas atômicas**: XP, saldo, streak, chefes e desafios atualizados via `runTransaction` — não perde dados com duas abas abertas.
- **Coach local**: nenhuma chamada a APIs de IA — mensagens variadas por contexto (geral, vitória, depósito), sem custo e sem chaves.
- **Fuso local**: streak calculado no horário do dispositivo (não UTC), correto para o Brasil.
- **Cache inteligente**: páginas sempre da rede (com fallback offline); assets cacheados.

## 🔒 Privacidade e segurança

- Cada usuário **só escreve no próprio documento** do Firestore (`firestore.rules`)
- Nenhuma credencial privada no cliente — apenas a config pública do SDK do Firebase, protegida pelas regras
- O ranking expõe apenas nome, nível e XP

## 🗺️ Roadmap

- [ ] Gráficos de evolução do saldo
- [ ] Meta financeira com barra de progresso dedicada
- [ ] Lembretes (notification API) para o desafio do dia
- [ ] Modo claro

## 👤 Autor

Desenvolvido por **Lucas Correa** — [hdjlucas-maker](https://github.com/hdjlucas-maker)

---

> ⚠️ Projeto educacional. Não é consultoria financeira e não promete resultados — o foco é incentivar hábitos conscientes.
