# Tipos-de-Servico-de-Nuvem---Laboratorio

📌 Resumo Detalhado – Criação de Instância Gerenciada de SQL do Azure
🔑 O que é

Azure SQL Managed Instance é um serviço de banco de dados em nuvem que oferece quase 100% de compatibilidade com o SQL Server (Enterprise Edition).

É totalmente gerenciado pela Microsoft e combina funcionalidades do SQL Server com a flexibilidade da nuvem.

✅ Pré-requisitos

Ter uma assinatura do Azure (pode ser gratuita).

Permissões necessárias:

Função de Contribuidor da Instância Gerenciada de SQL.

Caso a sub-rede já esteja delegada, basta a permissão Microsoft.Sql/managedInstances/write.

Ter o módulo Az.SQL atualizado (PowerShell) ou a versão mais recente da Azure CLI.

Conferir regiões e tipos de assinatura compatíveis.

⚙️ Criando a Instância (Portal do Azure, PowerShell ou CLI)
📍 Passos no Portal do Azure

Entrar no Portal do Azure.

Acessar SQL do Azure → + Criar → Instâncias Gerenciadas de SQL.

Selecionar Criar Instância Gerenciada de SQL.

📝 Configurações da Instância
1. Guia Básico

Assinatura → escolha sua conta.

Grupo de recursos → novo ou existente.

Nome da instância → deve seguir regras de nomenclatura do Azure.

Região → escolha a região de hospedagem.

Pool de instâncias → opcional.

Método de autenticação → SQL (para início rápido; recomendável usar Microsoft Entra ID para mais segurança).

Admin/usuário e senha → senha com no mínimo 16 caracteres.

2. Computação + Armazenamento

Camada de serviço → Uso Geral (padrão, indicado para maioria dos cenários).

Geração de hardware → Standard (Gen 5).

vCores → defina de acordo com sua necessidade (8 vCores padrão).

Armazenamento (GB) → conforme o tamanho esperado dos dados.

Licenciamento → pagamento por uso ou Azure Hybrid Benefit.

Redundância de backup → geográfica (padrão, recomendado).

3. Guia Rede

Rede virtual/sub-rede → crie ou use existente.

Tipo de conexão → depende do caso de uso.

Ponto de extremidade público → desabilitado (recomendado por segurança).

Acesso → pode ser configurado como Serviços do Azure, Internet (teste) ou Sem acesso (mais restritivo).

4. Guia Segurança

Mantida com valores padrão (pode personalizar depois).

5. Configurações Adicionais

Ordenação → deve ser compatível com os bancos existentes.

Fuso horário → define operações e logs.

Replicação geográfica → desabilitada, a menos que queira failover secundário.

Janela de manutenção → define período para updates automáticos.

6. Marcas (Tags)

Importante para organização e relatórios de custo.

Ex.: Proprietário, Ambiente (Produção/Dev/Teste).

📊 Finalização

Examinar + Criar → revisar as escolhas → clicar em Criar.

Acompanhar pelo ícone de Notificações.

Se perder a tela, pode monitorar via Visão Geral no portal, PowerShell ou CLI.

🔐 Revisar Configurações de Rede

Verificar tabela de rotas e regras de segurança.

Se o ponto de extremidade público foi habilitado, liberar as portas necessárias para acesso externo.

🗄️ Criar um Banco de Dados

Dentro da instância: + Novo banco de dados.

Definir:

Nome.

Fonte de dados (nenhuma → vazio, ou restauração via backup).

Finalizar em Revisar + Criar.

🔗 Recuperar detalhes de conexão

No portal, em Visão Geral da instância, copiar o Host/FQDN.

Exemplo de endereço:

nomedainstancia.a1b2c3d4e5f6.database.windows.net


Usado para conectar aplicações ou o SQL Server Management Studio (SSMS).

📚 Conteúdo Relacionado

Configurar VMs do Azure.

Migrar de SQL Server local para SQL Managed Instance.

Configurar ponto a site.

Monitorar com Database Watcher.

Restaurar bancos usando Azure Database Migration Service ou RESTORE T-SQL.

🔮 Próximos Passos

Conectar aplicações à instância.

Explorar observabilidade e segurança.

Praticar migração de dados do SQL Server local para a nuvem.
