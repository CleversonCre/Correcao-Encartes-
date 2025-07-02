# Site de Comparação e Correção de Arquivos

## Descrição

Este projeto é um site web moderno e funcional que permite comparar e corrigir arquivos em diversos formatos (PDF, JPEG, PNG, Excel, Word) utilizando inteligência artificial (ChatGPT e Gemini). O sistema apresenta os resultados em formato de tabela e inclui um temporizador de execução.

## Funcionalidades

### ✅ Funcionalidades Implementadas

- **Upload de Arquivos**: Suporte para PDF, JPEG, PNG, Excel (.xlsx, .xls), Word (.docx, .doc)
- **Processamento de Arquivos**: Extração de conteúdo de diferentes formatos
- **Integração com IA**: APIs do ChatGPT e Gemini para análise e correção
- **Interface Moderna**: Design responsivo e intuitivo usando React e Tailwind CSS
- **Temporizador**: Acompanhamento do progresso e tempo estimado de conclusão
- **Resultados em Tabela**: Apresentação organizada dos resultados da comparação
- **Status das APIs**: Verificação em tempo real do status das APIs de IA
- **Sistema de Fallback**: Funcionamento mesmo quando APIs estão indisponíveis

### 📋 Campos da Tabela de Resultados

- **Planilha Original**: Conteúdo original extraído do arquivo
- **Planilha Corrigida**: Versão corrigida após processamento da IA
- **Descrição Imagem**: Análise do conteúdo visual
- **Resultado da Comparação**: "Correto" ou descrição das divergências encontradas

## Tecnologias Utilizadas

### Backend (Flask)
- **Flask**: Framework web Python
- **Flask-CORS**: Suporte a requisições cross-origin
- **OpenAI API**: Integração com ChatGPT
- **Google Generative AI**: Integração com Gemini
- **PyPDF2**: Processamento de arquivos PDF
- **openpyxl**: Processamento de arquivos Excel
- **Threading**: Processamento assíncrono

### Frontend (React)
- **React**: Biblioteca JavaScript para interface
- **Vite**: Build tool e servidor de desenvolvimento
- **Tailwind CSS**: Framework CSS para estilização
- **shadcn/ui**: Componentes de interface
- **Lucide Icons**: Ícones modernos

## Estrutura do Projeto

```
website_comparacao/
├── backend/
│   └── comparacao_app/
│       ├── src/
│       │   ├── main.py              # Arquivo principal do Flask
│       │   ├── routes/
│       │   │   ├── user.py          # Rotas de usuário (template)
│       │   │   └── file_comparison.py # Rotas de comparação de arquivos
│       │   ├── services/
│       │   │   ├── file_processor.py # Processamento de arquivos
│       │   │   └── ai_service.py     # Integração com APIs de IA
│       │   ├── models/              # Modelos de dados
│       │   └── static/              # Arquivos estáticos (frontend build)
│       ├── venv/                    # Ambiente virtual Python
│       └── requirements.txt         # Dependências Python
├── frontend/
│   └── comparacao-frontend/
│       ├── src/
│       │   ├── App.jsx              # Componente principal
│       │   ├── App.css              # Estilos principais
│       │   └── components/          # Componentes React
│       ├── dist/                    # Build de produção
│       └── package.json             # Dependências Node.js
├── test_files/                      # Arquivos de teste
└── README.md                        # Documentação
```

## Instalação e Execução Local

### Pré-requisitos
- Python 3.11+
- Node.js 20+
- npm ou pnpm

### Backend (Flask)

1. Navegue até o diretório do backend:
```bash
cd website_comparacao/backend/comparacao_app
```

2. Ative o ambiente virtual:
```bash
source venv/bin/activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

4. Execute o servidor:
```bash
python src/main.py
```

O backend estará disponível em `http://localhost:5000`

### Frontend (React)

1. Navegue até o diretório do frontend:
```bash
cd website_comparacao/frontend/comparacao-frontend
```

2. Instale as dependências:
```bash
pnpm install
```

3. Execute o servidor de desenvolvimento:
```bash
pnpm run dev
```

O frontend estará disponível em `http://localhost:5173`

## Acesso Online

🌐 **Site Público**: https://5000-ibpaaa1qmcju11u6lbs7n-fb30960a.manusvm.computer

## APIs Utilizadas

### ChatGPT (OpenAI)
- **Status**: ❌ Quota excedida (necessário upgrade do plano)
- **Modelo**: GPT-4o
- **Uso**: Análise e correção de conteúdo

### Gemini (Google)
- **Status**: ✅ Online e funcional
- **Modelo**: Gemini 1.5 Flash
- **Uso**: Análise e correção de conteúdo (principal)

## Prompt de Correção

O sistema utiliza o seguinte prompt para análise e correção:

```
Considerar os fatores abaixo para esta correção. Primeiro faça a correção da planilha removendo as abreviações e corrigindo com padrões encontrados na Web com a grafia completa e correta seguindo as normas de escrita e acentuação brasileira atuais. Finalizado o processo acima compare com as imagens do encarte e realize as correções.

Observações (Correções): Detalhe as divergências encontradas, como:
- Data da oferta
- Divergência de Preço: Indique se o preço no catálogo está incorreto e qual é o valor certo.
- Divergência de Preço: Considerar quando houver 2 preços em um produto considere que o valor maior é o Preço 1 e o menor pertencente a clientes do Clube Golff mantendo ambos os valores. Com a descrição "Preço 1 R$ xx,xx, Clientes Clube Golff R$xx,xx"
- Divergência de Descrição/Ortografia/Acentuação: Aponte as palavras com erro de ortografia, falta ou excesso de acentos, ou termos diferentes nas descrições do catálogo e da tabela.
- Outras Diferenças: Se houver variação na marca (ex: Açúcar Globo vs. Santa Isabel), tamanho ou qualquer outra característica relevante.

Garanta que todos os produtos visíveis nas imagens sejam comparados e que as correções de ortografia e acentuação sigam o padrão da língua portuguesa, utilizando a descrição da tabela de ofertas como referência para a 'Descrição Correta'. Se um item não aparecer em uma das fontes, indique essa ausência na coluna de observações. Apontar itens faltantes seja no encarte ou planilha.
```

## Como Usar

1. **Acesse o site**: Abra o link público ou execute localmente
2. **Selecione os arquivos**: Clique nas áreas de upload e selecione dois arquivos para comparação
3. **Inicie a comparação**: Clique no botão "Iniciar Comparação"
4. **Acompanhe o progresso**: Observe o temporizador e status do processamento
5. **Visualize os resultados**: Analise a tabela de comparação gerada pela IA

## Limitações Conhecidas

- **ChatGPT**: Quota da API excedida, necessário upgrade do plano
- **Arquivos Word**: Processamento simplificado devido a limitações de dependências no deploy
- **Tamanho máximo**: 16MB por arquivo
- **Formatos suportados**: PDF, JPEG, PNG, Excel, Word

## Melhorias Futuras

- Implementação de processamento completo de arquivos Word
- Suporte a mais formatos de arquivo
- Sistema de autenticação de usuários
- Histórico de comparações
- API própria para processamento de texto
- Cache de resultados
- Processamento em lote

## Suporte

Para dúvidas ou problemas, verifique:
1. Status das APIs no painel do site
2. Formato e tamanho dos arquivos
3. Conexão com a internet
4. Logs do console do navegador

## Licença

Este projeto foi desenvolvido como uma solução personalizada para comparação e correção de arquivos usando IA.

