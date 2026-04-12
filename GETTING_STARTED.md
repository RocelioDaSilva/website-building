# 🚀 Guia Rápido - Após Instalação

## ✅ Instalação Concluída!

Parabéns! Seu projeto Corhed Landing Page está pronto para uso.

## 🎯 Próximos Passos

### 1. **Visualizar o Site**
```bash
# Abra o site no navegador (porta 8000)
npm run preview
```

### 2. **Personalizar o Conteúdo**
Edite `index.html` para ajustar:
- ✅ Nome da empresa
- ✅ Informações de contato
- ✅ Serviços oferecidos
- ✅ Estatísticas e números
- ✅ Depoimentos de clientes

### 3. **Adicionar Logo**
- Substitua `corhed-logo.png` pelo logo oficial
- Verifique se aparece corretamente no header

### 4. **Configurar Formulários**
Para formulários funcionais:
- **Formspree**: Crie conta gratuita em [formspree.io](https://formspree.io)
- Substitua `action="#"` no formulário por sua URL do Formspree

### 5. **Deploy (Opcional)**
Quando estiver pronto para publicar:
```bash
# Netlify (recomendado)
npm install -g netlify-cli
netlify deploy --prod --dir=.

# Ou Vercel
npm install -g vercel
vercel --prod
```

## 🔧 Comandos Úteis

```bash
# Desenvolvimento
npm run dev          # Servidor com auto-reload

# Produção
npm run preview      # Teste final antes do deploy
npm run build        # Otimização para produção

# Deploy
npm run deploy       # Para GitHub Pages (se configurado)
```

## 📞 Suporte

- **Email**: contato@corhed.com
- **Telefone**: (11) 3000-0000
- **Documentação**: README.md completo

---

**🎉 Seu site está funcionando! Acesse http://localhost:8000**