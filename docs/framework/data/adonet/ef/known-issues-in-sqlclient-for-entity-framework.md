---
title: Problemi noti in SqlClient per Entity Framework
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: 32a1dd22111498ab5b3b75940f5485b2957367e8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452500"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Problemi noti in SqlClient per Entity Framework
Questa sezione descrive i problemi noti relativi al provider di dati .NET Framework per SQL Server.  
  
## <a name="trailing-spaces-in-string-functions"></a>Spazi finali nelle funzioni di stringa  
 SQL Server ignora gli spazi finali nei valori stringa. Il passaggio degli spazi finali nella stringa può pertanto generare risultati imprevedibili e persino errori.  
  
 Se è necessario disporre di spazi finali nella stringa, è consigliabile aggiungere un carattere di spazio vuoto alla fine, in modo che SQL Server non Ritaglia la stringa. Se gli spazi finali non sono richiesti, devono essere tagliati prima di essere passati alla pipeline della query.  
  
## <a name="right-function"></a>Funzione RIGHT  
 Se viene passato un valore non `null` come primo argomento e 0 come secondo argomento a `RIGHT(nvarchar(max)`, 0`)` o `RIGHT(varchar(max)`, 0`)`, verrà restituito un valore `NULL` anziché una stringa `empty`.  
  
## <a name="cross-and-outer-apply-operators"></a>Operatori CROSS e OUTER APPLY  
 Gli operatori CROSS e OUTER APPLY sono stati introdotti nella SQL Server 2005. In alcuni casi, è possibile che la pipeline della query produca un'istruzione Transact-SQL contenente gli operatori CROSS APPLY e/o OUTER APPLY. Poiché alcuni provider back-end, incluse le versioni di SQL Server precedenti SQL Server 2005, non supportano questi operatori, tali query non possono essere eseguite su questi provider back-end.  
  
 Gli elementi seguenti rappresentano alcuni scenari tipici che potrebbero produrre operatori CROSS APPLY e/o OUTER APPLY nella query di output:  
  
- Una subquery correlata con paging.  
  
- Un oggetto `AnyElement` su una sottoquery correlata o su una raccolta prodotta dalla navigazione.  
  
- Query LINQ che usano metodi di raggruppamento che accettano un selettore elemento.  
  
- Una query in cui è specificato in modo esplicito un operatore CROSS APPLY o OUTER APPLY.  
  
- Una query che presenta un costrutto DEREF su un costrutto REF.  
  
## <a name="skip-operator"></a>Operatore SKIP  
 Se si usa SQL Server 2000, l'uso di SKIP con ORDER BY in colonne non chiave potrebbe restituire risultati non corretti. Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato. Ciò è dovuto alla modalità di conversione di SKIP per SQL Server 2000. Nella query seguente, ad esempio, potrebbero essere ignorate più di cinque righe se `E.NonKeyColumn` presenta valori duplicati:  
  
```sql  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Utilizzo della versione di SQL Server corretta  
 Il Entity Framework è destinato alla query Transact-SQL basata sulla versione SQL Server specificata nell'attributo `ProviderManifestToken` dell'elemento schema nel file del modello di archiviazione (con estensione ssdl). Tale versione potrebbe differire dalla versione effettiva di SQL Server a cui si è connessi. Se ad esempio si usa SQL Server 2005, ma l'attributo `ProviderManifestToken` è impostato su 2008, la query Transact-SQL generata potrebbe non essere eseguita nel server. Una query che utilizza ad esempio i nuovi tipi datetime introdotti in SQL Server 2008 non verrà eseguita sulle versioni precedente di SQL Server. Se si usa SQL Server 2005, ma l'attributo `ProviderManifestToken` è impostato su 2000, è possibile che la query Transact-SQL generata sia meno ottimizzata o che venga generata un'eccezione che indica che la query non è supportata. Per ulteriori informazioni, vedere la sezione operatori CROSS e OUTER APPLY più indietro in questo argomento.  
  
 Determinati comportamenti del database dipendono dal livello di compatibilità impostato per il database. Se l'attributo `ProviderManifestToken` è impostato su 2005 e la versione del SQL Server è 2005, ma il livello di compatibilità di un database è impostato su "80" (SQL Server 2000), la destinazione di Transact-SQL generata sarà SQL Server 2005, ma potrebbe non essere eseguita come previsto a causa dell'impostazione del livello di compatibilità. Se, ad esempio, un nome di colonna nell'elenco ORDER BY corrisponde a un nome di colonna nel selettore, può verificarsi la perdita delle informazioni sugli ordini.  
  
## <a name="nested-queries-in-projection"></a>Query annidate nella proiezione  
 Le query annidate in una clausola di proiezione potrebbero essere tradotte in query di un prodotto cartesiano sul server. In alcuni server back-end, tra cui SQL Server, questo può causare un notevole numero di dimensioni della tabella TempDB. con una conseguente riduzione della prestazione del server.  
  
 Di seguito è riportato un esempio di query annidata in una clausola di proiezione:  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Valori Identity GUID generati dal server  
 Il Entity Framework supporta i valori di identità del tipo GUID generati dal server, ma il provider deve supportare la restituzione del valore di identità generato dal server dopo l'inserimento di una riga. A partire da SQL Server 2005, è possibile restituire il tipo GUID generato dal server in un database SQL Server tramite la [clausola output](/sql/t-sql/queries/output-clause-transact-sql).
  
## <a name="see-also"></a>Vedere anche

- [SqlClient per Entity Framework](sqlclient-for-the-entity-framework.md)
- [Problemi noti e considerazioni in LINQ to Entities](./language-reference/known-issues-and-considerations-in-linq-to-entities.md)
