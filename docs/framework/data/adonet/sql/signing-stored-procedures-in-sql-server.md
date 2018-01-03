---
title: Firma di stored procedure in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b3d90579e28fde40d461bdb511d797e5d7f6f179
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firma di stored procedure in SQL Server
È possibile firmare una stored procedure con un certificato o una chiave asimmetrica. Le firme sono progettate per scenari in cui le autorizzazioni non possono essere ereditate tramite il concatenamento della proprietà oppure in cui la catena di proprietà è interrotta, come nel caso delle istruzioni SQL dinamiche. Viene quindi eseguito il mapping di un utente creato al certificato e vengono concesse le autorizzazioni dell'utente del certificato sugli oggetti cui la stored procedure deve accedere.  
  
 Durante l'esecuzione della stored procedure, SQL Server combina le autorizzazioni dell'utente del certificato con quelle del chiamante. A differenza della clausola EXECUTE AS, il contesto di esecuzione della stored procedure non viene modificato. Le funzioni predefinite che restituiscono i nomi di accesso e i nomi utente restituiscono il nome del chiamante e non il nome dell'utente del certificato.  
  
 Un firma digitale è un digest di dati crittografato con la chiave privata del firmatario. La chiave privata garantisce che la firma digitale è univoca per il titolare o il proprietario. È possibile usare la firma per stored procedure, funzioni o trigger.  
  
> [!NOTE]
>  Per concedere autorizzazioni a livello di server, è possibile creare un certificato nel database master.  
  
## <a name="creating-certificates"></a>Creazione di certificati  
 Quando si firma una stored procedure con un certificato, viene usata la chiave privata per creare un digest di dati costituito dall'hash crittografato del codice della stored procedure code. In fase di esecuzione il digest di dati viene decrittografato usando la chiave pubblica e confrontato con il valore hash della stored procedure. La modifica della stored procedure invalida il valore hash, annullando di fatto la corrispondenza della firma digitale. In tal modo si impedisce che un utente che non disponga di accesso alla chiave privata possa modificare il codice della stored procedure. È pertanto necessario firmare nuovamente la procedura ogni volta che viene modificata.  
  
 La firma di un modulo è un processo in quattro passaggi:  
  
1.  Creazione di un certificato tramite l'istruzione `CREATE CERTIFICATE [certificateName]` Transact-SQL. Questa istruzione prevede diverse opzioni per l'impostazione di una data di inizio e una data di fine, nonché di una password. La data di scadenza predefinita è pari a un anno.  
  
2.  Creazione di un utente del database associato al certificato tramite l'istruzione `CREATE USER [userName] FROM CERTIFICATE [certificateName]` Transact-SQL. Questo utente esiste solo nel database e non è associato a un account di accesso.  
  
3.  Concessione delle autorizzazioni necessarie sugli oggetti di database all'utente del certificato.  
  
> [!NOTE]
>  Un certificato non può concedere autorizzazioni a un utente al quale sono state revocate autorizzazioni usando l'istruzione DENY. DENY ha sempre la precedenza su GRANT e impedisce al chiamante di ereditare autorizzazioni concesse all'utente del certificato.  
  
1.  Firma della stored procedure con il certificato tramite l'istruzione `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` Transact-SQL.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Firma del modulo](http://go.microsoft.com/fwlink/?LinkId=98590) nella documentazione Online di SQL Server|Viene descritta la procedura di firma dei moduli e vengono forniti uno scenario di esempio e collegamenti agli argomenti Transact-SQL attinenti.|  
|[Stored procedure con un certificato di firma](http://msdn.microsoft.com/library/bb283630.aspx) nella documentazione Online di SQL Server|Viene fornita un'esercitazione per firmare una stored procedure con un certificato.|  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Cenni preliminari sulla sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Gestione delle autorizzazioni con stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Scrittura dinamica sicura in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Personalizzazione delle autorizzazioni con rappresentazione in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Modifica di dati con stored procedure](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
