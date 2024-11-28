# Study App

Uma aplicação móvel desenvolvida em React Native para gerenciamento de cartões de estudo e tarefas com integração Firebase.

## Estrutura do Projeto

```
├── assets/                 # Recursos estáticos como imagens e ícones
├── src/
│   ├── config/            # Arquivos de configuração
│   │   └── firebaseConfig.js  # Inicialização e config do Firebase
│   ├── contexts/          # Provedores de Context do React
│   │   ├── AuthContext.js     # Gerenciamento do estado de autenticação
│   │   └── CartoesEstudoContext.js  # Gerenciamento dos cartões de estudo
│   └── screens/           # Telas da aplicação
│       ├── EdicaoCartaoScreen.js    # Tela de edição de cartões
│       ├── ListaCartaoScreen.js     # Tela principal de listagem
│       ├── LoginScreen.js           # Tela de autenticação
│       ├── RegistroScreen.js        # Tela de Registro
│       └── TarefasVencimentoProximoScreen.js  # Tela de tarefas próximas
├── App.js                 # Componente Pai
├── app.json             
├── babel.config.js       # Configuração do Babel
└── package.json          # Dependências do projeto
```

## Arquivos Principais

- [App.js](App.js) : Componente principal que configura navegação e provedores de contexto
- [firebaseConfig.js](firebaseConfig.js): Configuração e inicialização do Firebase
- [AuthContext.js](AuthContext.js): Gerencia estado de autenticação do usuário
- [CartoesEstudoContext.js](CartoesEstudoContext.js): Gerencia dados e operações dos cartões de estudo
- [screens](screens): Contém todas as telas da aplicação

## Funcionalidades

- Autenticação de usuários (login/registro)
- Gerenciamento de cartões de estudo (operações CRUD)
- Acompanhamento de status dos cartões (backlog, em andamento, concluído)
- Acompanhamento de datas de vencimento
- Filtragem de tarefas por status
- Visualização de tarefas próximas (próximos 15 dias)

## Bibliotecas Utilizadas

### Dependências Principais
- `react-native`: Framework para desenvolvimento móvel
- `expo`: Plataforma de desenvolvimento para React Native
- `firebase`: Serviços de backend e autenticação

### Navegação
- `@react-navigation/native`: Container de navegação
- `@react-navigation/native-stack`
- `@react-navigation/stack`

### Componentes de UI
- `react-native-vector-icons`: Componentes de ícones
- `@react-native-picker/picker`: Componente de seleção
- `react-native-modal-datetime-picker`: Seletor de data/hora

### Gerenciamento das variáveis  de ambiente
- `react-native-dotenv`: Gerenciamento de variáveis de ambiente

### Desenvolvimento
- `babel-preset-expo`: Configuração do Babel para Expo
- `react-native-dotenv`: Suporte a variáveis de ambiente

## Configuração do Ambiente

O projeto utiliza variáveis de ambiente para configuração do Firebase. Crie um arquivo [.env](.env) com:

```
FIREBASE_API_KEY=
FIREBASE_AUTH_DOMAIN=
FIREBASE_PROJECT_ID=
FIREBASE_STORAGE_BUCKET=
FIREBASE_MESSAGING_SENDER_ID=
FIREBASE_APP_ID=
```

## Executando o Projeto

1. Instale as dependências:
```bash
npm install
```

2. Inicie o servidor de desenvolvimento:
```bash
npm start
```


## Autenticação

O app utiliza Firebase Authentication para gerenciamento de usuários. Os usuários podem:
- Registrar com email/senha
- Fazer login com credenciais existentes
- Fazer logout da aplicação

## Modelo de Dados

Os cartões de estudo contêm as seguintes informações:
- Título
- Notas
- Status (backlog/in_progress/done)
- Data de vencimento
- ID do usuário (para a identificação dos cartões por usuário)

Os dados são armazenados no Firebase Firestore com atualizações em tempo real.
