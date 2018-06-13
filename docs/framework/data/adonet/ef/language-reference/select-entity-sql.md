---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: f815c08b9be11efc71b04678d9780cabcdd69ab5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765984"
---
# <a name="select-entity-sql"></a><span data-ttu-id="e7157-102">SELECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7157-102">SELECT (Entity SQL)</span></span>
<span data-ttu-id="e7157-103">Specifica gli elementi restituiti da una query.</span><span class="sxs-lookup"><span data-stu-id="e7157-103">Specifies the elements returned by a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7157-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7157-104">Syntax</span></span>  
  
```  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr   
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7157-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e7157-105">Arguments</span></span>  
 <span data-ttu-id="e7157-106">ALL</span><span class="sxs-lookup"><span data-stu-id="e7157-106">ALL</span></span>  
 <span data-ttu-id="e7157-107">Specifica che nel set di risultati possono essere inclusi duplicati.</span><span class="sxs-lookup"><span data-stu-id="e7157-107">Specifies that duplicates can appear in the result set.</span></span> <span data-ttu-id="e7157-108">ALL è l'argomento predefinito.</span><span class="sxs-lookup"><span data-stu-id="e7157-108">ALL is the default.</span></span>  
  
 <span data-ttu-id="e7157-109">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="e7157-109">DISTINCT</span></span>  
 <span data-ttu-id="e7157-110">Specifica che nel set di risultati possono essere inclusi solo risultati univoci.</span><span class="sxs-lookup"><span data-stu-id="e7157-110">Specifies that only unique results can appear in the result set.</span></span>  
  
 <span data-ttu-id="e7157-111">VALUE</span><span class="sxs-lookup"><span data-stu-id="e7157-111">VALUE</span></span>  
 <span data-ttu-id="e7157-112">Consente di specificare un solo elemento e non aggiunge un wrapper di riga.</span><span class="sxs-lookup"><span data-stu-id="e7157-112">Allows only one item to be specified, and does not add on a row wrapper.</span></span>  
  
 `topSubclause`  
 <span data-ttu-id="e7157-113">Qualsiasi espressione valida che indica il numero dei primi risultati che devono essere restituiti dalla query, nel formato `top (``expr``)`.</span><span class="sxs-lookup"><span data-stu-id="e7157-113">Any valid expression that indicates the number of first results to return from the query, of the form `top (``expr``)`.</span></span>  
  
 <span data-ttu-id="e7157-114">Il parametro LIMIT del [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) operatore consente inoltre di selezionare i primi n elementi nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="e7157-114">The LIMIT parameter of the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) operator also lets you select the first n items in the result set.</span></span>  
  
 `aliasedExpr`  
 <span data-ttu-id="e7157-115">Espressione nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="e7157-115">An expression of the form:</span></span>  
  
 <span data-ttu-id="e7157-116">`expr` come `identifier`&#124; `expr`</span><span class="sxs-lookup"><span data-stu-id="e7157-116">`expr` as `identifier` &#124; `expr`</span></span>  
  
 `expr`  
 <span data-ttu-id="e7157-117">Valore letterale o espressione.</span><span class="sxs-lookup"><span data-stu-id="e7157-117">A literal or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7157-118">Note</span><span class="sxs-lookup"><span data-stu-id="e7157-118">Remarks</span></span>  
 <span data-ttu-id="e7157-119">La clausola SELECT viene valutata dopo il [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), e [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) clausole sono state valutate.</span><span class="sxs-lookup"><span data-stu-id="e7157-119">The SELECT clause is evaluated after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), and [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) clauses have been evaluated.</span></span> <span data-ttu-id="e7157-120">La clausola SELECT può fare riferimento solo agli elementi attualmente inclusi nell'ambito (dalla clausola FROM o da ambiti esterni).</span><span class="sxs-lookup"><span data-stu-id="e7157-120">The SELECT clause can only refer to items currently in-scope (from the FROM clause, or from outer scopes).</span></span> <span data-ttu-id="e7157-121">Se è stata specificata una clausola GROUP BY, la clausola SELECT può fare riferimento solo agli alias per le chiavi GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="e7157-121">If a GROUP BY clause has been specified, the SELECT clause is only allowed to reference the aliases for the GROUP BY keys.</span></span> <span data-ttu-id="e7157-122">Il riferimento agli elementi della clausola FROM è consentito solo nelle funzioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="e7157-122">Referring to the FROM clause items is only permitted in aggregate functions.</span></span>  
  
 <span data-ttu-id="e7157-123">L'elenco di una o più espressioni di query che seguono la parola chiave SELECT è noto come elenco di selezione o, più formalmente, come proiezione.</span><span class="sxs-lookup"><span data-stu-id="e7157-123">The list of one or more query expressions following the SELECT keyword is known as the select list, or more formally as the projection.</span></span> <span data-ttu-id="e7157-124">La forma più generale di proiezione è una singola espressione di query.</span><span class="sxs-lookup"><span data-stu-id="e7157-124">The most general form of projection is a single query expression.</span></span> <span data-ttu-id="e7157-125">Se si seleziona un membro `member1` da una raccolta `collection1`, verrà creata una nuova raccolta di tutti i valori di `member1` per ogni oggetto di `collection1`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7157-125">If you select a member `member1` from a collection `collection1`, you will produce a new collection of all the `member1` values for each object in `collection1`, as illustrated in the following example.</span></span>  
  
```  
SELECT collection1.member1 FROM collection1  
```  
  
 <span data-ttu-id="e7157-126">Se, ad esempio, `customers` è una raccolta di tipo `Customer` con una proprietà `Name` di tipo `string`, se si seleziona `Name` da `customers` verrà creata una raccolta di stringhe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7157-126">For example, if `customers` is a collection of type `Customer` that has a property `Name` that is of type `string`, selecting `Name` from `customers` will yield a collection of strings, as illustrated in the following example.</span></span>  
  
```  
SELECT customers.Name FROM customers AS c  
```  
  
 <span data-ttu-id="e7157-127">È anche possibile usare la sintassi JOIN (FULL, INNER, LEFT, OUTER, ON e RIGHT).</span><span class="sxs-lookup"><span data-stu-id="e7157-127">It is also possible to use JOIN syntax (FULL, INNER, LEFT, OUTER, ON, and RIGHT).</span></span> <span data-ttu-id="e7157-128">ON è obbligatorio per gli inner join e non è consentito per i cross join.</span><span class="sxs-lookup"><span data-stu-id="e7157-128">ON is required for inner joins and is nto allowed for cross joins.</span></span>  
  
## <a name="row-and-value-select-clauses"></a><span data-ttu-id="e7157-129">Clausole SELECT per la selezione di righe e di valori</span><span class="sxs-lookup"><span data-stu-id="e7157-129">Row and Value Select Clauses</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7157-130"> supporta due varianti della clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="e7157-130"> supports two variants of the SELECT clause.</span></span> <span data-ttu-id="e7157-131">La prima variante, per la selezione di righe, è identificata dalla parola chiave SELECT e può essere usata per specificare uno o più valori da proiettare. Poiché ai valori restituiti viene aggiunto in modo implicito un wrapper di riga, il risultato dell'espressione di query è sempre un multiset di righe.</span><span class="sxs-lookup"><span data-stu-id="e7157-131">The first variant, row select, is identified by the SELECT keyword, and can be used to specify one or more values that should be projected out. Because a row wrapper is implicitly added around the values returned, the result of the query expression is always a multiset of rows.</span></span>  
  
 <span data-ttu-id="e7157-132">In ogni espressione di query in una clausola per la selezione di righe deve essere specificato un alias.</span><span class="sxs-lookup"><span data-stu-id="e7157-132">Each query expression in a row select must specify an alias.</span></span> <span data-ttu-id="e7157-133">Se non viene specificato alcun alias, in[!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generare un alias usando le regole di generazione di alias.</span><span class="sxs-lookup"><span data-stu-id="e7157-133">If no alias is specified,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias by using the alias generation rules.</span></span>  
  
 <span data-ttu-id="e7157-134">L'altra variante della clausola SELECT, per la selezione di valori, è identificata dalla parola chiave SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="e7157-134">The other variant of the SELECT clause, value select, is identified by the SELECT VALUE keyword.</span></span> <span data-ttu-id="e7157-135">Questo tipo di clausola consente di specificare un solo valore e non aggiunge un wrapper di riga.</span><span class="sxs-lookup"><span data-stu-id="e7157-135">It allows only one value to be specified, and does not add a row wrapper.</span></span>  
  
 <span data-ttu-id="e7157-136">Una clausola per la selezione di righe può essere sempre espressa in termini di VALUE SELECT, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7157-136">A row select is always expressible in terms of VALUE SELECT, as illustrated in the following example.</span></span>  
  
```  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C   
```  
  
## <a name="all-and-distinct-modifiers"></a><span data-ttu-id="e7157-137">Modificatori ALL e DISTINCT</span><span class="sxs-lookup"><span data-stu-id="e7157-137">All and Distinct Modifiers</span></span>  
 <span data-ttu-id="e7157-138">Entrambe le varianti della clausola SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consentono di specificare un modificatore ALL o DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="e7157-138">Both variants of SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allow the specification of an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="e7157-139">Se viene specificato il modificatore DISTINCT, i duplicati vengono eliminati dalla raccolta prodotta dall'espressione di query, fino alla clausola SELECT inclusa.</span><span class="sxs-lookup"><span data-stu-id="e7157-139">If the DISTINCT modifier is specified, duplicates are eliminated from the collection produced by the query expression (up to and including the SELECT clause).</span></span> <span data-ttu-id="e7157-140">Se viene specificato il modificatore ALL, non viene eseguita alcuna eliminazione dei duplicati. ALL rappresenta l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e7157-140">If the ALL modifier is specified, no duplicate elimination is performed; ALL is the default.</span></span>  
  
## <a name="differences-from-transact-sql"></a><span data-ttu-id="e7157-141">Differenze rispetto a Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7157-141">Differences from Transact-SQL</span></span>  
 <span data-ttu-id="e7157-142">A differenza di Transact-SQL, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è supportato l'uso dell'argomento \* nella clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="e7157-142">Unlike Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support use of the \* argument in the SELECT clause.</span></span>  <span data-ttu-id="e7157-143">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] consente invece alle query di proiettare interi record facendo riferimento agli alias della raccolta dalla clausola FROM, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e7157-143">Instead, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows queries to project out entire records by referencing the collection aliases from the FROM clause, as illustrated in the following example.</span></span>  
  
```  
SELECT * FROM T1, T2  
```  
  
 <span data-ttu-id="e7157-144">L'espressione di query [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] precedente viene espressa in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="e7157-144">The previous [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] query expression is expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in the following way.</span></span>  
  
```  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a><span data-ttu-id="e7157-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7157-145">Example</span></span>  
 <span data-ttu-id="e7157-146">Nella query Entity SQL seguente viene usato l'operatore SELECT per specificare gli elementi che devono essere restituiti da una query.</span><span class="sxs-lookup"><span data-stu-id="e7157-146">The following Entity SQL query uses the SELECT operator to specify the elements to be returned by a query.</span></span> <span data-ttu-id="e7157-147">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e7157-147">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e7157-148">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7157-148">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e7157-149">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e7157-149">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e7157-150">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e7157-150">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="e7157-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7157-151">See Also</span></span>  
 [<span data-ttu-id="e7157-152">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="e7157-152">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="e7157-153">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e7157-153">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e7157-154">TOP</span><span class="sxs-lookup"><span data-stu-id="e7157-154">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
