# Banco-de-Dados-Azure

# Configuração de uma Instância de Banco de Dados no Microsoft Azure


## 1. Pré-requisitos
- Conta do Azure ;
- Acesso ao portal Azure (https://portal.azure.com);
- Definir qual serviço de banco de dados será usado (Azure SQL Database, MySQL, PostgreSQL, Cosmos DB, etc.).

## 2. Criando um Banco de Dados Azure SQL (exemplo)

  Passo 1: Acessar o Portal Azure
  - Faça login no portal Azure (https://portal.azure.com)

  Passo 2: Criar o recurso
  1. Clique em "Criar um recurso" (+)
  2. Selecione "Bancos de Dados" > "SQL Database"

  Passo 3: Configurar o banco de dados
  1. **Detalhes do projeto**:
   - Selecione a assinatura
   - Crie ou selecione um grupo de recursos

  2. **Detalhes do banco de dados**:
   - Nome do banco de dados
   - Selecione o servidor (ou crie um novo)
     - Nome do servidor (deve ser globalmente único)
     - Localização
     - Método de autenticação (SQL ou Azure AD)
     - Definir credenciais de administrador
   - Quer usar pool elástico? (Sim/Não)
   - Tipo de computação (Provisionado ou Sem servidor)
   - Camada de serviço (DTU ou vCore)
   - Tamanho do armazenamento

  3. **Rede**:
   - Método de conectividade (Ponto de extremidade público ou Ponto de extremidade privado)
   - Permitir que serviços e recursos do Azure acessem este servidor (Sim/Não)
   - Adicionar endereço IP atual ao firewall

  4. **Segurança** (opcional):
   - Configurar proteção de dados avançada
   - Habilitar Transparent Data Encryption (TDE)

  5. **Configurações adicionais**:
   - Usar fonte de dados existente (backup, banco de dados de exemplo ou vazio)
   - Definir collation (padrão: SQL_Latin1_General_CP1_CI_AS)

  Passo 4: Revisar e criar
  - Revise todas as configurações
  - Clique em "Criar" para provisionar o banco de dados

 ## 3. Pós-configuração
  Conectando ao banco de dados:
   1. Após a implantação, navegue até o recurso
   2. Obtenha a string de conexão em "Cadeias de conexão"
   3. Use ferramentas como:
    - SQL Server Management Studio (SSMS)
    - Azure Data Studio
    - Visual Studio

  Configurações adicionais importantes
  1. **Monitoramento**:
    - Configurar alertas
    - Habilitar Query Performance Insight

  2. **Backup**:
    - Configurar política de retenção de backups
    - Habilitar backups automáticos

  3. **Escala**:
    - Ajustar camada de serviço conforme necessário
    - Configurar escalonamento automático (se aplicável)

 ## 4. Melhores práticas
   - Sempre use regras de firewall para restringir acesso
  - Considere usar Private Link para conexões mais seguras
   - Monitore regularmente o desempenho e custos
   - Implemente tags para organização e gerenciamento de custos

Para outros tipos de banco de dados (MySQL, PostgreSQL, Cosmos DB), o processo é similar, com variações nas opções específicas de cada serviço.
