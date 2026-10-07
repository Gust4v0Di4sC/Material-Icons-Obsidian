<div align="center">

# 🎨 Material Icons for Obsidian

**Ícones coloridos no estilo Material Theme para arquivos e pastas do Obsidian.**

[![Version](https://img.shields.io/badge/version-1.0.1-7c3aed)](https://github.com/Gust4v0Di4sC/Material-Icons-Obsidian/releases)
[![Obsidian](https://img.shields.io/badge/Obsidian-1.0%2B-7c3aed?logo=obsidian&logoColor=white)](https://obsidian.md/)
[![TypeScript](https://img.shields.io/badge/TypeScript-4.7-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/license-MIT-2ea44f)](LICENSE)

[Instalação](#-instalação) · [Ícones suportados](#-ícones-suportados) · [Desenvolvimento](#-desenvolvimento) · [Reportar problema](https://github.com/Gust4v0Di4sC/Material-Icons-Obsidian/issues)

</div>

---

## Sobre

**Material Icons for Obsidian** personaliza o explorador de arquivos do Obsidian com ícones inspirados no Material Theme do VS Code.

O plugin identifica automaticamente extensões e nomes de pastas, aplica cores distintas para facilitar a navegação e acompanha alterações no vault sem exigir atualização manual da interface.

## ✨ Funcionalidades

- 🎯 **Reconhecimento automático** — identifica arquivos pela extensão e pastas pelo nome.
- 🌈 **Ícones coloridos** — diferencia rapidamente conteúdos no explorador de arquivos.
- 🔄 **Atualização em tempo real** — reage à criação, exclusão e renomeação de itens.
- 📄 **Fallback inteligente** — aplica um ícone genérico a arquivos e pastas não mapeados.
- 🪶 **Integração leve** — usa SVGs embutidos, sem carregar imagens ou fontes externas.
- 🖱️ **Feedback visual** — destaca suavemente o ícone ao passar o cursor.

## 🧩 Ícones suportados

### Arquivos

| Ícone | Tipo | Extensões | Cor predominante |
|:---:|---|---|---|
| 📝 | Markdown | `.md` | Roxo |
| 🟨 | JavaScript | `.js` | Amarelo |
| 🟦 | TypeScript | `.ts` | Azul |
| 🐍 | Python | `.py` | Azul e amarelo |
| `{ }` | JSON | `.json` | Amarelo |
| 🎨 | Estilos | `.css` | Azul |
| 🌐 | HTML | `.html` | Laranja |
| `</>` | XML | `.xml` | Laranja |
| ⚙️ | Configuração YAML | `.yaml`, `.yml` | Vermelho |
| 💻 | Shell script | `.sh` | Verde |
| 📃 | Texto | `.txt` | Cinza |
| 📕 | PDF | `.pdf` | Vermelho |
| 🔐 | Variáveis de ambiente | `.env` | Vermelho |
| 📦 | Arquivo compactado | `.zip` | Laranja |
| 🖼️ | Imagem | `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.svg`, `.ico` | Variada |
| 📄 | Outros arquivos | Demais extensões | Cinza |

### Pastas

| Ícone | Categoria | Nomes reconhecidos |
|:---:|---|---|
| 💻 | Código-fonte | `src`, `source` |
| 🎨 | Recursos | `assets`, `asset` |
| 🖼️ | Imagens | `images`, `image`, `img` |
| 📚 | Documentação | `docs`, `documents` |
| 📝 | Notas | `notes`, `note` |
| 📊 | Projetos | `projects`, `project` |
| 📋 | Templates | `templates`, `template` |
| 🖥️ | Scripts | `scripts`, `script` |
| ⚙️ | Configurações | `config`, `configs`, `settings` |
| 🗄️ | Arquivos históricos | `archive`, `archives` |
| 🌿 | Git | `.git`, `git` |
| 📁 | Outras pastas | Demais nomes |

## 🛠️ Tecnologias

| Área | Tecnologias |
|---|---|
| Plugin | Obsidian API |
| Linguagem | TypeScript |
| Interface | SVG e CSS |
| Build | esbuild |
| Empacotamento | npm |

## 🏗️ Arquitetura

O plugin mantém os SVGs e seus mapeamentos em `main.ts`. Ao carregar o workspace, ele percorre o explorador de arquivos, identifica cada item e injeta o ícone correspondente. Um `MutationObserver` monitora mudanças na árvore para atualizar os ícones quando necessário.

```text
Obsidian File Explorer
        │
        ▼
Extensão do arquivo / nome da pasta
        │
        ▼
Mapeamento do ícone SVG
        │
        ▼
Ícone renderizado e estilizado
```

### Estrutura do projeto

```text
material-icons-obsidian/
├── 🧠 main.ts              # Código-fonte e mapeamentos
├── 📦 main.js              # Plugin compilado
├── 🎨 styles.css           # Aparência e alinhamento dos ícones
├── 🧩 manifest.json        # Metadados do plugin para o Obsidian
├── 📋 versions.json        # Compatibilidade entre versões
├── 🛠️ esbuild.config.mjs   # Configuração de build
├── ⚙️ tsconfig.json        # Configuração do TypeScript
└── 📄 package.json         # Dependências e scripts
```

## 🚀 Instalação

### Instalação manual

1. Baixe ou compile os arquivos `main.js`, `manifest.json` e `styles.css`.
2. Crie a pasta abaixo dentro do seu vault:

```text
SEU_VAULT/.obsidian/plugins/material-icons/
```

3. Copie os três arquivos para essa pasta.
4. Abra o Obsidian e acesse **Configurações → Plugins da Comunidade**.
5. Desative o modo restrito, se necessário, e ative **Material Icons**.

> Se o plugin não aparecer imediatamente, reinicie o Obsidian ou recarregue os plugins instalados.

## 💻 Desenvolvimento

### Pré-requisitos

- [Node.js](https://nodejs.org/) 18 ou superior
- npm

### Executando localmente

```bash
git clone https://github.com/Gust4v0Di4sC/Material-Icons-Obsidian.git
cd Material-Icons-Obsidian
npm install
npm run dev
```

O modo de desenvolvimento recompila o plugin sempre que `main.ts` é alterado.

Para gerar uma versão de produção:

```bash
npm run build
```

O comando valida o TypeScript e gera o arquivo `main.js` na raiz do projeto.

## ➕ Adicionando novos ícones

1. Adicione o SVG ao objeto `SVG` em `main.ts`.
2. Para arquivos, use a extensão como chave do novo ícone.
3. Para pastas, relacione o nome desejado ao ícone no objeto `FOLDER_MAP`.
4. Execute `npm run build` para validar e compilar as alterações.

Os ícones foram inspirados no projeto open source [Material Icon Theme](https://github.com/PKief/vscode-material-icon-theme).

## 📄 Licença

Distribuído sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais informações.
