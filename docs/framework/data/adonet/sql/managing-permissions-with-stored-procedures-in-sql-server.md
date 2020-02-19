---
title: Gestione delle autorizzazioni con stored procedure in SQL Server
ms.date: 03/30/2017
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
ms.openlocfilehash: 85383c46dd029db825d24d2f67d2dbda00f3bc95
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452383"
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a>Gestione delle autorizzazioni con stored procedure in SQL Server
Per creare più linee di difesa intorno al database, è possibile implementare tutto l'accesso ai dati tramite stored procedure o funzioni definite dall'utente. Revocare o negare tutte le autorizzazioni per gli oggetti sottostanti, ad esempio tabelle, e concedere autorizzazioni EXECUTE sulle stored procedure. In questo modo viene creato un perimetro di sicurezza efficace intorno ai dati e agli oggetti di database.  
  
## <a name="stored-procedure-benefits"></a>Vantaggi delle stored procedure  
 Le stored procedure offrono i vantaggi seguenti:  
  
- La logica dei dati e le regole business possono essere incapsulate in modo tale che gli utenti possano accedere a dati e oggetti soltanto nelle modalità previste dagli sviluppatori e dagli amministratori di database.  
  
- Le stored procedure con parametri che convalidano tutto l'input dell'utente possono essere usate per contrastare gli attacchi SQL injection. Se si usano istruzioni SQL dinamiche, aggiungere parametri ai comandi e non includere mai i valori dei parametri direttamente in una stringa di query.  
  
- È possibile non consentire le query e le modifiche dei dati ad hoc, per impedire agli utenti di eliminare in modo permanente i dati o di eseguire query che compromettono le prestazioni del server o della rete, inavvertitamente o intenzionalmente.  
  
- Gli errori possono essere gestiti nel codice procedurale senza essere passati direttamente alle applicazioni client. In questo modo si impedisce la restituzione di messaggi di errore che potrebbero agevolare un attacco di tipo probe. Registrare gli errori e gestirli sul server.  
  
- Le stored procedure possono essere scritte una sola volta ed essere accessibili a molte applicazioni.  
  
- Le applicazioni client non devono necessariamente riconoscere le strutture dati sottostanti. Il codice delle stored procedure può essere modificato senza richiedere modifiche nelle applicazioni client, purché le modifiche non abbiano effetto sugli elenchi di parametri o sui tipi di dati restituiti.  
  
- Le stored procedure consentono di ridurre il traffico di rete combinando più operazioni in un'unica chiamata di procedura.  
  
## <a name="stored-procedure-execution"></a>Esecuzione delle stored procedure  
 Le stored procedure traggono vantaggio dal concatenamento della proprietà per fornire l'accesso ai dati. In questo modo gli utenti non devono disporre di autorizzazioni esplicite per l'accesso agli oggetti di database. Una catena di proprietà esiste quando gli oggetti che accedono ad altri oggetti in modo sequenziale appartengono allo stesso utente. Ad esempio, una stored procedure può chiamare un'altra stored procedure oppure può accedere a più tabelle. Se tutti gli oggetti nella catena di esecuzione appartengono allo stesso utente, in SQL server viene controllata solo l'autorizzazione EXECUTE del chiamante, non le autorizzazioni per altri oggetti. Pertanto, è necessario concedere solo le autorizzazioni EXECUTE sulle stored procedure e revocare o negare tutte le autorizzazioni per le tabelle sottostanti.  
  
## <a name="best-practices"></a>Procedure consigliate  
 Scrivere stored procedure non è sufficiente per proteggere in modo adeguato l'applicazione. È necessario prendere in considerazione anche i possibili problemi di sicurezza elencati di seguito.  
  
- Concedere autorizzazioni EXECUTE sulle stored procedure per i ruoli del database che si desidera siano in grado di accedere ai dati.  
  
- Revocare o negare tutte le autorizzazioni sulle tabelle sottostanti per tutti i ruoli e gli utenti del database, incluso il ruolo `public`. Tutti gli utenti ereditano le autorizzazioni dal ruolo public. Pertanto, negando le autorizzazioni a `public`, solo i proprietari e i membri `sysadmin` dispongono di accesso, mentre tutti gli altri utenti non saranno in grado di ereditare le autorizzazioni dall'appartenenza ad altri ruoli.  
  
- Non aggiungere utenti o ruoli ai ruoli `sysadmin` o `db_owner`. Gli amministratori di sistema e i proprietari di database possono accedere a tutti gli oggetti di database.  
  
- Disabilitare l'account `guest`. In questo modo gli utenti anonimi non potranno connettersi al database. L'account Guest è disabilitato per impostazione predefinita nei nuovi database.  
  
- Implementare la gestione degli errori e registrare gli errori.  
  
- Creare stored procedure con parametri che convalidano tutto l'input dell'utente. Considerare tutto l'input dell'utente come non attendibile.  
  
- Evitare le istruzioni SQL dinamiche se non sono assolutamente necessarie. Usare la funzione Transact-SQL QUOTENAME() per delimitare un valore di stringa e usare caratteri di escape per tutte le occorrenze del delimitatore nella stringa di input.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le seguenti risorse.  
  
|Resource|Descrizione|  
|--------------|-----------------|  
|[Stored procedure](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) e [SQL injection](/sql/relational-databases/security/sql-injection)|Gli articoli descrivono come creare stored procedure e il funzionamento di SQL injection.|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Cenni preliminari sulla sicurezza in SQL Server](overview-of-sql-server-security.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Scrittura dinamica sicura in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Firma di stored procedure in SQL Server](signing-stored-procedures-in-sql-server.md)
- [Personalizzazione delle autorizzazioni con rappresentazione in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Modifica di dati con stored procedure](../modifying-data-with-stored-procedures.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
