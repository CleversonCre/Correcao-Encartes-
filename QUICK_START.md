# 🚀 Quick Start - Sistema de Comparação de Arquivos

## 📦 **Arquivos Prontos para Deploy**

Este projeto está completamente configurado e pronto para ser implantado em qualquer servidor web.

## ⚡ **Início Rápido**

### **1. Upload para o Servidor**
Faça upload da pasta `backend/comparacao_app/` para seu servidor web.

### **2. Configuração Básica**
```bash
# Navegue até o diretório
cd comparacao_app

# Crie ambiente virtual
python3 -m venv venv

# Ative o ambiente virtual
source venv/bin/activate

# Instale dependências
pip install -r requirements.txt
```

### **3. Configure as Chaves de API**
Edite o arquivo `src/services/enhanced_ai_service.py` e insira suas chaves:

```python
# Linha 12: ChatGPT
self.openai_api_key = "sua_chave_openai_aqui"

# Linha 13: Gemini
self.gemini_api_key = "sua_chave_gemini_aqui"

# Linha 17: Hugging Face
self.huggingface_token = "sua_chave_huggingface_aqui"

# Linha 20: Cohere
self.cohere_api_key = "sua_chave_cohere_aqui"

# Linha 23: TextRazor
self.textrazor_api_key = "sua_chave_textrazor_aqui"

# Linha 26: Cloudmersive
self.cloudmersive_api_key = "sua_chave_cloudmersive_aqui"
```

### **4. Execute a Aplicação**

**Opção A - Desenvolvimento:**
```bash
python src/main.py
```

**Opção B - Produção (Recomendado):**
```bash
python run_production.py
```

### **5. Acesse o Site**
Abra seu navegador e acesse: `http://seu_servidor:5000`

## 🔧 **Funcionalidades Implementadas**

✅ **6 APIs de IA Integradas:**
- ChatGPT (OpenAI)
- Gemini (Google)
- Hugging Face
- Cohere
- TextRazor
- Cloudmersive

✅ **Sistema de Fallback Inteligente:**
- Tenta cada API sequencialmente
- Nunca fica completamente offline
- Sistema de fallback robusto

✅ **Interface Moderna:**
- Design responsivo
- Status das APIs em tempo real
- Upload de múltiplos formatos
- Progresso em tempo real

✅ **Formatos Suportados:**
- PDF, JPEG, PNG, Excel, Word

## 🌐 **Como Obter Chaves de API Gratuitas**

### **1. Hugging Face (Gratuita)**
- Acesse: https://huggingface.co/settings/tokens
- Crie uma conta e gere um token

### **2. Cohere (1000 calls gratuitas)**
- Acesse: https://dashboard.cohere.com/api-keys
- Registre-se e clique em "New Trial Key"

### **3. TextRazor (Gratuita)**
- Acesse: https://www.textrazor.com/
- Clique em "Free API Key"

### **4. Cloudmersive (600 calls/mês)**
- Acesse: https://account.cloudmersive.com/signup
- Registre-se gratuitamente

### **5. ChatGPT (Paga)**
- Acesse: https://platform.openai.com/api-keys
- Crie uma conta e adicione créditos

### **6. Gemini (Gratuita com limites)**
- Acesse: https://makersuite.google.com/app/apikey
- Crie uma conta Google e gere a chave

## 📁 **Estrutura do Projeto**

```
comparacao_app/
├── src/
│   ├── main.py                    # Aplicação principal
│   ├── routes/file_comparison.py  # Rotas da API
│   ├── services/
│   │   ├── enhanced_ai_service.py # 6 APIs de IA
│   │   └── file_processor.py      # Processador de arquivos
│   └── static/                    # Frontend compilado
├── venv/                          # Ambiente virtual
├── requirements.txt               # Dependências
├── run_production.py              # Script de produção
├── app.wsgi                       # Para Apache
└── DEPLOYMENT_INSTRUCTIONS.md     # Instruções detalhadas
```

## 🔍 **Teste de Funcionamento**

1. **Acesse:** `http://seu_servidor:5000`
2. **Verifique:** Status das APIs na tela inicial
3. **Teste:** Upload de dois arquivos
4. **Confirme:** Processamento e resultados

## 🆘 **Solução Rápida de Problemas**

**Erro de porta em uso:**
```bash
sudo lsof -i :5000
sudo kill -9 PID_DO_PROCESSO
```

**Erro de dependências:**
```bash
pip install --upgrade -r requirements.txt
```

**APIs não funcionando:**
- Verifique se as chaves estão corretas
- Acesse `/api/health` para diagnóstico

---

**✅ Status:** Pronto para produção
**🔧 Configuração:** 5 minutos
**🚀 Deploy:** Imediato

