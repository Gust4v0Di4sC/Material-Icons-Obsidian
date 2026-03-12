# 🎨 Material Icons for Obsidian

Adiciona ícones no estilo **Material Theme** (igual ao VS Code) no explorador de arquivos do Obsidian.

## ✨ Ícones suportados

### Arquivos
| Extensão | Cor |
|---|---|
| `.md` | Azul |
| `.js` | Amarelo |
| `.ts` | Azul escuro |
| `.py` | Azul/Amarelo |
| `.json` | Amarelo |
| `.css` | Azul |
| `.html` | Laranja |
| `.svg` | Âmbar |
| `.png`, `.jpg`, `.jpeg`, `.gif` | Verde |
| `.pdf` | Vermelho |
| `.txt` | Cinza |
| `.xml` | Laranja escuro |
| `.yaml`, `.yml` | Vermelho |
| `.sh` | Verde |
| `.zip` | Laranja |
| `.env` | Vermelho |
| `.gitignore` | Laranja |

### Pastas especiais
`src`, `assets`, `images`, `docs`, `notes`, `projects`, `templates`, `.git`, `config`, `archive`, `scripts`

---

## 🚀 Como instalar e compilar

### 1. Pré-requisitos
- [Node.js](https://nodejs.org/) v18 ou superior
- npm (vem junto com o Node.js)

### 2. Clone ou baixe este repositório
```bash
git clone <url-do-repo> material-icons-obsidian
cd material-icons-obsidian
```

### 3. Instale as dependências
```bash
npm install
```

### 4. Compile o plugin
```bash
npm run build
```
Isso vai gerar o arquivo `main.js` na raiz do projeto.

### 5. Instale no Obsidian

**Opção A — Manual (recomendado para desenvolvimento):**
```bash
# No Mac/Linux:
cp main.js manifest.json styles.css ~/seu-vault/.obsidian/plugins/material-icons/

# No Windows (PowerShell):
# Primeiro crie a pasta:
# New-Item -ItemType Directory -Path "$env:USERPROFILE\seu-vault\.obsidian\plugins\material-icons"
# Depois copie:
# Copy-Item main.js, manifest.json, styles.css "$env:USERPROFILE\seu-vault\.obsidian\plugins\material-icons\"
```

**Opção B — Script automático:**
```bash
# Edite o caminho do vault antes de rodar:
VAULT="$HOME/MeuVault"
PLUGIN="$VAULT/.obsidian/plugins/material-icons"
mkdir -p "$PLUGIN"
cp main.js manifest.json styles.css "$PLUGIN/"
echo "✅ Plugin instalado com sucesso!"
```

### 6. Ative no Obsidian
1. Abra o Obsidian
2. Vá em **Configurações** → **Plugins da Comunidade**
3. Desative o "Modo restrito" se ainda não fez isso
4. Em **Plugins instalados**, localize **Material Icons**
5. Ative o toggle

---

## 🛠️ Desenvolvimento

Para desenvolvimento com hot-reload:
```bash
npm run dev
```

---

## 📁 Estrutura do projeto
```
material-icons-obsidian/
├── main.ts          ← código fonte principal
├── main.js          ← arquivo compilado (gerado pelo build)
├── manifest.json    ← metadados do plugin
├── styles.css       ← estilos CSS
├── package.json
├── tsconfig.json
└── esbuild.config.mjs
```

---

## 🎨 Adicionando mais ícones

Edite o objeto `SVG` em `main.ts` e adicione novos mapeamentos no `FOLDER_MAP` ou na lógica de `getFileIcon`.

Os SVGs do [Material Icon Theme](https://github.com/PKief/vscode-material-icon-theme) são open source (MIT) e podem ser usados diretamente.
