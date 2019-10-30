---
title: Autenticazione in SQL Server
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 09f7825fd6b4f852b24142ea297c078bd8a1e221
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040275"
---
# <a name="authentication-in-sql-server"></a>Autenticazione in SQL Server
In SQL Server sono supportate due modalità di autenticazione: la modalità dell'autenticazione di Windows e la modalità mista.  
  
- L'autenticazione di Windows è l'impostazione predefinita e viene spesso definita sicurezza integrata perché questo modello di sicurezza di SQL Server è strettamente integrato con Windows. Determinati account utente e gruppi di Windows vengono considerati attendibili per l'accesso a SQL Server. Gli utenti di Windows che sono già stati autenticati non devono presentare credenziali aggiuntive.  
  
- La modalità mista supporta l'autenticazione di Windows e quella di SQL Server. Le coppie di nome utente e password vengono mantenute in SQL Server.  
  
> [!IMPORTANT]
> Se possibile, si consiglia di usare l'autenticazione di Windows. In questa modalità viene utilizzata una serie di messaggi crittografati per autenticare gli utenti in SQL Server. Quando vengono usati SQL Server account di accesso, SQL Server i nomi di accesso e le password crittografate vengono passati attraverso la rete, rendendoli meno sicuri.  
  
 Con l'autenticazione di Windows, gli utenti sono già connessi a Windows e non devono eseguire separatamente l'accesso a SQL Server. Il `SqlConnection.ConnectionString` seguente specifica l'autenticazione di Windows senza richiedere agli utenti di specificare un nome utente o una password.  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> Gli account di accesso sono distinti dagli utenti del database. È necessario eseguire il mapping degli account di accesso o gruppi di Windows agli utenti o ruoli del database in un'operazione separata. È quindi possibile concedere le autorizzazioni agli utenti o ai ruoli per l'accesso agli oggetti di database.  
  
## <a name="authentication-scenarios"></a>Scenari di autenticazione  
 L'autenticazione di Windows risulta in genere la soluzione ideale nelle seguenti situazioni:  
  
- È presente un controller di dominio.  
  
- L'applicazione e il database si trovano nello stesso computer.  
  
- Si sta utilizzando un'istanza di SQL Server Express o del database locale.  
  
 Gli account di accesso di SQL Server vengono in genere usati nelle seguenti situazioni:  
  
- Si dispone di un gruppo di lavoro.  
  
- Gli utenti si connettono da domini diversi, non attendibili.  
  
- Applicazioni Internet, ad esempio ASP.NET.  
  
> [!NOTE]
> Se si specifica l'autenticazione di Windows, gli account di accesso di SQL Server non vengono disabilitati. Utilizzare l'istruzione Transact-SQL ALTER LOGIN DISABLE per disabilitare gli account di accesso di SQL Server con privilegi elevati.  
  
## <a name="login-types"></a>Tipi di account di accesso  
 SQL Server supporta tre tipi di account di accesso:  
  
- Account utente di Windows locale o account di dominio attendibile. SQL Server si affida a Windows per l'autenticazione degli account utente di Windows.  
  
- Gruppo di Windows. L'accesso concesso a un gruppo di Windows viene assegnato a tutti gli account di accesso degli utenti di Windows che sono membri di tale gruppo.  
  
- Account di accesso di SQL Server. In SQL Server sia il nome utente che un hash della password vengono archiviati nel database master, utilizzando metodi di autenticazione interni per verificare i tentativi di accesso.  
  
> [!NOTE]
> SQL Server fornisce gli account di accesso creati da certificati o chiavi asimmetriche utilizzate solo per la firma del codice. che non possono essere utilizzati per la connessione a SQL Server.  
  
## <a name="mixed-mode-authentication"></a>Autenticazione in modalità mista  
 Se è necessario utilizzare l'autenticazione in modalità mista, occorre creare account di accesso di SQL Server, che vengono archiviati in SQL Server. È quindi necessario specificare il nome utente e la password di SQL Server in fase di esecuzione.  
  
> [!IMPORTANT]
> SQL Server viene installato con un account di accesso denominato `sa` (abbreviazione di "system administrator"). Assegnare una password complessa all'account di accesso `sa` e non usare l'account di accesso `sa` nell'applicazione. L'account di accesso `sa` viene mappato al ruolo predefinito del server `sysadmin`, che dispone di credenziali amministrative irrevocabili nell'intero server. Non esistono limiti ai danni che potrebbero verificarsi se un utente non autorizzato ottiene accesso come amministratore di sistema. Per impostazione predefinita, tutti i membri del gruppo `BUILTIN\Administrators` di Windows (il gruppo di amministratori locali) sono membri del ruolo `sysadmin`, ma possono essere rimossi da tale ruolo.  
  
 SQL Server fornisce i meccanismi di criteri password di Windows per SQL Server account di accesso quando viene eseguito in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] o versioni successive. I criteri di complessità delle password sono progettati per fungere da deterrente agli attacchi a forza bruta aumentando il numero di password possibili. SQL Server possibile applicare gli stessi criteri di complessità e scadenza usati in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] alle password usate all'interno SQL Server.  
  
> [!IMPORTANT]
> La concatenazione di stringhe di connessione dall'input dell'utente può lasciare il sistema vulnerabile a un attacco injection alle stringhe di connessione. Usare <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per creare stringhe di connessione sintatticamente valide in fase di esecuzione. Per altre informazioni, vedere [Compilatori di stringhe di connessione](../connection-string-builders.md).  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le seguenti risorse.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Entità](/sql/relational-databases/security/authentication-access/principals-database-engine)|Vengono descritti gli account di accesso e altre entità di sicurezza in SQL Server.|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Connessione a un'origine dati](../connecting-to-a-data-source.md)
- [Stringhe di connessione](../connection-strings.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
