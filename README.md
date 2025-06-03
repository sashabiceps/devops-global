📌 DevOps Tools & Cloud Computing - Projeto de Containerização
📝 Descrição
Projeto de containerização de uma API Java com PostgreSQL, desenvolvido como parte da disciplina DevOps Tools & Cloud Computing.
Objetivo: Conteinerizar uma aplicação Java com banco de dados PostgreSQL, seguindo boas práticas de Infraestrutura como Código (IaC).

🚀 Tecnologias Utilizadas
Linguagem: Java

Banco de Dados: PostgreSQL (containerizado)

Containerização: Docker + Docker Compose

Gerenciamento de Dependências: Maven

Cloud: Microsoft Azure (VM Ubuntu)

⚙️ Configuração do Ambiente
Pré-requisitos
Docker (Instalação)

Docker Compose (Instalação)

JDK 17+ (Download)

Maven (Instalação)

🐳 Execução com Docker
1. Clone o repositório
bash
git clone https://github.com/Pablo0703/java_global_solution.git
cd java_global_solution
2. Configure as variáveis de ambiente
Edite o arquivo .env (ou crie um):

bash
DB_URL=jdbc:postgresql://postgres-container:5432/globaldb
DB_USERNAME=rm556834
DB_PASSWORD=070301
3. Construa e execute os containers
bash
docker-compose up --build -d
4. Verifique os logs
bash
docker-compose logs -f
5. Acesse a aplicação
API: http://localhost:8080

Banco de Dados:

bash
docker exec -it postgres-container psql -U rm556834 -d globaldb
📂 Estrutura do Projeto
java_global_solution/
├── src/                     # Código-fonte Java
├── target/                  # Build da aplicação (gerado pelo Maven)
├── docker-compose.yml       # Configuração dos containers
├── Dockerfile               # Definição da imagem Docker da aplicação
├── .env                     # Variáveis de ambiente
└── README.md                # Documentação
🔍 Testes e Validação
Teste o CRUD via curl
bash
# Criar (POST)
curl -X POST http://localhost:8080/api/items -H "Content-Type: application/json" -d '{"name":"Exemplo"}'

# Listar (GET)
curl http://localhost:8080/api/items

# Atualizar (PUT)
curl -X PUT http://localhost:8080/api/items/1 -H "Content-Type: application/json" -d '{"name":"Atualizado"}'

# Deletar (DELETE)
curl -X DELETE http://localhost:8080/api/items/1
Verifique persistência no PostgreSQL
bash
docker exec -it postgres-container psql -U rm556834 -d globaldb -c "SELECT * FROM items;"
📌 Regras do Projeto (Atendidas)
✅ 2 Containers Integrados (App Java + PostgreSQL)
✅ Dockerfile personalizado (com usuário não-root)
✅ Variáveis de ambiente configuradas
✅ Persistência de dados (Volume Docker)
✅ CRUD completo + logs via terminal
✅ Vídeo demonstrativo (explicando cada etapa)

📜 Licença
Este projeto está sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

📧 Contato
Aluno: Pablo Silva
RM: 556834
Aluno: Diego Santos
RM: 558711
Aluno: Vinicius Leopoldino
RM: 557047
FIAP - DevOps Tools & Cloud Computing

🔗 Links Úteis
Documentação Docker

Documentação PostgreSQL

Azure Cloud

🎯 Observação: Este projeto foi desenvolvido em uma VM Azure (Ubuntu 22.04) seguindo as especificações da disciplina.
⚠️ Aviso: Não utilize o Docker Desktop para evidências (apenas terminal).

📌 Dúvidas? Abra uma issue no repositório! 🚀
