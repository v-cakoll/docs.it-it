---
title: Cenni preliminari su Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 4d7db9c6a7aaeef900132663a5b0aa7420afe668
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251063"
---
# <a name="entity-sql-overview"></a>Cenni preliminari su Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] è un linguaggio simile a SQL che consente di eseguire query sui modelli concettuali in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. I modelli concettuali rappresentano i dati come entità e relazioni [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e consentono di eseguire query su tali entità e relazioni in un formato noto a coloro che hanno utilizzato SQL.  
  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] funziona con provider di dati specifici dell'archiviazione per convertire il linguaggio [!INCLUDE[esql](../../../../../../includes/esql-md.md)] generico in query specifiche dell'archiviazione. Il provider EntityClient consente di eseguire un comando [!INCLUDE[esql](../../../../../../includes/esql-md.md)] su un modello di entità e di restituire tipi complessi di dati che includono risultati scalari, set di risultati e oggetti grafici. Quando si costruiscono oggetti <xref:System.Data.EntityClient.EntityCommand>, è possibile specificare il nome di una stored procedure o il testo di una query assegnando una stringa di query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alla proprietà <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> espone i risultati dell'esecuzione di un oggetto <xref:System.Data.EntityClient.EntityCommand> su EDM. Per eseguire il comando che restituisce <xref:System.Data.EntityClient.EntityDataReader>, chiamare <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Oltre al provider EntityClient, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] consente di usare [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per eseguire query su un modello concettuale e restituire dati come oggetti CLR fortemente tipizzati che sono istanze di tipi di entità. Per ulteriori informazioni, vedere [utilizzo di oggetti](../working-with-objects.md).  
  
 Contenuto della sezione vengono fornite informazioni di carattere concettuale su [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="in-this-section"></a>In questa sezione  
 [Differenze tra Entity SQL e Transact-SQL](how-entity-sql-differs-from-transact-sql.md)  
  
 [Riferimento rapido a Entity SQL](entity-sql-quick-reference.md)  
  
 [Sistema di tipi](type-system-entity-sql.md)  
  
 [Definizioni di tipo](type-definitions-entity-sql.md)  
  
 [Costruzione di tipi](constructing-types-entity-sql.md)  
  
 [Memorizzazione nella cache di piani di query](query-plan-caching-entity-sql.md)  
  
 [Spazi dei nomi](namespaces-entity-sql.md)  
  
 [Identificatori](identifiers-entity-sql.md)  
  
 [Parametri](parameters-entity-sql.md)  
  
 [Variabili](variables-entity-sql.md)  
  
 [Espressioni non supportate](unsupported-expressions-entity-sql.md)  
  
 [Valori letterali](literals-entity-sql.md)  
  
 [Valori letterali Null e inferenza del tipo](null-literals-and-type-inference-entity-sql.md)  
  
 [Set di caratteri di input](input-character-set-entity-sql.md)  
  
 [Espressioni di query](query-expressions-entity-sql.md)  
  
 [Funzioni](functions-entity-sql.md)  
  
 [Precedenza tra gli operatori](operator-precedence-entity-sql.md)  
  
 [Paging](paging-entity-sql.md)  
  
 [Semantica di confronto](comparison-semantics-entity-sql.md)  
  
 [Composizione di query Entity SQL annidate](composing-nested-entity-sql-queries.md)  
  
 [Tipi strutturati nullable](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Linguaggio Entity SQL](entity-sql-language.md)
- [Specifiche CSDL, SSDL e MSL](csdl-ssdl-and-msl-specifications.md)
