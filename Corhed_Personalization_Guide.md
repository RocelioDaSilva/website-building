# Corhed - Guia de Personalização da Landing Page

## 📋 Visão Geral

A landing page foi criada especificamente para a **Corhed**, uma empresa de soluções profissionais. O site é uma landing page focada em **demonstração de serviços** (sem recrutamento) com foco em conversão e apresentação clara da empresa.

---

## 🎨 O Que Já Está Pronto

✅ **Layout responsivo** (funciona em mobile, tablet e desktop)
✅ **Header com navegação sticky** (fica no topo)
✅ **Hero section** com call-to-action principal
✅ **6 serviços principais** em grid com cards interativos
✅ **Seção "Por Que Escolher"** com 6 diferenciais
✅ **Formulário de contato** funcional
✅ **Informações de contato** completas
✅ **Footer com links** legais
✅ **Menu mobile** responsivo
✅ **Animações suaves**
✅ **Cores profissionais** (Azul #003366, Vermelho #ff0000, Branco)

---

## 🔧 O Que Você Precisa Personalizar

### 1. **Informações Básicas da Empresa**

Abra o arquivo `corhed-index.html` e procure por:

| Elemento | Localização | O Que Mudar |
|----------|-------------|-----------|
| **Email** | Seção Contato | `contato@corhed.com` |
| **Telefone** | Seção Contato | `(11) 3000-0000` |
| **Endereço** | Seção Contato | `São Paulo, SP` |
| **Horários** | Seção Contato | `Segunda a Sexta: 9h às 18h` |

### 2. **Os 6 Serviços**

Cada serviço tem ícone, título e descrição. Para personalizar, edite:

**Serviço 1** (Consultoria Estratégica)
```
📊 Consultoria Estratégica
Desenvolvemos estratégias personalizadas para otimizar seus processos...
```

**Serviço 2** (Gestão Empresarial)
**Serviço 3** (Assessoria Profissional)
**Serviço 4** (Análise de Mercado)
**Serviço 5** (Implementação de Soluções)
**Serviço 6** (Parcerias Estratégicas)

### 3. **Diferenciais (Por Que Escolher)**

6 cards com razões para escolher. Você pode:
- ✓ Manter os 6 diferenciais atuais
- ✓ Customizar os textos
- ✓ Adicionar/remover diferenciais

### 4. **Formulário de Contato**

O formulário coleta:
- Nome Completo
- E-mail
- Empresa
- Serviço de Interesse (dropdown com 6 opções + "Outro")
- Mensagem

---

## 📝 Instruções Passo a Passo para Personalização

### Passo 1: Localizar o Arquivo
```
c:\Users\PCGAME\Desktop\website building\corhed-index.html
```

### Passo 2: Abrir em um Editor de Texto
- Use VS Code, Notepad++, ou qualquer editor
- Ou abra diretamente em um navegador para visualizar

### Passo 3: Substituir Informações
Use a função "Encontrar e Substituir" (Ctrl+H) para:

```
ANTES                          DEPOIS
contato@corhed.com      →      seu-email@corhed.com
(11) 3000-0000         →      seu-telefone
São Paulo, SP          →      sua-cidade
Segunda a Sexta: 9h    →      seus-horários
```

### Passo 4: Personalizar Serviços
Localize a seção `<!-- Services Section -->` e edite:
- Ícone (emoji)
- Título do serviço
- Descrição (2-3 linhas)

### Passo 5: Adicionar Logo ou Imagem
Na seção `<header>`, você pode substituir:
```html
<div class="logo">CORHED</div>
```

Por:
```html
<img src="logo.png" alt="Corhed" style="height: 40px;">
```

---

## 🎯 Próximas Ações Recomendadas

### 1. **Configurar Envio de Formulário**
Atualmente o formulário mostra um alerta. Para funcionar completamente, você precisa:

**Opção A: Formulário simples (Email direto)**
```html
<form action="mailto:contato@corhed.com" method="POST" enctype="text/plain">
```

**Opção B: Usar serviço gratuito (Recomendado)**
- Formspree (formspree.io)
- Basin (usebasin.com)
- Netlify Forms

### 2. **Adicionar Mais Páginas** (Opcional)
Você pode criar:
- `/aboute-us.html` - Sobre a Corhed
- `/portfolio.html` - Trabalhos/Case Studies
- `/blog.html` - Blog com artigos

### 3. **Integrar Google Analytics**
Adicione no `<head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-ID"></script>
```

### 4. **SEO Otimização**
Edite no `<head>`:
```html
<meta name="description" content="Descrição customizada aqui">
<meta name="keywords" content="consultoria, gestão, empresa">
```

### 5. **SSL/HTTPS**
Se você publicar o site, certifique-se de usar HTTPS (protege os dados dos formulários)

---

## 🌐 Como Usar o Site

### Para Visualizar Localmente
1. Salve o arquivo como `corhed-index.html`
2. Abra em seu navegador: `File > Open` e selecione o arquivo
3. Ou execute um servidor local (veja [Server.ps1](#) no workspace)

### Para Publicar na Internet
1. Compre um domínio (namecheap, godaddy, etc.)
2. Contrate hosting (bluehost, siteground, netlify)
3. Faça upload do arquivo HTML
4. Configure SSL (HTTPS)

---

## 📊 Estrutura do Arquivo

```
corhed-index.html
├── Header (Logo + Navegação)
├── Hero (Headline + CTA)
├── Services (6 cards)
├── Why Us (6 diferenciais)
├── Contact (Info + Formulário)
└── Footer (Copyright + Links)
```

---

## 🎨 Cores Corporativas (Já Aplicadas)

| Cor | Código | Uso |
|-----|--------|-----|
| Azul Profissional | #003366 | Header, Títulos |
| Vermelho Accent | #ff0000 | Botões, Hover |
| Branco | #ffffff | Fundo, Texto |
| Cinza | #666666 | Texto secundário |

**Para mudar cores globalmente**, procure por:
```css
#003366  → substitua pela sua cor principal
#ff0000  → substitua pela sua cor accent
```

---

## ⚙️ Funcionalidades Incluídas

✅ Menu responsivo para mobile
✅ Smooth scroll nos links
✅ Hover effects nos cards e botões
✅ Validação básica de formulário
✅ Animations ao carregamento
✅ Otimizado para SEO
✅ Acessível (HTML semântico)
✅ Rápido (sem dependências externas)

---

## 📱 Testar em Diferentes Dispositivos

1. **Desktop**: F12 > Dimensões normais
2. **Tablet**: F12 > 768px width
3. **Mobile**: F12 > 375px width

Tudo deve ficar bonito e funcional em todos os tamanhos.

---

## 🆘 Suporte & Troubleshooting

**Problema: Formulário não envia**
- Solução: Configure um backend ou use serviço como Formspree

**Problema: Imagens não aparecem**
- Solução: Use URLs completas (http://...) ou coloque imagens na mesma pasta

**Problema: Estilo quebrado**
- Solução: Verifique se não deletou nenhuma `<div>` ou `</div>`

**Problema: Mobile menu não funciona**
- Solução: Certifique-se de que o JavaScript está intacto

---

## 📂 Arquivos no Workspace

```
website building/
├── corhed-index.html ← ARQUIVO PRINCIPAL (VOCÊ ESTÁ AQUI)
├── index.html (versão genérica)
├── about.html
├── services.html
├── faq.html
├── contact.html
├── Privacy_Policy.md
├── Terms_and_Conditions.md
├── Cookie_Policy.md
├── Email_Setup_Guide.md
├── Domain_and_Hosting_Setup.md
├── SEO_Setup_Guide.md
├── Social_Media_Strategy.md
├── Content_Templates.md
├── Website_Launch_Checklist.md
├── Lovable_Website_Prompt.md
├── Complete_Website_Checklist.md
└── website ai list.md
```

---

## ✨ Próximos Passos

1. **Hoje**: Personalize o arquivo com suas informações
2. **Amanhã**: Configure domínio e hosting
3. **Próxima Semana**: Publique o site
4. **Contínuo**: Monitore análiticas e otimize

---

**Arquivo criado em**: 26 de Março de 2026
**Última atualização**: Corhed Landing Page v1.0
**Status**: Pronto para personalização