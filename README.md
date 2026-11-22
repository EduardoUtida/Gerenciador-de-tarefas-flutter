# Gerenciador de Tarefas

Aplicativo mobile desenvolvido com **Flutter e Firebase** para gerenciamento de tarefas pessoais. O sistema permite que cada usuário tenha sua própria conta e organize suas atividades de maneira simples e intuitiva.

## Tecnologias utilizadas

- **Flutter:** desenvolvimento da interface mobile.
- **Dart:** linguagem de programação.
- **Firebase Authentication:** cadastro e autenticação de usuários.
- **Firebase Realtime Database:** armazenamento dos usuários e tarefas.
- **SharedPreferences:** armazenamento local das preferências de tema.

## Funcionalidades

### Autenticação de usuários
- Cadastro de usuários com nome, e-mail e senha.
- Login com e-mail e senha.
- Logout.
- Persistência da sessão do usuário.

### Gerenciamento de tarefas
- Cadastro de tarefas.
- Edição de tarefas existentes.
- Exclusão de tarefas.
- Definição de título e descrição.
- Definição de data de vencimento.
- Classificação por prioridade: baixa, média e alta.
- Identificação de tarefas pendentes e concluídas.
- Listagem e visualização das tarefas.

### Página inicial
- Exibição das informações do usuário.
- Contagem total de tarefas.
- Quantidade de tarefas pendentes.
- Quantidade de tarefas concluídas.

### Configurações
- Alternância entre tema claro e escuro.
- Salvamento da preferência de tema no dispositivo.

## Organização do projeto

```text
lib/
├── models/
│   ├── tarefa.dart
│   └── usuario.dart
├── screens/
│   ├── cadastro_usuario_screen.dart
│   ├── configuracoes_screen.dart
│   ├── home_screen.dart
│   ├── login_screen.dart
│   └── tarefas_screen.dart
├── services/
│   ├── auth_service.dart
│   ├── firebase_service.dart
│   └── preferences_service.dart
├── themes/
│   └── app_theme.dart
├── widgets/
├── firebase_options.dart
└── main.dart
```

## Configuração e execução

### Pré-requisitos

- Flutter instalado.
- Dart instalado.
- Android Studio ou Visual Studio Code.
- Conta Google e projeto configurado no Firebase.

### 1. Clone o repositório

```bash
git clone https://github.com/EduardoUtida/Gerenciador-de-tarefas-flutter.git
```

### 2. Acesse a pasta do projeto

```bash
cd Gerenciador-de-tarefas-flutter
```

### 3. Instale as dependências

```bash
flutter pub get
```

### 4. Configure o Firebase

O projeto utiliza Firebase Authentication e Firebase Realtime Database.

Para executar com sua própria configuração Firebase:

1. Crie um projeto no [Firebase Console](https://console.firebase.google.com/).
2. Ative o método de autenticação por e-mail e senha.
3. Crie um Realtime Database.
4. Configure o aplicativo Flutter utilizando o FlutterFire CLI.
5. Gere o arquivo `firebase_options.dart` para sua configuração.

### 5. Execute o aplicativo

Conecte um dispositivo Android ou inicie um emulador e execute:

```bash
flutter run
```

## Banco de dados

Os dados são organizados por usuário, utilizando o UID fornecido pelo Firebase Authentication.

Estrutura simplificada:

```text
usuarios/
  UID_DO_USUARIO/
    nome
    email

tarefas/
  UID_DO_USUARIO/
    ID_DA_TAREFA/
      titulo
      descricao
      dataVencimento
      prioridade
      concluida
```

As regras de segurança do Realtime Database restringem a leitura e escrita aos usuários autenticados, permitindo o acesso somente aos próprios dados.

## Desenvolvedor

**Eduardo Hideki Utida**

Estudante de Engenharia de Software – UNIGRAN.

Projeto desenvolvido como atividade prática da disciplina de Programação Mobile.

---

**Repositório:** [GitHub - Gerenciador de Tarefas Flutter](https://github.com/EduardoUtida/Gerenciador-de-tarefas-flutter)
