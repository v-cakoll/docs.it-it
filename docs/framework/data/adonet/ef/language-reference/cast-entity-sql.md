---
title: CAST (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 353398f834aff5cefb3aed91899ce042df9df60a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cast-entity-sql"></a><span data-ttu-id="0c773-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0c773-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="0c773-103">Consente di convertire un'espressione da un tipo di dati a un altro.</span><span class="sxs-lookup"><span data-stu-id="0c773-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c773-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c773-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c773-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0c773-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0c773-106">Qualsiasi espressione valida che è possibile convertire in `data_type`.</span><span class="sxs-lookup"><span data-stu-id="0c773-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="0c773-107">Tipo di dati di sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0c773-107">The target system-supplied data type.</span></span> <span data-ttu-id="0c773-108">Deve trattarsi di un tipo primitivo (scalare).</span><span class="sxs-lookup"><span data-stu-id="0c773-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="0c773-109">Il tipo `data_type` usato dipende dall'ambito della query.</span><span class="sxs-lookup"><span data-stu-id="0c773-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="0c773-110">Se una query viene eseguita con <xref:System.Data.EntityClient.EntityCommand>, il tipo di dati è un tipo definito nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="0c773-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="0c773-111">Per altre informazioni, vedere [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="0c773-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="0c773-112">Se una query viene eseguita con <xref:System.Data.Objects.ObjectQuery%601>, il tipo di dati è un tipo CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="0c773-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c773-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c773-113">Return Value</span></span>  
 <span data-ttu-id="0c773-114">Restituisce lo stesso valore di `data_type`.</span><span class="sxs-lookup"><span data-stu-id="0c773-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c773-115">Note</span><span class="sxs-lookup"><span data-stu-id="0c773-115">Remarks</span></span>  
 <span data-ttu-id="0c773-116">La semantica dell'espressione CAST è simile a quella dell'espressione CONVERT [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c773-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="0c773-117">L'espressione CAST viene usata per convertire un valore di un tipo in un valore di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="0c773-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="0c773-118">Se e è di tipo S, e S è convertibile in T, l'espressione precedente è un'espressione CAST valida.</span><span class="sxs-lookup"><span data-stu-id="0c773-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="0c773-119">T deve essere un tipo primitivo (scalare).</span><span class="sxs-lookup"><span data-stu-id="0c773-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="0c773-120">Quando si esegue il cast a `Edm.Decimal`, è possibile fornire i valori dei facet di precisione e scala.</span><span class="sxs-lookup"><span data-stu-id="0c773-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="0c773-121">Se non vengono forniti in modo esplicito, i valori predefiniti per la precisione e la scala sono 18 e 0, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c773-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="0c773-122">In particolare, gli overload seguenti sono supportati per `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="0c773-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="0c773-123">L'utilizzo di un'espressione CAST è considerato una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="0c773-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="0c773-124">Le conversioni esplicite possono comportare il troncamento dei dati o la perdita di precisione.</span><span class="sxs-lookup"><span data-stu-id="0c773-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c773-125">L'operatore CAST è supportato solo per tipi primitivi e tipi di membro di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0c773-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c773-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c773-126">Example</span></span>  
 <span data-ttu-id="0c773-127">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore CAST per eseguire il cast di un'espressione da un tipo di dati a un altro.</span><span class="sxs-lookup"><span data-stu-id="0c773-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="0c773-128">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c773-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0c773-129">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c773-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0c773-130">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0c773-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="0c773-131">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery`:</span><span class="sxs-lookup"><span data-stu-id="0c773-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="0c773-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c773-132">See Also</span></span>  
 [<span data-ttu-id="0c773-133">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0c773-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
