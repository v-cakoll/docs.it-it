---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 2334a30009d6bef9544d2ca1e0ab923a7441d6f2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833824"
---
# <a name="from-entity-sql"></a><span data-ttu-id="cf478-102">FROM (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cf478-102">FROM (Entity SQL)</span></span>
<span data-ttu-id="cf478-103">Specifica la raccolta usata nelle istruzioni [Select](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="cf478-103">Specifies the collection used in [SELECT](select-entity-sql.md) statements.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf478-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf478-104">Syntax</span></span>

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a><span data-ttu-id="cf478-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cf478-105">Arguments</span></span>

`expression` \
<span data-ttu-id="cf478-106">Qualsiasi espressione di query valida che produce una raccolta da usare come origine in un'istruzione `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="cf478-106">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf478-107">Note</span><span class="sxs-lookup"><span data-stu-id="cf478-107">Remarks</span></span>

<span data-ttu-id="cf478-108">Una clausola `FROM` è un elenco delimitato da virgole di uno o più elementi della clausola `FROM`.</span><span class="sxs-lookup"><span data-stu-id="cf478-108">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="cf478-109">La clausola `FROM` può essere usata per specificare una o più origini per un'istruzione `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="cf478-109">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="cf478-110">Il tipo più semplice di clausola `FROM` consiste in una singola espressione di query che identifica una raccolta e un alias usati come origine in un'istruzione `SELECT`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-110">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>

`FROM C as c`

## <a name="from-clause-items"></a><span data-ttu-id="cf478-111">Elementi della clausola FROM</span><span class="sxs-lookup"><span data-stu-id="cf478-111">FROM Clause Items</span></span>

<span data-ttu-id="cf478-112">Ogni elemento della clausola `FROM` si riferisce a una raccolta di origine nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf478-112">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="cf478-113">supporta le classi seguenti di elementi della clausola `FROM`: elementi della clausola `FROM` semplici, elementi della clausola `JOIN FROM` ed elementi della clausola `APPLY FROM`</span><span class="sxs-lookup"><span data-stu-id="cf478-113">supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="cf478-114">Nelle sezioni seguenti è disponibile una descrizione più dettagliata per ognuno di questi elementi della clausola `FROM`.</span><span class="sxs-lookup"><span data-stu-id="cf478-114">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>

### <a name="simple-from-clause-item"></a><span data-ttu-id="cf478-115">Elemento della clausola FROM semplice</span><span class="sxs-lookup"><span data-stu-id="cf478-115">Simple FROM Clause Item</span></span>

<span data-ttu-id="cf478-116">L'elemento della clausola `FROM` più semplice è dato da una singola espressione che identifica una raccolta e un alias.</span><span class="sxs-lookup"><span data-stu-id="cf478-116">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="cf478-117">L'espressione può consistere semplicemente in un set di entità, o subquery, o in qualsiasi altra espressione corrispondente a un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="cf478-117">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="cf478-118">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="cf478-118">The following is an example:</span></span>

```sql
LOB.Customers as c
```

<span data-ttu-id="cf478-119">La specifica dell'alias è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cf478-119">The alias specification is optional.</span></span> <span data-ttu-id="cf478-120">Di seguito è riportato un esempio di specifica alternativa per l'elemento della clausola FROM precedente:</span><span class="sxs-lookup"><span data-stu-id="cf478-120">An alternate specification of the above from clause item could be the following:</span></span>

```sql
LOB.Customers
```

<span data-ttu-id="cf478-121">Se non viene specificato alcun alias, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generare un alias in base all'espressione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="cf478-121">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>

### <a name="join-from-clause-item"></a><span data-ttu-id="cf478-122">Elemento della clausola JOIN FROM</span><span class="sxs-lookup"><span data-stu-id="cf478-122">JOIN FROM Clause Item</span></span>

<span data-ttu-id="cf478-123">Un elemento della clausola `JOIN FROM` rappresenta un join tra due elementi della clausola `FROM`.</span><span class="sxs-lookup"><span data-stu-id="cf478-123">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="cf478-124">supporta cross join, inner join, left e right outer join e full outer join.</span><span class="sxs-lookup"><span data-stu-id="cf478-124">supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="cf478-125">Tutti questi join sono supportati in modo analogo al modo in cui sono supportati in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="cf478-125">All these joins are supported similar to the way that they are supported in Transact-SQL.</span></span> <span data-ttu-id="cf478-126">Come in Transact-SQL, i due elementi della clausola `FROM` che interessano il `JOIN` devono essere indipendenti.</span><span class="sxs-lookup"><span data-stu-id="cf478-126">As in Transact-SQL, the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="cf478-127">In altre parole, non possono essere correlati.</span><span class="sxs-lookup"><span data-stu-id="cf478-127">That is, they cannot be correlated.</span></span> <span data-ttu-id="cf478-128">In questi casi è possibile usare una clausola `CROSS APPLY` o `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="cf478-128">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>

#### <a name="cross-joins"></a><span data-ttu-id="cf478-129">Cross join</span><span class="sxs-lookup"><span data-stu-id="cf478-129">Cross Joins</span></span>

<span data-ttu-id="cf478-130">Un'espressione di query `CROSS JOIN` genera il prodotto cartesiano di due raccolte, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-130">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a><span data-ttu-id="cf478-131">Inner join</span><span class="sxs-lookup"><span data-stu-id="cf478-131">Inner Joins</span></span>

<span data-ttu-id="cf478-132">Un `INNER JOIN` genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-132">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c [INNER] JOIN D AS d ON e`

<span data-ttu-id="cf478-133">L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera.</span><span class="sxs-lookup"><span data-stu-id="cf478-133">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="cf478-134">Se non è specificata alcuna condizione `ON`, un `INNER JOIN` degenera in un `CROSS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="cf478-134">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>

#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="cf478-135">Left outer join e right outer join</span><span class="sxs-lookup"><span data-stu-id="cf478-135">Left Outer Joins and Right Outer Joins</span></span>

<span data-ttu-id="cf478-136">Un'espressione di query `OUTER JOIN` genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-136">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

<span data-ttu-id="cf478-137">L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera.</span><span class="sxs-lookup"><span data-stu-id="cf478-137">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="cf478-138">Se la condizione `ON` è falsa, l'espressione elabora comunque una sola istanza dell'elemento a sinistra abbinato all'elemento a destra con valore Null.</span><span class="sxs-lookup"><span data-stu-id="cf478-138">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>

<span data-ttu-id="cf478-139">Un `RIGHT OUTER JOIN` può essere espresso in modo simile.</span><span class="sxs-lookup"><span data-stu-id="cf478-139">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>

#### <a name="full-outer-joins"></a><span data-ttu-id="cf478-140">Full Outer Join</span><span class="sxs-lookup"><span data-stu-id="cf478-140">Full Outer Joins</span></span>

<span data-ttu-id="cf478-141">Un `FULL OUTER JOIN` esplicito genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-141">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>

`FROM C AS c FULL OUTER JOIN D AS d ON e`

<span data-ttu-id="cf478-142">L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera.</span><span class="sxs-lookup"><span data-stu-id="cf478-142">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="cf478-143">Se la condizione `ON` è falsa, l'espressione elabora comunque una sola istanza dell'elemento a sinistra abbinato all'elemento a destra con valore Null.</span><span class="sxs-lookup"><span data-stu-id="cf478-143">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="cf478-144">Elabora inoltre una sola istanza dell'elemento a destra abbinato all'elemento a sinistra con valore Null.</span><span class="sxs-lookup"><span data-stu-id="cf478-144">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>

> [!NOTE]
> <span data-ttu-id="cf478-145">Per mantenere la compatibilità con SQL-92, in Transact-SQL la parola chiave OUTER è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cf478-145">To preserve compatibility with SQL-92, in Transact-SQL the OUTER keyword is optional.</span></span> <span data-ttu-id="cf478-146">Pertanto, `LEFT JOIN`, `RIGHT JOIN` e `FULL JOIN` sono sinonimi di `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` e `FULL OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="cf478-146">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>

### <a name="apply-clause-item"></a><span data-ttu-id="cf478-147">Elemento della clausola APPLY</span><span class="sxs-lookup"><span data-stu-id="cf478-147">APPLY Clause Item</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="cf478-148">supporta due tipi di clausola `APPLY`: `CROSS APPLY` e `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="cf478-148">supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>

<span data-ttu-id="cf478-149">Una clausola `CROSS APPLY` produce un abbinamento univoco di ogni elemento della raccolta a sinistra con un elemento della raccolta prodotto dalla valutazione dell'espressione a destra.</span><span class="sxs-lookup"><span data-stu-id="cf478-149">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="cf478-150">Con una clausola `CROSS APPLY`, l'espressione a destra dipende dal punto di vista funzionale dall'elemento a sinistra, come illustrato nell'esempio di raccolta associata seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-150">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

<span data-ttu-id="cf478-151">Il comportamento di `CROSS APPLY` è simile a quello dell'elenco di join.</span><span class="sxs-lookup"><span data-stu-id="cf478-151">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="cf478-152">Se l'espressione a destra restituisce una raccolta vuota, `CROSS APPLY` non produce abbinamenti per quell'istanza dell'elemento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cf478-152">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>

<span data-ttu-id="cf478-153">Una clausola `OUTER APPLY` è simile a una `CROSS APPLY`, ad eccezione del fatto che viene prodotto un abbinamento anche se l'espressione a destra restituisce una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="cf478-153">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="cf478-154">Di seguito viene riportato un esempio di `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="cf478-154">The following is an example of an `OUTER APPLY`:</span></span>

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> <span data-ttu-id="cf478-155">Diversamente da Transact-SQL, non è necessario un passaggio di unnesting esplicito in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf478-155">Unlike in Transact-SQL, there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="cf478-156">gli operatori `CROSS` e `OUTER APPLY` sono stati introdotti nella SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="cf478-156">`CROSS` and `OUTER APPLY` operators were introduced in SQL Server 2005.</span></span> <span data-ttu-id="cf478-157">In alcuni casi, è possibile che la pipeline della query produca istruzioni Transact-SQL contenenti gli operatori `CROSS APPLY` e/o `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="cf478-157">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="cf478-158">Poiché alcuni provider back-end, incluse le versioni di SQL Server precedenti SQL Server 2005, non supportano questi operatori, tali query non possono essere eseguite su questi provider back-end.</span><span class="sxs-lookup"><span data-stu-id="cf478-158">Because some backend providers, including versions of SQL Server earlier than SQL Server 2005, do not support these operators, such queries cannot be executed on these backend providers.</span></span>
>
> <span data-ttu-id="cf478-159">Di seguito sono elencati alcuni degli scenari tipici che potrebbero determinare la presenza degli operatori `CROSS APPLY` e/o `OUTER APPLY` nella query di output: una subquery correlata con paging, AnyElement su una subquery correlata o su una raccolta prodotta dalla navigazione, query LINQ che usano metodi di raggruppamento che accettano un selettore elemento, una query nella quale viene specificata in modo esplicito una clausola `CROSS APPLY` o `OUTER APPLY`, una query che presenta un costrutto `DEREF` su un costrutto `REF`.</span><span class="sxs-lookup"><span data-stu-id="cf478-159">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>

## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="cf478-160">Più raccolte nella clausola FROM</span><span class="sxs-lookup"><span data-stu-id="cf478-160">Multiple Collections in the FROM Clause</span></span>

<span data-ttu-id="cf478-161">La clausola `FROM` può contenere più raccolte separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="cf478-161">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="cf478-162">In questi casi, si presuppone che le raccolte siano unite in join,</span><span class="sxs-lookup"><span data-stu-id="cf478-162">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="cf478-163">come se si trattasse di un CROSS JOIN a n vie.</span><span class="sxs-lookup"><span data-stu-id="cf478-163">Think of these as an n-way CROSS JOIN.</span></span>

<span data-ttu-id="cf478-164">Nell'esempio seguente `C` e `D` sono raccolte indipendenti, ma `c.Names` dipende da `C`.</span><span class="sxs-lookup"><span data-stu-id="cf478-164">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>

```sql
FROM C AS c, D AS d, c.Names AS e
```

<span data-ttu-id="cf478-165">L'esempio precedente rappresenta l'equivalente logico dell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf478-165">The previous example is logically equivalent to the following example:</span></span>

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a><span data-ttu-id="cf478-166">Correlazione sinistra</span><span class="sxs-lookup"><span data-stu-id="cf478-166">Left Correlation</span></span>
 <span data-ttu-id="cf478-167">Gli elementi nella clausola `FROM` possono fare riferimento a elementi specificati nelle clausole precedenti.</span><span class="sxs-lookup"><span data-stu-id="cf478-167">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="cf478-168">Nell'esempio seguente `C` e `D` sono raccolte indipendenti, ma `c.Names` è dipendente da `C`:</span><span class="sxs-lookup"><span data-stu-id="cf478-168">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>

```sql
from C as c, D as d, c.Names as e
```

<span data-ttu-id="cf478-169">Si tratta dell'equivalente logico di:</span><span class="sxs-lookup"><span data-stu-id="cf478-169">This is logically equivalent to:</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a><span data-ttu-id="cf478-170">Semantics</span><span class="sxs-lookup"><span data-stu-id="cf478-170">Semantics</span></span>

<span data-ttu-id="cf478-171">Dal punto di vista logico, si presuppone che le raccolte nella clausola `FROM` facciano parte di un cross join a `n` vie, tranne nel caso di un cross join a una via.</span><span class="sxs-lookup"><span data-stu-id="cf478-171">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="cf478-172">Gli alias nella clausola `FROM` vengono elaborati da sinistra verso destra e vengono aggiunti all'ambito corrente per i riferimenti futuri.</span><span class="sxs-lookup"><span data-stu-id="cf478-172">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="cf478-173">Si presuppone che la clausola `FROM` produca un multiset di righe.</span><span class="sxs-lookup"><span data-stu-id="cf478-173">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="cf478-174">Per ogni elemento della clausola `FROM` sarà presente un campo che rappresenterà un singolo elemento della raccolta in questione.</span><span class="sxs-lookup"><span data-stu-id="cf478-174">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>

<span data-ttu-id="cf478-175">La clausola `FROM` produce logicamente un multiset di righe di tipo Row(c, d, e) in cui si presuppone che i campi c, d ed e siano del tipo di elemento `C`, `D` e `c.Names`.</span><span class="sxs-lookup"><span data-stu-id="cf478-175">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="cf478-176">introduce nell'ambito un alias per ogni elemento della clausola `FROM` semplice.</span><span class="sxs-lookup"><span data-stu-id="cf478-176">introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="cf478-177">Nel frammento di clausola FROM seguente, ad esempio, i nomi introdotti nell'ambito sono c, d ed e.</span><span class="sxs-lookup"><span data-stu-id="cf478-177">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

<span data-ttu-id="cf478-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a differenza di Transact-SQL), la clausola `FROM` introduce solo gli alias nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="cf478-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike Transact-SQL), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="cf478-179">Tutti i riferimenti alle colonne, o proprietà, di tali raccolte devono essere qualificati con l'alias.</span><span class="sxs-lookup"><span data-stu-id="cf478-179">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>

## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="cf478-180">Pull delle chiavi da query annidate</span><span class="sxs-lookup"><span data-stu-id="cf478-180">Pulling Up Keys from Nested Queries</span></span>

<span data-ttu-id="cf478-181">Non sono supportati determinati tipi di query che richiedono l'estrazione delle chiavi da una query annidata.</span><span class="sxs-lookup"><span data-stu-id="cf478-181">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="cf478-182">Viene ad esempio considerata valida la query seguente:</span><span class="sxs-lookup"><span data-stu-id="cf478-182">For example, the following query is valid:</span></span>

```sql
select c.Orders from Customers as c
```

<span data-ttu-id="cf478-183">L'esempio seguente non è invece considerato valido, in quanto la query annidata non contiene chiavi:</span><span class="sxs-lookup"><span data-stu-id="cf478-183">However, the following query is not valid, because the nested query does not have any keys:</span></span>

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a><span data-ttu-id="cf478-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf478-184">See also</span></span>

- [<span data-ttu-id="cf478-185">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cf478-185">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cf478-186">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="cf478-186">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="cf478-187">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="cf478-187">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
