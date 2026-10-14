# Projeto Sênior

**Projeto de aplicativo assistente para pessoas idosas, com foco em comunicação, rotina e contato com a família.**

> ⚠️ **Repositório demonstrativo.** Este repositório apresenta o projeto para fins de portfólio profissional. Ele **não contém o código-fonte, o instalador nem outros materiais do aplicativo**, e **não concede nenhuma licença** de uso, cópia, modificação ou distribuição. Consulte [LICENSE-AND-USAGE.md](LICENSE-AND-USAGE.md).

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

O **Projeto Sênior** é um projeto de aplicativo para celular desenvolvido para apoiar a **comunicação**, a **autonomia** e a **organização do dia a dia** de pessoas idosas.

A proposta é oferecer uma experiência simples e acessível, com botões grandes, textos legíveis, cores suaves e ações que podem ser realizadas com um toque. No aplicativo, o assistente é identificado como **"Ajudante"**.

A versão 1.0.0 foi desenvolvida entre julho e agosto de 2026, com geração de instalador para Android.

## O problema

Muitas pessoas idosas enfrentam barreiras ao utilizar aplicativos comuns, como menus complexos, letras pequenas e fluxos com muitos passos. Algumas também apresentam dificuldades de comunicação verbal ou precisam de apoio para organizar tarefas diárias, como horários de medicamentos e refeições.

O Projeto Sênior reúne recursos voltados a essas necessidades:

- Uma forma rápida de **expressar necessidades** sem depender exclusivamente da fala.
- Um **acompanhamento visual da rotina** diária.
- **Acesso direto à família e aos cuidadores**, facilitando a comunicação.

## Público-alvo

- **Pessoas idosas** que buscam mais autonomia no uso do celular.
- Pessoas com **dificuldades de fala**, que podem utilizar frases prontas reproduzidas pelo aparelho.
- **Familiares e cuidadores** que acompanham a rotina e mantêm contato com a pessoa assistida.

## Funcionalidades

As funcionalidades descritas abaixo correspondem à versão 1.0.0 do aplicativo.

### 🗣️ Comunicação por voz

- Cartões com **emoji e frases curtas**, como "Sim", "Não" e "Pode me ajudar?".
- Reprodução das frases em voz alta ao tocar nos cartões, por meio de tecnologia de texto para fala.
- Adição de novas frases com emojis personalizados e remoção de frases não utilizadas.

### 📋 Rotina diária

- Tarefas organizadas em **Manhã ☀️, Tarde 🌤️ e Noite 🌙**.
- Marcação de tarefas concluídas e **indicador de progresso**, como "3 de 5 concluídas".
- Adição e remoção de tarefas em cada período.
- Armazenamento das alterações no próprio aparelho.

### 👨‍👩‍👧 Família e cuidadores

- Lista com fotos e nomes de familiares e cuidadores.
- **Ligações com um toque**, abrindo o discador com o número preenchido.
- **Envio de SMS** com uma mensagem pronta, que precisa ser confirmada antes do envio.

### 🆘 SOS Emergência — em desenvolvimento

- Botão de destaque na tela inicial.
- A interface está implementada, mas a ação de emergência ainda não foi desenvolvida.

## Tecnologias

| Área | Tecnologia |
|---|---|
| Linguagem principal | Python 3.10 ou superior |
| Interface multiplataforma | [Flet](https://flet.dev), versão 0.86 ou superior |
| Texto para fala | Extensão própria para Flet (`flet-tts`), com componentes em Python e Dart/Flutter |
| Persistência de dados | Arquivos JSON locais |
| Plataforma de distribuição | Android, com geração de APK pelo comando `flet build apk` |
| Integrações do sistema | Abertura do discador e do aplicativo de SMS por meio dos esquemas `tel:` e `sms:` |
| Controle de versão | Git e GitHub |

## Arquitetura (visão geral)

O aplicativo está organizado em camadas com responsabilidades separadas:

```text
┌─────────────────────────────────────────────┐
│ Navegação por rotas                         │
│ Ponto de entrada e troca de telas           │
├─────────────────────────────────────────────┤
│ Telas (UI)                                  │
│ Início, comunicação, rotina, família        │
│ e cuidadores                                │
├─────────────────────────────────────────────┤
│ Serviços                                    │
│ Voz, frases de comunicação e rotinas        │
├──────────────────────┬──────────────────────┤
│ Dados locais (JSON)  │ Extensão de voz      │
│                      │ (Python ↔ Flutter)   │
└──────────────────────┴──────────────────────┘

Tema visual centralizado: cores e estilos
```

Mais detalhes estão disponíveis em [docs/overview.md](docs/overview.md). Os detalhes internos de implementação não fazem parte deste repositório demonstrativo.

## Minha contribuição

Fui a **única desenvolvedora responsável pela implementação técnica** do Projeto Sênior, desenvolvendo o aplicativo sem auxílio técnico de outras pessoas.

Minhas contribuições incluíram:

- **Estrutura do aplicativo:** organização e navegação por rotas entre as telas.
- **Interface:** desenvolvimento das telas, centralização do tema visual e atenção à legibilidade e à facilidade de interação.
- **Comunicação por voz:** criação e integração de uma extensão própria para o Flet, conectando Python e Flutter, incluindo a correção do funcionamento da voz no Android.
- **Serviços de dados:** leitura, gravação e edição de frases e rotinas em armazenamento local.
- **Integração com recursos do celular:** implementação das integrações para ligações e SMS.
- **Build e distribuição:** geração do instalador Android (APK).
- **Documentação:** elaboração da documentação do projeto.

O histórico completo de versionamento, com a autoria dos commits, está preservado no repositório original, que é privado.

## Status e roteiro

**Versão do aplicativo:** 1.0.0 (Android).

Próximos passos previstos:

- [ ] Implementar a ação do botão SOS.
- [ ] Desenvolver o cadastro de contatos pelo próprio aplicativo.
- [ ] Implementar lembretes e notificações de medicamentos.
- [ ] Adicionar atalho para WhatsApp.

## Propriedade intelectual e uso

- Este repositório possui **caráter exclusivamente demonstrativo**.
- **Não é concedida nenhuma licença**, seja de código aberto ou comercial, sobre o código-fonte, o aplicativo, o nome, a interface ou outros materiais do projeto.
- O acesso, a reprodução, a distribuição e a utilização de materiais protegidos dependem das **autorizações e dos direitos aplicáveis**.

Consulte os termos completos em [LICENSE-AND-USAGE.md](LICENSE-AND-USAGE.md).

## Contato

Para conversar sobre o projeto, solicitar uma demonstração ou tratar de uma **possível licença ou autorização de uso**:

**Bárbara Pironato Sherveninas**

📧 [sherve2023@gmail.com](mailto:sherve2023@gmail.com)

🐙 GitHub: [@Sherveninas06](https://github.com/Sherveninas06)
