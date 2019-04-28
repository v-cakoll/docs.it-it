---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: e7c6cf6b67dc3af29f7ca8fb22af419235a9b833
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879762"
---
# <a name="top-entity-sql"></a><span data-ttu-id="e2d63-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2d63-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="e2d63-103">La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e2d63-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="e2d63-104">La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="e2d63-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2d63-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2d63-105">Syntax</span></span>

```
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="e2d63-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e2d63-106">Arguments</span></span>

<span data-ttu-id="e2d63-107">`n` L'espressione numerica che specifica il numero di righe da restituire.</span><span class="sxs-lookup"><span data-stu-id="e2d63-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="e2d63-108">`n` potrebbero essere un singolo valore letterale numerico o un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="e2d63-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2d63-109">Note</span><span class="sxs-lookup"><span data-stu-id="e2d63-109">Remarks</span></span>

<span data-ttu-id="e2d63-110">L'espressione TOP deve essere un singolo valore letterale numerico o un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="e2d63-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="e2d63-111">Se viene usato un valore letterale costante, il tipo del valore letterale deve essere implicitamente promuovibile a Edm.Int64 (byte, int16, int32 o int64 oppure qualsiasi tipo di provider mappato a un tipo promuovibile a Edm.Int64) e il suo valore deve essere maggiore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="e2d63-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="e2d63-112">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e2d63-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="e2d63-113">Se come espressione viene usato un parametro, anche il tipo di parametro deve essere implicitamente promuovibile a Edm.Int64, ma non verrà eseguita alcuna convalida effettiva del valore del parametro durante la compilazione in quanto per i valori dei parametri viene usata l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="e2d63-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="e2d63-114">Di seguito è illustrato un esempio di espressione TOP costante.</span><span class="sxs-lookup"><span data-stu-id="e2d63-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="e2d63-115">Di seguito è riportato un esempio di espressione TOP con parametri:</span><span class="sxs-lookup"><span data-stu-id="e2d63-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="e2d63-116">L'espressione TOP non è deterministica, a meno che la query non venga ordinata.</span><span class="sxs-lookup"><span data-stu-id="e2d63-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="e2d63-117">Se è necessario un risultato deterministico, usare le sottoclausole [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) nella clausola [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="e2d63-117">If you require a deterministic result, use the [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses in the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="e2d63-118">TOP e SKIP/LIMIT si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="e2d63-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="e2d63-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2d63-119">Example</span></span>

<span data-ttu-id="e2d63-120">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato TOP per specificare la riga superiore da restituire dal risultato della query.</span><span class="sxs-lookup"><span data-stu-id="e2d63-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="e2d63-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e2d63-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e2d63-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2d63-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="e2d63-123">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e2d63-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="e2d63-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e2d63-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a><span data-ttu-id="e2d63-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2d63-125">See also</span></span>

- [<span data-ttu-id="e2d63-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="e2d63-126">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [<span data-ttu-id="e2d63-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="e2d63-127">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)
- [<span data-ttu-id="e2d63-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="e2d63-128">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)
- [<span data-ttu-id="e2d63-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="e2d63-129">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [<span data-ttu-id="e2d63-130">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e2d63-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
