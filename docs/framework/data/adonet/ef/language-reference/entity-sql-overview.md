---
title: Cenni preliminari su Entity SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 301a934cad59b14d1a65a1e98247490d578e6866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-overview"></a><span data-ttu-id="f5972-102">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f5972-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="f5972-103"> è un linguaggio simile a SQL che consente di eseguire query sui modelli concettuali in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5972-103"> is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f5972-104">I modelli concettuali rappresentano i dati come entità e relazioni, e [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consente di eseguire una query di queste entità e relazioni in un formato familiare a coloro che usano SQL.</span><span class="sxs-lookup"><span data-stu-id="f5972-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="f5972-105">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] funziona con provider di dati specifici dell'archiviazione per convertire il linguaggio [!INCLUDE[esql](../../../../../../includes/esql-md.md)] generico in query specifiche dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f5972-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="f5972-106">Il provider EntityClient consente di eseguire un comando [!INCLUDE[esql](../../../../../../includes/esql-md.md)] su un modello di entità e di restituire tipi complessi di dati che includono risultati scalari, set di risultati e oggetti grafici.</span><span class="sxs-lookup"><span data-stu-id="f5972-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="f5972-107">Quando si costruiscono oggetti <xref:System.Data.EntityClient.EntityCommand>, è possibile specificare il nome di una stored procedure o il testo di una query assegnando una stringa di query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alla proprietà <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5972-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f5972-108"><xref:System.Data.EntityClient.EntityDataReader> espone i risultati dell'esecuzione di un oggetto <xref:System.Data.EntityClient.EntityCommand> su EDM.</span><span class="sxs-lookup"><span data-stu-id="f5972-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="f5972-109">Per eseguire il comando che restituisce <xref:System.Data.EntityClient.EntityDataReader>, chiamare <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5972-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="f5972-110">Oltre al provider EntityClient, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] consente di usare [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per eseguire query su un modello concettuale e restituire dati come oggetti CLR fortemente tipizzati che sono istanze di tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="f5972-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="f5972-111">Per ulteriori informazioni, vedere [lavora con gli oggetti](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f5972-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="f5972-112">Contenuto della sezione vengono fornite informazioni di carattere concettuale su [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5972-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5972-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5972-113">In This Section</span></span>  
 [<span data-ttu-id="f5972-114">Differenze tra Entity SQL da Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5972-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="f5972-115">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f5972-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="f5972-116">Sistema di tipi</span><span class="sxs-lookup"><span data-stu-id="f5972-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="f5972-117">Definizioni di tipo</span><span class="sxs-lookup"><span data-stu-id="f5972-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="f5972-118">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="f5972-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="f5972-119">La memorizzazione nella cache di piano di query</span><span class="sxs-lookup"><span data-stu-id="f5972-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="f5972-120">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="f5972-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="f5972-121">Identificatori</span><span class="sxs-lookup"><span data-stu-id="f5972-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="f5972-122">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5972-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="f5972-123">Variabili</span><span class="sxs-lookup"><span data-stu-id="f5972-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="f5972-124">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="f5972-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="f5972-125">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="f5972-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="f5972-126">Valori letterali null e inferenza dei tipi</span><span class="sxs-lookup"><span data-stu-id="f5972-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="f5972-127">Set di caratteri di input</span><span class="sxs-lookup"><span data-stu-id="f5972-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="f5972-128">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="f5972-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="f5972-129">Funzioni</span><span class="sxs-lookup"><span data-stu-id="f5972-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="f5972-130">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="f5972-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="f5972-131">Paging</span><span class="sxs-lookup"><span data-stu-id="f5972-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="f5972-132">Semantica di confronto</span><span class="sxs-lookup"><span data-stu-id="f5972-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="f5972-133">Composizione di query Entity SQL annidate</span><span class="sxs-lookup"><span data-stu-id="f5972-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="f5972-134">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="f5972-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5972-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5972-135">See Also</span></span>  
 [<span data-ttu-id="f5972-136">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f5972-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="f5972-137">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f5972-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="f5972-138">Specifiche CSDL, SSDL e MSL</span><span class="sxs-lookup"><span data-stu-id="f5972-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
