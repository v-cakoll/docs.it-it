---
title: Provider EntityClient per Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: 70cc5a9aaa22cc563c910f9d250ad4565e34a135
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251594"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Provider EntityClient per Entity Framework
EntityClient è un provider di dati usato dalle applicazioni Entity Framework per accedere a dati descritti in un  modello concettuale. Per informazioni sui modelli concettuali, vedere [modellazione e mapping](modeling-and-mapping.md). EntityClient usa altri provider di dati .NET Framework per accedere all'origine dati, ad esempio il provider di dati .NET Framework per SQL Server (SqlClient) in caso di accesso a un database SQL Server. Per informazioni sul provider SqlClient, vedere [SqlClient per la Entity Framework](sqlclient-for-the-entity-framework.md). Il provider EntityClient viene implementato nello spazio dei nomi <xref:System.Data.EntityClient>.  
  
## <a name="managing-connections"></a>Gestione di connessioni  
 Si basa su provider di dati ADO.NET specifici dell'archiviazione fornendo un oggetto <xref:System.Data.EntityClient.EntityConnection> a un provider di dati e a un database relazionale sottostanti. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Per costruire un <xref:System.Data.EntityClient.EntityConnection> oggetto, è necessario fare riferimento a un set di metadati che contiene i modelli e il mapping necessari e anche un nome di provider di dati e una stringa di connessione specifici per l'archiviazione. Una volta <xref:System.Data.EntityClient.EntityConnection> che l'oggetto è disponibile, è possibile accedere alle entità tramite le classi generate dal modello concettuale.  
  
 È possibile specificare una stringa di connessione nel file app.config.  
  
 <xref:System.Data.EntityClient> include anche la classe <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Questa classe consente agli sviluppatori di creare a livello di codice stringhe di connessione sintatticamente corrette, nonché di analizzare e ricompilare le stringhe di connessione esistenti, usando le proprietà e i metodi della classe. Per altre informazioni, vedere [Procedura: Compilare una stringa](how-to-build-an-entityconnection-connection-string.md)di connessione EntityConnection.  
  
## <a name="creating-queries"></a>Creazione di query  
 Il [!INCLUDE[esql](../../../../../includes/esql-md.md)] linguaggio è un sottolinguaggio SQL indipendente dall'archiviazione che interagisce direttamente con gli schemi di entità concettuali e supporta Entity Data Model concetti quali l'ereditarietà e le relazioni. La <xref:System.Data.EntityClient.EntityCommand> classe viene utilizzata per eseguire un [!INCLUDE[esql](../../../../../includes/esql-md.md)] comando su un modello di entità. Quando si costruiscono oggetti <xref:System.Data.EntityClient.EntityCommand>, è possibile specificare un nome di stored procedure o un testo della query. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] funziona con provider di dati specifici dell'archiviazione per convertire il linguaggio [!INCLUDE[esql](../../../../../includes/esql-md.md)] generico in query specifiche dell'archiviazione. Per ulteriori informazioni sulla scrittura [!INCLUDE[esql](../../../../../includes/esql-md.md)] di query, vedere [linguaggio Entity SQL](./language-reference/entity-sql-language.md).  
  
 Nell'esempio seguente viene creato <xref:System.Data.EntityClient.EntityCommand> un oggetto e viene assegnato [!INCLUDE[esql](../../../../../includes/esql-md.md)] un testo della query <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> alla relativa proprietà. Questa [!INCLUDE[esql](../../../../../includes/esql-md.md)] query richiede i prodotti ordinati in base al prezzo di listino dal modello concettuale. Il codice seguente non comporta alcuna conoscenza del modello di archiviazione.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Esecuzione di query  
 Quando una query viene eseguita, viene analizzata e convertita in un albero dei comandi canonici. Tutte le elaborazioni successive vengono eseguite nell'albero dei comandi. L'albero dei comandi è il mezzo di comunicazione tra <xref:System.Data.EntityClient> e il provider di dati .NET Framework sottostante, <xref:System.Data.SqlClient>ad esempio.  
  
 <xref:System.Data.EntityClient.EntityDataReader> espone i risultati dell'esecuzione di un oggetto <xref:System.Data.EntityClient.EntityCommand> su un modello concettuale. Per eseguire il comando che restituisce <xref:System.Data.EntityClient.EntityDataReader>, chiamare <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>. <xref:System.Data.EntityClient.EntityDataReader> implementa <xref:System.Data.IExtendedDataRecord> per descrivere risultati completamente strutturati.  
  
## <a name="managing-transactions"></a>Gestione di transazioni  
 In Entity Framework è possibile usare le transazioni in modo esplicito e in modo automatico. Le transazioni automatiche usano lo spazio dei nomi <xref:System.Transactions> e le transazioni esplicite usano la classe <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Per aggiornare i dati esposti tramite un modello concettuale, vedere [procedura: Gestire le transazioni nel Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Compilare una stringa di connessione EntityConnection](how-to-build-an-entityconnection-connection-string.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di PrimitiveType](how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di StructuralType](how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di RefType](how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Procedura: Eseguire una query che restituisce tipi complessi](how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedura: Eseguire una query che restituisce raccolte annidate](how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Procedura: Eseguire una query di Entity SQL con parametri utilizzando EntityCommand](how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Procedura: Eseguire una stored procedure con parametri tramite EntityCommand](how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Procedura: Eseguire una query polimorfica](how-to-execute-a-polymorphic-query.md)  
  
 [Procedura: Esplorare le relazioni con l'operatore Navigate](how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>Vedere anche

- [Gestione delle connessioni e delle transazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [ADO.NET Entity Framework](index.md)
- [Riferimenti per il linguaggio](./language-reference/index.md)
