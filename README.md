# ✅ SOLUÇÃO COMPLETA: DIO - Trilha .NET - API e Entity Framework

## Contexto do Desafio
O objetivo desta atividade foi construir um sistema gerenciador de tarefas (To-Do List) com a implementação de todos os métodos **CRUD** (Create, Read, Update, Delete) e filtros de busca, utilizando **ASP  .NET Core** e **Entity Framework Core**. 

---

## 🛠️ Solução Implementada

O projeto foi concluído implementando a totalidade dos endpoints esperados e configurando a persistência de dados.

### 1. Modelo de Dados

A classe principal implementada no projeto é `Tarefa`, conforme o diagrama:

| Propriedade | Tipo | Descrição |
| :--- | :--- | :--- |
| `Id` | `int` | Chave primária (PK). |
| `Titulo` | `string` | Título da Tarefa. |
| `Descricao` | `string` | Detalhes da Tarefa. |
| `Data` | `DateTime` | Data e hora de agendamento. |
| `Status` | `EnumStatusTarefa` | Status atual da tarefa (Pendente, Finalizado, etc.). |

### 2. Configuração do Banco de Dados

* **Tecnologia:** SQL Server (Instalado diretamente no ambiente Linux Mint).
* **Persistência:** Entity Framework Core (Geradas e aplicadas as Migrations para a criação da tabela `Tarefa`).
* **String de Conexão:** A conexão foi configurada em `appsettings.json`, usando o formato para conexão com o SQL Server no Linux:

```json
"ConnectionStrings": {
  "ConexaoPadrao": "Server=localhost,1433;Database=Agenda;User Id=sa;Password=0351Dede;TrustServerCertificate=True;"
}
```


📊 Endpoints e Resultados dos Testes (Swagger UI)

```   
Todos os endpoints na TarefaController foram implementados, testados via Swagger UI e retornaram o status HTTP esperado.

Verbo	    Endpoint	    Parâmetro	        Ação	            Status Esperado	              Status Obtido

POST	    /Tarefa	          N/A	    Cria uma nova tarefa.	    201 Created	                    ✅ 201

GET	    /Tarefa/{id}	       id	    Lê a tarefa pelo ID.	    200 OK	                        ✅ 200

PUT	     /Tarefa/{id}	       id	     Atualiza a tarefa.	      200 OK	                        ✅ 200

DELETE	/Tarefa/{id}	       id	      Deleta a tarefa.	      204 No                          ✅ 204

GET	    /Tarefa/ObterTodos	N/A	    Lista todas as tarefas.	  200 OK	                        ✅ 200

GET	 /Tarefa/ObterPorTitulo	titulo	 Filtra por título        200 OK	                        ✅ 200

GET	/Tarefa/ObterPorData	  data	    Filtra por data.	      200 OK	                        ✅ 200

GET	/Tarefa/ObterPorStatus	status	  Filtra por status       200 OK	                        ✅ 200
```

