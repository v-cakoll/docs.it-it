---
title: Provider EntityClient per Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4ffb3071e9788ef4442127118c00e23c8a11530b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Provider EntityClient per Entity Framework
EntityClient è un provider di dati usato dalle applicazioni Entity Framework per accedere a dati descritti in un modello concettuale. Per informazioni sui modelli concettuale, vedere [modellazione e Mapping](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md). EntityClient usa altri provider di dati .NET Framework per accedere all'origine dati, ad esempio il provider di dati .NET Framework per SQL Server (SqlClient) in caso di accesso a un database SQL Server. Per informazioni sul provider SqlClient, vedere [SqlClient per Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md). Il provider EntityClient viene implementato nello spazio dei nomi <xref:System.Data.EntityClient>.  
  
## <a name="managing-connections"></a>Gestione di connessioni  
 Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] si basa sulle specifiche dell'archiviazione [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] i provider di dati, fornendo un <xref:System.Data.EntityClient.EntityConnection> a un provider di dati sottostante e un database relazionale. Per costruire un <xref:System.Data.EntityClient.EntityConnection> dell'oggetto, è necessario fare riferimento a un set di metadati che contiene i modelli necessari e i mapping, nonché una stringa di connessione e nome provider dati specifici dell'archiviazione. Dopo il <xref:System.Data.EntityClient.EntityConnection> è sul posto, le entità sono accessibili tramite le classi generate dal modello concettuale.  
  
 È possibile specificare una stringa di connessione nel file app.config.  
  
 <xref:System.Data.EntityClient> include anche la classe <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Questa classe consente agli sviluppatori di creare a livello di codice stringhe di connessione sintatticamente corrette, nonché di analizzare e ricompilare le stringhe di connessione esistenti, usando le proprietà e i metodi della classe. Per ulteriori informazioni, vedere [procedura: compilare una stringa di connessione EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Creazione di query  
 Il [!INCLUDE[esql](../../../../../includes/esql-md.md)] language è un sottolinguaggio indipendente dall'archiviazione di SQL che interagisce direttamente con gli schemi di entità concettuali e supporta i concetti di Entity Data Model, quali l'ereditarietà e le relazioni. Il <xref:System.Data.EntityClient.EntityCommand> classe viene utilizzata per eseguire un [!INCLUDE[esql](../../../../../includes/esql-md.md)] comando su un modello di entità. Quando si costruiscono oggetti <xref:System.Data.EntityClient.EntityCommand>, è possibile specificare un nome di stored procedure o un testo della query. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] funziona con provider di dati specifici dell'archiviazione per convertire il linguaggio [!INCLUDE[esql](../../../../../includes/esql-md.md)] generico in query specifiche dell'archiviazione. Per ulteriori informazioni sulla scrittura [!INCLUDE[esql](../../../../../includes/esql-md.md)] query, vedere [linguaggio Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 Nell'esempio seguente viene creato un <xref:System.Data.EntityClient.EntityCommand> oggetto e assegna un [!INCLUDE[esql](../../../../../includes/esql-md.md)] query testo relativo <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> proprietà. Questo [!INCLUDE[esql](../../../../../includes/esql-md.md)] le richieste di query prodotti ordinati in base al listino prezzi dal modello concettuale. Il codice seguente non comporta alcuna conoscenza del modello di archiviazione.  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## <a name="executing-queries"></a>Esecuzione di query  
 Quando una query viene eseguita, viene analizzata e convertita in una struttura ad albero dei comandi canonici. Tutte le elaborazioni successive vengono eseguite nell'albero dei comandi. L'albero dei comandi costituisce il mezzo di comunicazione tra <xref:System.Data.EntityClient> e il provider di dati [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] sottostante, ad esempio <xref:System.Data.SqlClient>.  
  
 <xref:System.Data.EntityClient.EntityDataReader> espone i risultati dell'esecuzione di un oggetto <xref:System.Data.EntityClient.EntityCommand> su un modello concettuale. Per eseguire il comando che restituisce <xref:System.Data.EntityClient.EntityDataReader>, chiamare <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>. <xref:System.Data.EntityClient.EntityDataReader> implementa <xref:System.Data.IExtendedDataRecord> per descrivere risultati completamente strutturati.  
  
## <a name="managing-transactions"></a>Gestione di transazioni  
 In Entity Framework è possibile usare le transazioni in modo esplicito e in modo automatico. Le transazioni automatiche usano lo spazio dei nomi <xref:System.Transactions> e le transazioni esplicite usano la classe <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Per aggiornare i dati esposti tramite un modello concettuale. vedere [procedura: gestire le transazioni in Entity Framework](http://msdn.microsoft.com/library/4a55eb7f-f826-4a48-9df1-aebe2352ebef).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Compilare una stringa di connessione EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Procedura: Eseguire una query che restituisce risultati PrimitiveType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Procedura: Eseguire una query che restituisce risultati StructuralType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedura: Eseguire una query che restituisce risultati RefType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Procedura: Eseguire una query che restituisce tipi complessi](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedura: Eseguire una query che restituisce raccolte annidate](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Procedura: Eseguire una stored procedure con parametri tramite EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Procedura: Eseguire una query polimorfica](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Procedura: Esplorare relazioni con l'operatore Navigate](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione di connessioni e transazioni](http://msdn.microsoft.com/library/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)  
 [Riferimenti per il linguaggio](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
