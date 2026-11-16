🐾 PetCare — Gerenciador de Saúde e Rotina de Pets

Aplicativo Android nativo desenvolvido em Kotlin com Jetpack Compose para o gerenciamento completo da vida de animais de estimação. O sistema permite cadastrar múltiplos pets de diferentes espécies e acompanhar vacinas, medicamentos, consultas na agenda, documentos oficiais e estoque de produtos.

Projeto desenvolvido para a disciplina de Desenvolvimento Mobile do IFPB (Instituto Federal da Paraíba).

✨ Funcionalidades e Requisitos Atendidos

🎨 Interface Moderna e Responsiva (Jetpack Compose & Material Design 3):

UI declarativa adaptável a diferentes tamanhos de tela utilizando componentes do Material 3 (Scaffold, ModalNavigationDrawer, LazyColumn, Surface, OutlinedTextField).

Tema personalizado (PetCareTheme) com paleta de cores focada em bem-estar animal.

🔍 Busca com Filtro e Navegação entre Telas:

Barra de pesquisa em tempo real na tela inicial (HomeScreen) permitindo filtrar animais por nome, espécie ou raça.

Filtros por pet específico nas telas de Agenda, Medicamentos e Documentos.

Navegação fluida com Jetpack Navigation Compose e menu lateral (ModalNavigationDrawer) integrando 7 telas:

HomeScreen (Listagem de pets, busca e card da API REST)

PetFormScreen (Cadastro e edição de animais)

PetDetailScreen (Perfil detalhado e resumo do pet)

MedicationsScreen (Controle de remédios e vacinas)

AgendaScreen (Consultas veterinárias, banho e tosa)

DocumentsScreen (RGA, microchip, exames e carteira de vacinação)

ProductsScreen (Controle de ração, higiene e alerta de reposição de estoque)

🌐 Consumo de API REST com Retrofit:

Integração com a API pública Dog CEO API (https://dog.ceo/api/) utilizando a biblioteca Retrofit2 e conversor Gson.

Requisições assíncronas com Kotlin Coroutines e exibição de imagens remotas via Coil (AsyncImage).

💾 Persistência de Dados e CRUD Completo:

Operações completas de Create, Read, Update e Delete (CRUD) gerenciadas de forma reativa com StateFlow e ViewModel.

Povoamento inicial automático (Database Seeding) com 3 animais de espécies distintas (Cachorro, Gato e Ave/Calopsita), além de medicamentos, vacinas, agendamentos, documentos e produtos de exemplo.

🛠️ Tecnologias e Arquitetura

O projeto segue o padrão arquitetural MVVM (Model-View-ViewModel):

Linguagem: Kotlin

Interface (UI): Jetpack Compose + Material Design 3

Navegação: Navigation Compose

Arquitetura e Estado: Android ViewModel, StateFlow e Kotlin Coroutines

Rede / API REST: Retrofit 2 + Gson Converter

Banco de Dados: Room Database (SQLite) / Persistência estruturada com DAO

Carregamento de Imagens: Coil Compose

📂 Estrutura de Pastas do Projeto

br.edu.ifpb.petcare
├── data
│   ├── dao
│   │   └── PetCareDao.kt          # Consultas e operações CRUD no banco
│   ├── database
│   │   └── PetCareDatabase.kt     # Configuração da instância do banco de dados
│   └── model
│       └── Entities.kt            # Modelos: Pet, Appointment, HealthRecord, PetDocument, PetProduct
├── ui
│   ├── components
│   │   └── CommonComponents.kt    # TopBar, botões customizados e cards reutilizáveis
│   ├── navigation
│   │   └── Screen.kt              # Rotas tipadas de navegação do app
│   ├── screens
│   │   ├── HomeScreen.kt          # Tela principal com busca, lista de pets e destaque da API REST
│   │   ├── PetFormScreen.kt       # Formulário de criação/edição/exclusão de pet
│   │   ├── PetDetailScreen.kt     # Perfil completo do pet selecionado
│   │   ├── MedicationsScreen.kt   # Histórico e cadastro de vacinas e remédios
│   │   ├── AgendaScreen.kt        # Compromissos com checklist de conclusão
│   │   ├── DocumentsScreen.kt     # Prontuário e documentos do animal
│   │   └── ProductsScreen.kt      # Gestão de compras e alerta de reposição
│   └── theme
│       └── Theme.kt               # Cores, tipografia e tema Material 3
├── viewmodel
│   └── PetCareViewModel.kt        # Lógica de negócios, estados reativos, seed inicial e cliente Retrofit
└── MainActivity.kt                # Ponto de entrada, Drawer lateral e NavHost


🚀 Como Executar o Projeto

Clone este repositório:

git clone https://github.com/SEU-USUARIO/PetCare.git


Abra o projeto no Android Studio (versão Ladybug / Iguana ou superior recomendada).

Aguarde a sincronização automática do Gradle (Sync Project with Gradle Files).

Certifique-se de que o emulador ou dispositivo físico possui acesso à internet (para o carregamento das imagens da API REST via Retrofit).

Clique em Run 'app' (Shift + F10).

🧪 Dados Iniciais de Demonstração (Seed Automático)

Ao iniciar o aplicativo pela primeira vez com o banco limpo, o sistema cadastra automaticamente:

Thor (Cachorro - Golden Retriever): Antipulgas Simparic, Vacina V10 + Antirrábica, agendamento de Banho e Tosa, Certificado de Microchipagem e Ração Premier.

Mingau (Gato - Siamês): Vermífugo Milbemax, Vacina Quádrupla Felina (V4), Check-up Renal, Carteira de Vacinação Digital, Ração Super Premium e Areia Biodegradável.

Piu (Ave - Calopsita): Suplemento Avitrin Complexo Vitamínico, consulta de revisão com especialista em aves, Certificado de Sexagem por DNA e Ração Extrusada.
