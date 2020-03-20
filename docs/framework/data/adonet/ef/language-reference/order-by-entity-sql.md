---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 1233971b172079aa48227d0ec520068afbdf0952
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150069"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="16a46-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="16a46-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="16a46-103">Specifica il tipo di ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="16a46-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16a46-104">Syntax</span></span>  
  
```sql  
[ ORDER BY
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="16a46-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="16a46-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="16a46-106">Qualsiasi espressione di query valida che specifica una proprietà in base a cui eseguire l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="16a46-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="16a46-107">È possibile specificare più espressioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="16a46-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="16a46-108">La sequenza delle espressioni di ordinamento nella clausola ORDER BY definisce l'organizzazione del set di risultati ordinato.</span><span class="sxs-lookup"><span data-stu-id="16a46-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="16a46-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="16a46-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="16a46-110">Indica che l'operazione ORDER BY deve essere eseguita in base alle regole di confronto specificate in `collation_name`.</span><span class="sxs-lookup"><span data-stu-id="16a46-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="16a46-111">È possibile applicare COLLATE solo alle espressioni stringa.</span><span class="sxs-lookup"><span data-stu-id="16a46-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="16a46-112">ASC</span><span class="sxs-lookup"><span data-stu-id="16a46-112">ASC</span></span>  
 <span data-ttu-id="16a46-113">Specifica che i valori nella proprietà specificata devono essere ordinati in modo crescente, dal valore più basso a quello più alto.</span><span class="sxs-lookup"><span data-stu-id="16a46-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="16a46-114">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="16a46-114">This is the default.</span></span>  
  
 <span data-ttu-id="16a46-115">DESC</span><span class="sxs-lookup"><span data-stu-id="16a46-115">DESC</span></span>  
 <span data-ttu-id="16a46-116">Specifica che i valori nella proprietà specificata devono essere ordinati in modo decrescente, dal valore più alto a quello più basso.</span><span class="sxs-lookup"><span data-stu-id="16a46-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="16a46-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="16a46-117">LIMIT `n`</span></span>  
 <span data-ttu-id="16a46-118">Verranno selezionati solo i primi `n` elementi.</span><span class="sxs-lookup"><span data-stu-id="16a46-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="16a46-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="16a46-119">SKIP `n`</span></span>  
 <span data-ttu-id="16a46-120">I primi `n` elementi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="16a46-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16a46-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="16a46-121">Remarks</span></span>  
 <span data-ttu-id="16a46-122">La clausola ORDER BY viene applicata logicamente al risultato della clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="16a46-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="16a46-123">La clausola ORDER BY può fare riferimento agli elementi nell'elenco di selezione tramite i relativi alias.</span><span class="sxs-lookup"><span data-stu-id="16a46-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="16a46-124">La clausola ORDER BY può fare riferimento anche ad altre variabili attualmente incluse nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="16a46-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="16a46-125">Se, tuttavia, la clausola SELECT è stata specificata con un modificatore DISTINCT, la clausola ORDER BY può fare riferimento solo agli alias della clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="16a46-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="16a46-126">Ogni espressione nella clausola ORDER BY deve restituire un tipo che possa essere confrontato per verificare la disuguaglianza ordinata (minore di o maggiore di e così via).</span><span class="sxs-lookup"><span data-stu-id="16a46-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="16a46-127">Questi tipi sono in genere tipi primitivi scalari ad esempio numeri, stringhe e date.</span><span class="sxs-lookup"><span data-stu-id="16a46-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="16a46-128">Anche i tipi RowTypes di tipi confrontabili possono essere confrontati in termini di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="16a46-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="16a46-129">Se il codice scorre un set ordinato, non è garantito che l'ordine venga mantenuto, ad eccezione del caso di una proiezione di livello principale.</span><span class="sxs-lookup"><span data-stu-id="16a46-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  

<span data-ttu-id="16a46-130">Nell'esempio seguente, l'ordine è garantito per essere mantenuto:</span><span class="sxs-lookup"><span data-stu-id="16a46-130">In the following sample, order is guaranteed to be preserved:</span></span>

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="16a46-131">Nella query seguente, l'ordinamento della query nidificata viene ignorato:</span><span class="sxs-lookup"><span data-stu-id="16a46-131">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="16a46-132">Per eseguire un'operazione UNION, UNION ALL, EXCEPT o INTERSECT ordinata, usare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="16a46-132">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="16a46-133">Parole chiave con restrizioni</span><span class="sxs-lookup"><span data-stu-id="16a46-133">Restricted keywords</span></span>  
 <span data-ttu-id="16a46-134">Le parole chiave seguenti devono essere racchiuse tra virgolette quando usate in una clausola `ORDER BY` :</span><span class="sxs-lookup"><span data-stu-id="16a46-134">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="16a46-135">CROSS</span><span class="sxs-lookup"><span data-stu-id="16a46-135">CROSS</span></span>  
  
- <span data-ttu-id="16a46-136">FULL</span><span class="sxs-lookup"><span data-stu-id="16a46-136">FULL</span></span>  
  
- <span data-ttu-id="16a46-137">KEY</span><span class="sxs-lookup"><span data-stu-id="16a46-137">KEY</span></span>  
  
- <span data-ttu-id="16a46-138">LEFT</span><span class="sxs-lookup"><span data-stu-id="16a46-138">LEFT</span></span>  
  
- <span data-ttu-id="16a46-139">ORDER</span><span class="sxs-lookup"><span data-stu-id="16a46-139">ORDER</span></span>  
  
- <span data-ttu-id="16a46-140">OUTER</span><span class="sxs-lookup"><span data-stu-id="16a46-140">OUTER</span></span>  
  
- <span data-ttu-id="16a46-141">RIGHT</span><span class="sxs-lookup"><span data-stu-id="16a46-141">RIGHT</span></span>  
  
- <span data-ttu-id="16a46-142">ROW</span><span class="sxs-lookup"><span data-stu-id="16a46-142">ROW</span></span>  
  
- <span data-ttu-id="16a46-143">VALORE</span><span class="sxs-lookup"><span data-stu-id="16a46-143">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="16a46-144">Ordinamento di query annidate</span><span class="sxs-lookup"><span data-stu-id="16a46-144">Ordering Nested Queries</span></span>  
 <span data-ttu-id="16a46-145">In Entity Framework un'espressione annidata può essere inserita in una posizione qualsiasi nella query. L'ordine di una query annidata non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="16a46-145">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  

<span data-ttu-id="16a46-146">La query seguente ordinerà i risultati in base al cognome:</span><span class="sxs-lookup"><span data-stu-id="16a46-146">The following query will order the results by the last name:</span></span>  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="16a46-147">Nella query seguente, l'ordinamento della query nidificata viene ignorato:</span><span class="sxs-lookup"><span data-stu-id="16a46-147">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="16a46-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="16a46-148">Example</span></span>  
 <span data-ttu-id="16a46-149">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ORDER BY per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="16a46-149">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="16a46-150">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="16a46-150">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="16a46-151">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16a46-151">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="16a46-152">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="16a46-152">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="16a46-153">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="16a46-153">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="16a46-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16a46-154">See also</span></span>

- [<span data-ttu-id="16a46-155">Espressioni di queryQuery Expressions</span><span class="sxs-lookup"><span data-stu-id="16a46-155">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="16a46-156">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="16a46-156">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="16a46-157">Saltare</span><span class="sxs-lookup"><span data-stu-id="16a46-157">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="16a46-158">Limite</span><span class="sxs-lookup"><span data-stu-id="16a46-158">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="16a46-159">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="16a46-159">TOP</span></span>](top-entity-sql.md)
