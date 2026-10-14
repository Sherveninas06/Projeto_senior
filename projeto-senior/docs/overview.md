# Visão geral técnica: Fala Amigo Sênior

> Documento de apresentação. Descreve o projeto em **nível geral**, sem expor o código-fonte nem detalhes internos de implementação.

## 1. Objetivo

Oferecer a pessoas idosas um assistente no celular que concentre três necessidades do dia a dia:

1. **Comunicar-se**, inclusive sem depender da fala;
2. **Acompanhar a rotina** de manhã, tarde e noite;
3. **Falar com familiares e cuidadores** com um toque.

## 2. Princípios de design

| Princípio | Como aparece no aplicativo |
|---|---|
| Simplicidade | Tela inicial com poucos blocos grandes que levam direto a cada área |
| Legibilidade | Ícones e emojis grandes, textos com bom contraste |
| Conforto visual | Paleta de cores suaves (tons de rosa, verde e bege sobre fundo claro), definida em um tema centralizado |
| Ação em um toque | Frases faladas, tarefas marcadas, ligação e SMS iniciados com um toque |
| Confirmação humana | O SMS é aberto com o texto pronto, e quem envia é a própria pessoa |
| Funcionamento local | Frases e rotinas ficam salvas no aparelho, sem depender de servidor |

## 3. Arquitetura em camadas

```
Navegação por rotas
   │
   ├── Telas ─────────────── início · comunicação · nova frase
   │                         rotina (manhã/tarde/noite) · nova tarefa
   │                         família/cuidadores · contato
   │
   ├── Serviços ──────────── voz · comunicações · rotinas
   │       │
   │       ├── Dados locais (JSON)
   │       └── Extensão de voz (Python ⇄ Flutter)
   │
   └── Tema visual centralizado
```

- **Navegação:** o aplicativo usa navegação por rotas, com uma pilha de telas e retorno à tela anterior.
- **Telas:** cada área funcional fica em um módulo próprio de interface.
- **Serviços:** separam as regras de negócio (criar, editar e remover frases e tarefas, falar um texto) da interface.
- **Dados locais:** as informações são gravadas em arquivos JSON, e o aplicativo cria valores iniciais quando eles ainda não existem.
- **Extensão de voz:** para falar em voz alta, foi criada uma extensão própria do Flet que liga a camada Python à camada nativa Flutter. Ela foi feita a partir do modelo de extensões do Flet.
- **Recursos do sistema:** ligações e mensagens usam os aplicativos nativos do celular.

## 4. Plataformas

- **Android:** instalador (APK) gerado com o processo de build do Flet.
- **Desktop:** usado para execução e testes durante o desenvolvimento.

## 5. Status

| Área | Situação |
|---|---|
| Comunicação por voz | ✅ Implementada |
| Rotina diária | ✅ Implementada |
| Família e cuidadores (ligação/SMS) | ✅ Implementada |
| SOS Emergência | 🚧 Interface pronta, ação ainda não implementada |
| Cadastro de contatos no app | 🗓️ Planejado |
| Lembretes de remédios | 🗓️ Planejado |
| Atalho para WhatsApp | 🗓️ Planejado |

## 6. O que não está neste repositório

- Código-fonte do aplicativo e da extensão de voz
- Instalador (APK) e arquivos de build
- Imagens, fotos e dados usados no aplicativo
- Configurações de ambiente e quaisquer credenciais

Para pedir uma demonstração ou tratar de autorização de uso, veja a seção de contato no [README](../README.md).
