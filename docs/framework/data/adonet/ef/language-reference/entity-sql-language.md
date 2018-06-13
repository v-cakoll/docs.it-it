---
title: Linguaggio Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: dbc44189634f4548b97647d19465e28ee343635d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761038"
---
# <a name="entity-sql-language"></a>Linguaggio Entity SQL
Entity SQL è un linguaggio di query indipendente da archiviazione che è simile a SQL. Entity SQL consente di eseguire una query su dati di entità, come oggetti o in un form tabulare. L'utilizzo di Entity SQL è indicato nei casi seguenti:  
  
-   Quando è necessario creare una query dinamicamente in fase di runtime. In questo caso, si dovrebbero usare anche i metodi del generatore di query di <xref:System.Data.Objects.ObjectQuery%601> anziché costruire una stringa di query Entity SQL in fase di runtime.  
  
-   Quando si desidera definire una query come parte della definizione del modello. Solo Entity SQL è supportato in un modello di dati. Per altre informazioni, vedere [elemento QueryView (MSL)](http://msdn.microsoft.com/library/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   Quando si usa EntityClient per restituire dati di entità di sola lettura come set di righe usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>. Per ulteriori informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Se si è già esperti nei linguaggi di query basati su SQL, Entity SQL potrebbe essere la soluzione più semplice.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Uso di Entity SQL con il provider EntityClient  
 Se si desidera usare Entity SQL con il provider EntityClient, vedere gli argomenti seguenti per ulteriori informazioni:  
  
 [Provider EntityClient per Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Procedura: Compilare una stringa di connessione EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Procedura: Eseguire una query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Procedura: Eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedura: Eseguire una query che restituisce risultati RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Procedura: Eseguire una query che restituisce tipi complessi](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedura: Eseguire una query che restituisce raccolte annidate](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Procedura: Eseguire una stored procedure con parametri tramite EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Procedura: Eseguire una query polimorfica](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Procedura: Esplorare relazioni con l'operatore Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Uso di Entity SQL con le query di oggetto  
 Se si desidera usare Entity SQL con query di oggetto, vedere gli argomenti seguenti per ulteriori informazioni:  
  
 [Procedura: eseguire una Query che restituisce gli oggetti di tipo di entità](http://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [Procedura: eseguire una Query con parametri](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [Procedura: spostarsi tra relazioni tramite proprietà di navigazione](http://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [Procedura: chiamare una funzione definita dall'utente](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [Procedura: filtrare i dati](http://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [Procedura: ordinare i dati](http://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [Procedura: raggruppare i dati](http://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [Procedura: aggregazione dei dati](http://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [Procedura: eseguire una Query che restituisce gli oggetti di tipo anonimo](http://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [Procedura: eseguire una Query che restituisce una raccolta di tipi primitivi](http://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [Procedura: eseguire Query su oggetti correlati in un elemento EntityCollection](http://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [Procedura: ordinare l'unione di due query](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [Procedura: spostarsi Query tra i risultati](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [Riferimenti per il linguaggio](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
