---
title: Cenni preliminari su Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 8f40a34f361669d2b8d89b63b3187cae6bf705d2
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854491"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="a127f-102">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a127f-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a127f-103">è un linguaggio simile a SQL che consente di eseguire query sui modelli concettuali nell'Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a127f-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="a127f-104">I modelli concettuali rappresentano i dati come entità e relazioni [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e consentono di eseguire query su tali entità e relazioni in un formato noto a coloro che hanno utilizzato SQL.</span><span class="sxs-lookup"><span data-stu-id="a127f-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
      
 <span data-ttu-id="a127f-105">Il Entity Framework funziona con i provider di dati specifici dell'archiviazione per [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tradurre Generic in query specifiche dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a127f-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="a127f-106">Il provider EntityClient consente di eseguire un comando [!INCLUDE[esql](../../../../../../includes/esql-md.md)] su un modello di entità e di restituire tipi complessi di dati che includono risultati scalari, set di risultati e oggetti grafici.</span><span class="sxs-lookup"><span data-stu-id="a127f-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="a127f-107">Quando si costruiscono oggetti <xref:System.Data.EntityClient.EntityCommand>, è possibile specificare il nome di una stored procedure o il testo di una query assegnando una stringa di query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alla proprietà <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a127f-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a127f-108"><xref:System.Data.EntityClient.EntityDataReader> espone i risultati dell'esecuzione di un oggetto <xref:System.Data.EntityClient.EntityCommand> su EDM.</span><span class="sxs-lookup"><span data-stu-id="a127f-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="a127f-109">Per eseguire il comando che restituisce <xref:System.Data.EntityClient.EntityDataReader>, chiamare <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="a127f-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="a127f-110">Oltre al provider EntityClient, il Entity Framework consente di utilizzare [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per eseguire query su un modello concettuale e restituire dati come oggetti CLR fortemente tipizzati che sono istanze di tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="a127f-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="a127f-111">Per ulteriori informazioni, vedere [utilizzo di oggetti](../working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a127f-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="a127f-112">Contenuto della sezione vengono fornite informazioni di carattere concettuale su [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a127f-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a127f-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a127f-113">In This Section</span></span>  
 [<span data-ttu-id="a127f-114">Differenze tra Entity SQL e Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a127f-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="a127f-115">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a127f-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="a127f-116">Sistema di tipi</span><span class="sxs-lookup"><span data-stu-id="a127f-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="a127f-117">Definizioni di tipo</span><span class="sxs-lookup"><span data-stu-id="a127f-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="a127f-118">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="a127f-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="a127f-119">Memorizzazione nella cache di piani di query</span><span class="sxs-lookup"><span data-stu-id="a127f-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="a127f-120">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="a127f-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="a127f-121">Identificatori</span><span class="sxs-lookup"><span data-stu-id="a127f-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="a127f-122">Parametri</span><span class="sxs-lookup"><span data-stu-id="a127f-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="a127f-123">Variabili</span><span class="sxs-lookup"><span data-stu-id="a127f-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="a127f-124">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="a127f-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a127f-125">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="a127f-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="a127f-126">Valori letterali Null e inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="a127f-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="a127f-127">Set di caratteri di input</span><span class="sxs-lookup"><span data-stu-id="a127f-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="a127f-128">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="a127f-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a127f-129">Funzioni</span><span class="sxs-lookup"><span data-stu-id="a127f-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="a127f-130">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="a127f-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="a127f-131">Paging</span><span class="sxs-lookup"><span data-stu-id="a127f-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="a127f-132">Semantica di confronto</span><span class="sxs-lookup"><span data-stu-id="a127f-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="a127f-133">Composizione di query Entity SQL annidate</span><span class="sxs-lookup"><span data-stu-id="a127f-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="a127f-134">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="a127f-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="a127f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a127f-135">See also</span></span>

- [<span data-ttu-id="a127f-136">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a127f-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a127f-137">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a127f-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="a127f-138">Specifiche CSDL, SSDL e MSL</span><span class="sxs-lookup"><span data-stu-id="a127f-138">CSDL, SSDL, and MSL Specifications</span></span>](csdl-ssdl-and-msl-specifications.md)
