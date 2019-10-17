---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 16be25336bac386c993eae7527c9377be1073d1e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319270"
---
# <a name="top-entity-sql"></a><span data-ttu-id="6985f-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6985f-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="6985f-103">La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6985f-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="6985f-104">La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="6985f-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="6985f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6985f-105">Syntax</span></span>

```sql
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="6985f-106">argomenti</span><span class="sxs-lookup"><span data-stu-id="6985f-106">Arguments</span></span>

<span data-ttu-id="6985f-107">`n` espressione numerica che specifica il numero di righe da restituire.</span><span class="sxs-lookup"><span data-stu-id="6985f-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="6985f-108">`n` potrebbero essere un singolo valore letterale numerico o un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="6985f-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="6985f-109">Note</span><span class="sxs-lookup"><span data-stu-id="6985f-109">Remarks</span></span>

<span data-ttu-id="6985f-110">L'espressione TOP deve essere un singolo valore letterale numerico o un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="6985f-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="6985f-111">Se viene usato un valore letterale costante, il tipo del valore letterale deve essere implicitamente promuovibile a Edm.Int64 (byte, int16, int32 o int64 oppure qualsiasi tipo di provider mappato a un tipo promuovibile a Edm.Int64) e il suo valore deve essere maggiore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="6985f-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="6985f-112">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6985f-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="6985f-113">Se come espressione viene usato un parametro, anche il tipo di parametro deve essere implicitamente promuovibile a Edm.Int64, ma non verrà eseguita alcuna convalida effettiva del valore del parametro durante la compilazione in quanto per i valori dei parametri viene usata l'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="6985f-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="6985f-114">Di seguito è illustrato un esempio di espressione TOP costante.</span><span class="sxs-lookup"><span data-stu-id="6985f-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="6985f-115">Di seguito è riportato un esempio di espressione TOP con parametri:</span><span class="sxs-lookup"><span data-stu-id="6985f-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="6985f-116">L'espressione TOP non è deterministica, a meno che la query non venga ordinata.</span><span class="sxs-lookup"><span data-stu-id="6985f-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="6985f-117">Se è necessario un risultato deterministico, usare le sottoclausole [SKIP](skip-entity-sql.md) e [LIMIT](limit-entity-sql.md) nella clausola [ORDER BY](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="6985f-117">If you require a deterministic result, use the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="6985f-118">TOP e SKIP/LIMIT si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="6985f-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="6985f-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="6985f-119">Example</span></span>

<span data-ttu-id="6985f-120">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato TOP per specificare la riga superiore da restituire dal risultato della query.</span><span class="sxs-lookup"><span data-stu-id="6985f-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="6985f-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6985f-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6985f-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6985f-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="6985f-123">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6985f-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="6985f-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6985f-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a><span data-ttu-id="6985f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6985f-125">See also</span></span>

- [<span data-ttu-id="6985f-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="6985f-126">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="6985f-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="6985f-127">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="6985f-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="6985f-128">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="6985f-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="6985f-129">ORDER BY</span></span>](order-by-entity-sql.md)
- [<span data-ttu-id="6985f-130">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6985f-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
