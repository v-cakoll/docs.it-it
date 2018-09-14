---
title: Problemi noti in SqlClient per Entity Framework
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: c1353444415ddd2305a73d14bacf1bb33a931929
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597485"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Problemi noti in SqlClient per Entity Framework
Questa sezione descrive i problemi noti relativi al provider di dati .NET Framework per SQL Server.  
  
## <a name="trailing-spaces-in-string-functions"></a>Spazi finali nelle funzioni di stringa  
 SQL Server vengono ignorati gli spazi finali nei valori stringa. Il passaggio degli spazi finali nella stringa può pertanto generare risultati imprevedibili e persino errori.  
  
 Se è necessario avere gli spazi finali nella stringa, è consigliabile aggiungere un carattere di spazio vuoto alla fine, in modo che SQL Server non Taglia la stringa. Se gli spazi finali non sono richiesti, devono essere tagliati prima di essere passati alla pipeline della query.  
  
## <a name="right-function"></a>Funzione RIGHT  
 Se viene passato un valore non `null` come primo argomento e 0 come secondo argomento a `RIGHT(nvarchar(max)`, 0`)` o `RIGHT(varchar(max)`, 0`)`, verrà restituito un valore `NULL` anziché una stringa `empty`.  
  
## <a name="cross-and-outer-apply-operators"></a>Operatori CROSS e OUTER APPLY  
 Gli operatori CROSS e OUTER APPLY sono stati introdotti in [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]. In alcuni casi, è possibile che la pipeline della query produca un'istruzione Transact-SQL contenente gli operatori CROSS APPLY e/o OUTER APPLY. Poiché alcuni provider di back-end, incluse le versioni di SQL Server precedenti a [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], questi operatori non sono supportati, tali query non possono essere eseguite su questi provider di back-end.  
  
 Gli elementi seguenti rappresentano alcuni scenari tipici che potrebbero produrre operatori CROSS APPLY e/o OUTER APPLY nella query di output:  
  
-   Una subquery correlata con paging.  
  
-   Un oggetto `AnyElement` su una sottoquery correlata o su una raccolta prodotta dalla navigazione.  
  
-   Query LINQ che usano metodi di raggruppamento che accettano un selettore elemento.  
  
-   Una query in cui è specificato in modo esplicito un operatore CROSS APPLY o OUTER APPLY.  
  
-   Una query che presenta un costrutto DEREF su un costrutto REF.  
  
## <a name="skip-operator"></a>Operatore SKIP  
 Se si usa [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)], uso di SKIP con ORDER BY in colonne non chiave potrebbe restituire risultati non corretti. Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato. Questo comportamento è dovuto alla modalità di conversione di SKIP per [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]. Ad esempio, nella query seguente, più di cinque righe potrebbero essere ignorate se `E.NonKeyColumn` sono presenti valori duplicati:  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Utilizzo della versione di SQL Server corretta  
 Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] destinazioni il [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] in base alla versione di SQL Server specificato nella query il `ProviderManifestToken` attributo dell'elemento dello Schema nel file di modello (con estensione SSDL) di archiviazione. Tale versione potrebbe differire dalla versione effettiva di SQL Server a cui si è connessi. Se, ad esempio, si utilizza SQL Server 2005, ma l'attributo `ProviderManifestToken` è impostato su 2008, la query [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] generata potrebbe non essere eseguita sul server. Una query che utilizza ad esempio i nuovi tipi datetime introdotti in SQL Server 2008 non verrà eseguita sulle versioni precedente di SQL Server. Se si usa SQL Server 2005, ma il `ProviderManifestToken` attributo è impostato su 2000, generato [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] query potrebbe essere meno ottimizzata o si verifichi un'eccezione che indica che la query non è supportata. Per altre informazioni, vedere la sezione applica gli operatori CROSS e OUTER, più indietro in questo argomento.  
  
 Determinati comportamenti del database dipendono dal livello di compatibilità impostato per il database. Se l'attributo `ProviderManifestToken` è impostato su 2005 e si usa la versione 2005 di SQL Server, ma il livello di compatibilità di un database è impostato su "80" (SQL Server 2000), il codice [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] generato avrà come destinazione SQL Server 2005, ma potrebbe non essere eseguito nel modo previsto a causa dell'impostazione del livello di compatibilità. Se, ad esempio, un nome di colonna nell'elenco ORDER BY corrisponde a un nome di colonna nel selettore, può verificarsi la perdita delle informazioni sugli ordini.  
  
## <a name="nested-queries-in-projection"></a>Query annidate nella proiezione  
 Le query annidate in una clausola di proiezione potrebbero essere tradotte in query di un prodotto cartesiano sul server. In alcuni server back-end, tra cui Server SLQ, questo può causare la tabella di database TempDB assumere dimensioni notevoli. con una conseguente riduzione della prestazione del server.  
  
 Di seguito è riportato un esempio di query annidata in una clausola di proiezione:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Valori Identity GUID generati dal server  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta valori di identità del tipo GUID generati dal server, ma il provider deve supportare la restituzione del valore di identità generato dal server dopo l'inserimento di una riga. A partire da SQL Server 2005, è possibile restituire il tipo GUID generati dal server in un database di SQL Server tramite il [clausola OUTPUT](https://go.microsoft.com/fwlink/?LinkId=169400) .  
  
## <a name="see-also"></a>Vedere anche  
 [SqlClient per Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)  
 [Problemi noti e considerazioni in LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)
