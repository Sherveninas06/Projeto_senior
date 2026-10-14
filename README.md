# Fala Amigo Sênior

**Aplicativo assistente para pessoas idosas, com foco em comunicação, rotina e contato com a família.**

> ⚠️ **Repositório demonstrativo.** Este repositório apresenta o projeto para fins de portfólio profissional. Ele **não contém o código-fonte, o instalador nem outros materiais do aplicativo**, e **não concede nenhuma licença** de uso, cópia, modificação ou distribuição. Veja [LICENSE-AND-USAGE.md](LICENSE-AND-USAGE.md).

---

## Sumário

- [Sobre o projeto](#sobre-o-projeto)
- [O problema](#o-problema)
- [Público-alvo](#público-alvo)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Arquitetura (visão geral)](#arquitetura-visão-geral)
- [Minha contribuição](#minha-contribuição)
- [Status e roteiro](#status-e-roteiro)
- [Propriedade intelectual e uso](#propriedade-intelectual-e-uso)
- [Contato](#contato)

---

## Sobre o projeto

O **Fala Amigo Sênior** (no aplicativo, *Falamigo Sênior*) é um aplicativo para celular feito para apoiar a **comunicação**, a **autonomia** e a **organização do dia a dia** de pessoas idosas.

A proposta é ser simples de usar: botões grandes, textos legíveis, cores suaves e ações que se resolvem com um toque. Dentro do aplicativo, o assistente aparece como **"Ajudante"**.

A versão 1.0.0 foi desenvolvida entre julho e agosto de 2026, com geração de instalador para Android.

## O problema

Muitas pessoas idosas enfrentam barreiras com aplicativos comuns: menus complexos, letras pequenas e fluxos com muitos passos. Algumas também têm dificuldade para falar ou para lembrar tarefas da rotina, como horários de remédios e refeições.

O Fala Amigo Sênior reúne em um só lugar, com uma interface pensada para esse público:

- uma forma rápida de **expressar necessidades** sem depender da fala;
- um **acompanhamento visual da rotina** diária;
- um **acesso direto à família e aos cuidadores**.

## Público-alvo

- **Pessoas idosas** que buscam mais autonomia no uso do celular.
- Pessoas com **dificuldade de fala**, que podem usar frases prontas faladas pelo aparelho.
- **Familiares e cuidadores**, que acompanham a rotina e mantêm contato com a pessoa assistida.

## Funcionalidades

As funcionalidades abaixo estão implementadas na versão 1.0.0.

### 🗣️ Comunicação por voz
- Cartões com **emoji e frase curta** (por exemplo, *"Sim"*, *"Não"*, *"Pode me ajudar?"*).
- Ao tocar no cartão, **o aparelho fala a frase em voz alta** (texto para fala).
- Adição de novas frases com o emoji escolhido e remoção de frases não utilizadas.

### 📋 Rotina diária
- Tarefas organizadas em **Manhã ☀️, Tarde 🌤️ e Noite 🌙**.
- Marcação de tarefas concluídas e **indicador de progresso** (por exemplo, *"3 de 5 concluídas"*).
- Adição e remoção de tarefas em cada período.
- As alterações ficam salvas no próprio aparelho.

### 👨‍👩‍👧 Família e cuidadores
- Lista com fotos e nomes de familiares e cuidadores.
- **Ligar** com um toque (abre o discador com o número preenchido).
- **Enviar SMS** com uma mensagem pronta, que a pessoa confirma antes do envio.

### 🆘 SOS Emergência *(em desenvolvimento)*
- Botão de destaque na tela inicial. A interface já existe; **a ação de emergência ainda não foi implementada**.

## Tecnologias

| Área | Tecnologia |
|---|---|
| Linguagem principal | Python (3.10 ou superior) |
| Interface multiplataforma | [Flet](https://flet.dev) (0.86 ou superior) |
| Texto para fala | Extensão Flet própria (`flet-tts`), com uma parte em Python e outra em Dart/Flutter, criada a partir do modelo de extensões do Flet |
| Persistência | Arquivos JSON locais |
| Plataforma de distribuição | Android (APK gerado com `flet build apk`) |
| Integrações do sistema | Abertura do discador e do aplicativo de SMS por esquemas `tel:` e `sms:` |
| Controle de versão | Git / GitHub |

## Arquitetura (visão geral)

O aplicativo está organizado em camadas com responsabilidades separadas:

```
┌─────────────────────────────────────────────┐
│  Navegação por rotas                        │  ponto de entrada, troca de telas
├─────────────────────────────────────────────┤
│  Telas (UI)                                 │  início, comunicação, rotina,
│                                             │  família/cuidadores, contato
├─────────────────────────────────────────────┤
│  Serviços                                   │  voz, frases de comunicação, rotinas
├──────────────────────┬──────────────────────┤
│  Dados locais (JSON) │  Extensão de voz     │
│                      │  (Python ⇄ Flutter)  │
└──────────────────────┴──────────────────────┘
        Tema visual centralizado (cores e estilos)
```

Mais detalhes em [docs/overview.md](docs/overview.md). Detalhes internos de implementação não fazem parte deste repositório.

## Minha contribuição

Fui a **única desenvolvedora** do Fala Amigo Sênior e fiz toda a parte técnica, sem auxílio técnico de outras pessoas:

- **Estrutura do aplicativo** e navegação por rotas entre as telas.
- **Interface** de todas as telas, com tema visual centralizado e foco em legibilidade e toque fácil.
- **Comunicação por voz:** criação e integração de uma extensão própria para o Flet, unindo Python e Flutter, incluindo a correção do funcionamento da voz no Android.
- **Serviços de dados:** leitura, gravação e edição de frases e rotinas em armazenamento local.
- **Integração com recursos do celular:** ligações e SMS.
- **Build e distribuição:** geração do instalador Android (APK).
- **Documentação** do projeto.

O histórico completo de versionamento, com a autoria dos commits, está preservado no repositório original, que é privado.

## Status e roteiro

**Versão atual:** 1.0.0 (Android)

Próximos passos previstos:

- [ ] Ativar a ação do botão SOS
- [ ] Cadastro de contatos pelo próprio aplicativo
- [ ] Lembretes e notificações de remédios
- [ ] Atalho para WhatsApp

## Propriedade intelectual e uso

- Este repositório tem **caráter exclusivamente demonstrativo**.
- **Não é concedida nenhuma licença**, nem de código aberto nem comercial, sobre o código-fonte, o aplicativo, o nome, a interface ou outros materiais do projeto.
- O acesso, a reprodução, a distribuição e a utilização de materiais protegidos dependem das **autorizações e dos direitos aplicáveis**.

Termos completos em [LICENSE-AND-USAGE.md](LICENSE-AND-USAGE.md).

## Contato

Para conversar sobre o projeto, pedir uma demonstração ou tratar de uma **possível licença ou autorização de uso**:

**Bárbara Pironato Sherveninas**
📧 [sherve2023@gmail.com](mailto:sherve2023@gmail.com)
🐙 GitHub: [@Sherveninas06](https://github.com/Sherveninas06)
