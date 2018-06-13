---
title: Abilitazione dell'accesso tra database in SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 22fa2b48d795fb81b4740ce882f9bff632deabbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353462"
---
# <a name="enabling-cross-database-access-in-sql-server"></a>Abilitazione dell'accesso tra database in SQL Server
Il concatenamento della proprietà tra database si verifica quando una procedura di un database dipende dagli oggetti di un altro. Una catena di proprietà tra database funziona allo stesso modo del concatenamento della proprietà con un singolo database, ad eccezione del fatto che una catena di proprietà non interrotta richiede che tutti i proprietari degli oggetti siano mappati allo stesso account di accesso. Se l'oggetto di origine nel database di origine e gli oggetti di destinazione nei database di destinazione appartengono allo stesso account di accesso, le autorizzazioni sugli oggetti di destinazione non verranno controllate in SQL Server.  
  
## <a name="off-by-default"></a>Disattivazione per impostazione predefinita  
 Il concatenamento della proprietà tra database è disattivato per impostazione predefinita. Microsoft consiglia di disabilitare questa funzionalità perché espone la sicurezza ai seguenti rischi:  
  
-   I proprietari dei database e i membri dei ruoli di database `db_ddladmin` o `db_owners` possono creare oggetti appartenenti ad altri utenti. Questi oggetti possono avere come destinazione gli oggetti di altri database, il che significa che se si abilita il concatenamento della proprietà tra database, è necessario considerare completamente attendibili questi utenti per i dati di tutti i database.  
  
-   Gli utenti con l'autorizzazione CREATE DATABASE possono creare nuovi database e collegare database esistenti. Se il concatenamento della proprietà tra database è abilitato, questi utenti possono accedere ad oggetti di altri database per cui potrebbero non disporre di privilegi dai database appena creati o collegati.  
  
## <a name="enabling-cross-database-ownership-chaining"></a>Abilitazione del concatenamento della proprietà tra database  
 Il concatenamento della proprietà tra database deve essere abilitato solo negli ambienti in cui gli utenti con privilegi elevati possono essere considerati completamente attendibili. Questa funzionalità può essere configurata durante l'installazione per tutti i database o in modo selettivo per specifici database usando i comandi [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `sp_configure` e `ALTER DATABASE`.  
  
 Per configurare in modo selettivo questa funzionalità, usare `sp_configure` per disattivarla per il server. Usare quindi il comando ALTER DATABASE con SET DB_CHAINING ON per configurare il concatenamento della proprietà tra database solo per i database per cui è necessario.  
  
 Nell'esempio seguente si attiva il concatenamento della proprietà tra database per tutti i database:  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 Nell'esempio seguente si attiva il concatenamento della proprietà tra database per database specifici:  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>SQL dinamico  
 Il concatenamento della proprietà tra database non funziona nei casi in cui vengono eseguite istruzioni SQL create in modo dinamico, a meno che nei due database non esistano gli stessi utenti. È possibile risolvere il problema in SQL Server creando una stored procedure che accede ai dati in un altro database e firmare la procedura con un certificato esistente in entrambi i database. In questo modo si fornisce agli utenti l'accesso alle risorse del database usate dalla procedura senza concedere loro l'accesso o le autorizzazioni per il database.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Estensione della rappresentazione di Database tramite EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) e [Cross DB Ownership Chaining-opzione](http://msdn.microsoft.com/library/ms188694.aspx)documentazione Online di SQL Server.|Negli argomenti viene descritto come configurare tra database concatenamento della proprietà per un'istanza di SQL Server.|  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Cenni preliminari sulla sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Gestione delle autorizzazioni con stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Scrittura dinamica sicura in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Firma di stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
