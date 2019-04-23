---
title: Linguaggio Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 09ec1a5518ec0847b54394449f32b3068c811577
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140933"
---
# <a name="entity-sql-language"></a><span data-ttu-id="2da65-102">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2da65-102">Entity SQL Language</span></span>
<span data-ttu-id="2da65-103">Entity SQL è un linguaggio di query indipendente da archiviazione che è simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="2da65-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="2da65-104">Entity SQL consente di eseguire una query su dati di entità, come oggetti o in un form tabulare.</span><span class="sxs-lookup"><span data-stu-id="2da65-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="2da65-105">L'utilizzo di Entity SQL è indicato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2da65-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="2da65-106">Quando è necessario creare una query dinamicamente in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="2da65-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="2da65-107">In questo caso, si dovrebbero usare anche i metodi del generatore di query di <xref:System.Data.Objects.ObjectQuery%601> anziché costruire una stringa di query Entity SQL in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="2da65-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="2da65-108">Quando si desidera definire una query come parte della definizione del modello.</span><span class="sxs-lookup"><span data-stu-id="2da65-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="2da65-109">Solo Entity SQL è supportato in un modello di dati.</span><span class="sxs-lookup"><span data-stu-id="2da65-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="2da65-110">Per altre informazioni, vedere [elemento QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="2da65-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="2da65-111">Quando si usa EntityClient per restituire dati di entità di sola lettura come set di righe usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="2da65-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="2da65-112">Per altre informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="2da65-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="2da65-113">Se si è già esperti nei linguaggi di query basati su SQL, Entity SQL potrebbe essere la soluzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="2da65-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="2da65-114">Uso di Entity SQL con il provider EntityClient</span><span class="sxs-lookup"><span data-stu-id="2da65-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="2da65-115">Se si desidera usare Entity SQL con il provider EntityClient, vedere gli argomenti seguenti per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="2da65-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="2da65-116">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2da65-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="2da65-117">Procedura: Compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="2da65-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="2da65-118">Procedura: Eseguire una Query che restituisce risultati PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="2da65-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="2da65-119">Procedura: Eseguire una Query che restituisce risultati StructuralType</span><span class="sxs-lookup"><span data-stu-id="2da65-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="2da65-120">Procedura: Eseguire una Query che restituisce risultati RefType</span><span class="sxs-lookup"><span data-stu-id="2da65-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="2da65-121">Procedura: Eseguire una Query che restituisce tipi complessi</span><span class="sxs-lookup"><span data-stu-id="2da65-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="2da65-122">Procedura: Eseguire una Query che restituisce raccolte annidate</span><span class="sxs-lookup"><span data-stu-id="2da65-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="2da65-123">Procedura: Eseguire una Query SQL di entità con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="2da65-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="2da65-124">Procedura: Eseguire una Stored Procedure con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="2da65-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="2da65-125">Procedura: Eseguire una Query polimorfica</span><span class="sxs-lookup"><span data-stu-id="2da65-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="2da65-126">Procedura: Esplorare relazioni con l'operatore Navigate</span><span class="sxs-lookup"><span data-stu-id="2da65-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="2da65-127">Uso di Entity SQL con le query di oggetto</span><span class="sxs-lookup"><span data-stu-id="2da65-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="2da65-128">Se si desidera usare Entity SQL con query di oggetto, vedere gli argomenti seguenti per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="2da65-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="2da65-129">[Procedura: Eseguire una Query che restituisce oggetti di tipo di entità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-129">[How to: Execute a Query that Returns Entity Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-130">[Procedura: Eseguire una Query con parametri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-130">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-131">[Procedura: Esplorare relazioni tramite proprietà di navigazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-131">[How to: Navigate Relationships Using Navigation Properties](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-132">[Procedura: Chiamare una funzione definita dall'utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-132">[How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-133">[Procedura: Filtrare i dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-133">[How to: Filter Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-134">[Procedura: Ordinamento dei dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-134">[How to: Sort Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-135">[Procedura: Raggruppare i dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-135">[How to: Group Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-136">[Procedura: Dati aggregati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-136">[How to: Aggregate Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-137">[Procedura: Eseguire una Query che restituisce oggetti di tipo anonimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-137">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-138">[Procedura: Eseguire una Query che restituisce una raccolta di tipi primitivi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-138">[How to: Execute a Query that Returns a Collection of Primitive Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-139">[Procedura: Query sugli oggetti correlati in un oggetto EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-139">[How to: Query Related Objects in an EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-140">[Procedura: Ordinare l'unione di due query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-140">[How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="2da65-141">[Procedura: Spostarsi tra i risultati della Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2da65-141">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2da65-142">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2da65-142">In This Section</span></span>  
 [<span data-ttu-id="2da65-143">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2da65-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="2da65-144">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2da65-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="2da65-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2da65-145">See also</span></span>

- [<span data-ttu-id="2da65-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2da65-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="2da65-147">Riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="2da65-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
