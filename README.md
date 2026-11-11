# 📷 guineves :: fotolog

> **1 foto por dia · Proporção vertical 3:4 · Baixa resolução · Sem edição · Y2K Dark**  
> Subdomínio oficial: [fotolog.guineves.com.br](https://fotolog.guineves.com.br)

Projeto off-topic nostálgico resgatando a essência da web dos anos 2000 (estilo Fotolog.net / Flogão), com estética escura (Y2K Dark), carimbo analógico de data no estilo câmera digital, metadados de humor/música/localização, livro de visitas (guestbook) e mini galeria.

---

## 🛠️ Comandos e Fluxo de Trabalho

Assim como os demais projetos da rede `guineves.com.br`, o fotolog utiliza arquitetura de dois estágios:
- **Sandbox Privado (`origin`):** [`gmneves/sandbox-fotolog`](https://github.com/gmneves/sandbox-fotolog) com histórico detalhado e suporte a `_drafts/`.
- **Repositório Público (`public`):** [`gmneves/fotolog`](https://github.com/gmneves/fotolog) publicado como commit único limpo via GitHub Pages.

### 1. Adicionar uma nova foto
```bash
./nova-foto.sh /caminho/para/foto.jpg
```
*O script corta centralizadamente a imagem para **3:4**, redimensiona para **600x800** (resolução analógica clássica), extrai o timestamp de câmera e cria automaticamente o arquivo Markdown em `_posts/` ou `_drafts/`.*

### 2. Salvar no Sandbox (Privado)
```bash
./commit.sh "mensagem do commit"
```
*Comita as alterações locais assinadas com chave GPG e sincroniza com o repositório privado.*

### 3. Publicar no ar (Público)
```bash
./publish.sh
```
*Gera o commit único assinado com GPG e atualiza o GitHub Pages em `fotolog.guineves.com.br`.*

---

## 🎨 Características do Design

- **Grid de Duas Colunas:** Coluna da foto com cartão principal e Livro de Visitas + Sidebar com perfil (avatar sem distorção), rolo de miniaturas, flogmarks e contador de visitantes odômetro.
- **Proporção 3:4 Sagrada:** Todas as fotos respeitam o clássico formato vertical.
- **Carimbo Analógico de Câmera:** Timestamp no canto inferior direito (`'26 11 02`).
- **Navegação Retrô:** Links « anterior e próxima » entre fotos por data.
- **Arquivo Completo:** Grade visual de miniaturas em `/arquivo/`.
- **GoatCounter Analytics & RSS Feed:** Integrado para métricas leves e privacidade.
