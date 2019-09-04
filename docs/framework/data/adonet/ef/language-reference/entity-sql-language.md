---
title: Linguaggio Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: a2e4b7245dbfccf7864481b52a0e868a85efbca6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251012"
---
# <a name="entity-sql-language"></a>Linguaggio Entity SQL
Entity SQL è un linguaggio di query indipendente da archiviazione che è simile a SQL. Entity SQL consente di eseguire una query su dati di entità, come oggetti o in un form tabulare. L'utilizzo di Entity SQL è indicato nei casi seguenti:  
  
- Quando è necessario creare una query dinamicamente in fase di runtime. In questo caso, si dovrebbero usare anche i metodi del generatore di query di <xref:System.Data.Objects.ObjectQuery%601> anziché costruire una stringa di query Entity SQL in fase di runtime.  
  
- Quando si desidera definire una query come parte della definizione del modello. Solo Entity SQL è supportato in un modello di dati. Per ulteriori informazioni, vedere [elemento QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
- Quando si usa EntityClient per restituire dati di entità di sola lettura come set di righe usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>. Per ulteriori informazioni, vedere [provider EntityClient per la Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Se si è già esperti nei linguaggi di query basati su SQL, Entity SQL potrebbe essere la soluzione più semplice.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Uso di Entity SQL con il provider EntityClient  
 Se si desidera usare Entity SQL con il provider EntityClient, vedere gli argomenti seguenti per ulteriori informazioni:  
  
 [Provider EntityClient per Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Procedura: Compilare una stringa di connessione EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Procedura: Eseguire una query che restituisce i risultati di RefType](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Procedura: Eseguire una query che restituisce tipi complessi](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Procedura: Eseguire una query che restituisce raccolte annidate](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Procedura: Eseguire una query di Entity SQL con parametri utilizzando EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Procedura: Eseguire una stored procedure con parametri tramite EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Procedura: Eseguire una query polimorfica](../how-to-execute-a-polymorphic-query.md)  
  
 [Procedura: Esplorare le relazioni con l'operatore Navigate](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Uso di Entity SQL con le query di oggetto  
 Se si desidera usare Entity SQL con query di oggetto, vedere gli argomenti seguenti per ulteriori informazioni:  
  
 [Procedura: Eseguire una query che restituisce oggetti del tipo di entità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Procedura: Eseguire una query con parametri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Procedura: Esplorare le relazioni usando le proprietà di navigazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Procedura: Chiamare una funzione definita dall'utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Procedura: Filtrare i dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Procedura: Ordina dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Procedura: Raggruppa dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Procedura: Dati aggregati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Procedura: Eseguire una query che restituisce oggetti di tipo anonimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Procedura: Eseguire una query che restituisce una raccolta di tipi primitivi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Procedura: Eseguire query sugli oggetti correlati in un oggetto EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Procedura: Ordinare l'Unione di due query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Procedura: Pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica di Entity SQL](entity-sql-overview.md)  
  
 [Riferimento a Entity SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET Entity Framework](../index.md)
- [Riferimenti per il linguaggio](index.md)
