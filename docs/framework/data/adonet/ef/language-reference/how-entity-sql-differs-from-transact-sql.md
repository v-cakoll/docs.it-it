---
title: Differenze tra Entity SQL e Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 96e2283074b6c69e51bb7fee4d4f257cdb58d615
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615631"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="f9ed8-102">Differenze di Entity SQL rispetto a Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9ed8-102">How Entity SQL differs from Transact-SQL</span></span>

<span data-ttu-id="f9ed8-103">Questo articolo descrive le differenze tra Entity SQL e Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-103">This article describes the differences between Entity SQL and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="f9ed8-104">Supporto di ereditarietà e relazioni</span><span class="sxs-lookup"><span data-stu-id="f9ed8-104">Inheritance and Relationships Support</span></span>  
 <span data-ttu-id="f9ed8-105">Entity SQL funziona direttamente con gli schemi di entità concettuali e supporta le funzionalità del modello concettuale, ad esempio l'ereditarietà e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-105">Entity SQL works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="f9ed8-106">Quando si usa l'ereditarietà, è spesso utile selezionare le istanze di un sottotipo da una raccolta di istanze di supertipi.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="f9ed8-107">L'operatore [OfType](oftype-entity-sql.md) in Entity SQL (simile a `oftype` nelle sequenze C#) fornisce questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-107">The [oftype](oftype-entity-sql.md) operator in Entity SQL (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="f9ed8-108">Supporto per le raccolte</span><span class="sxs-lookup"><span data-stu-id="f9ed8-108">Support for Collections</span></span>  
 <span data-ttu-id="f9ed8-109">Entity SQL considera le raccolte come entità di prima classe.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-109">Entity SQL treats collections as first-class entities.</span></span> <span data-ttu-id="f9ed8-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-110">For example:</span></span>  
  
- <span data-ttu-id="f9ed8-111">Le espressioni della Collection sono valide in una clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="f9ed8-112">Le sottoquery `in` e `exists` sono state generalizzate per consentire qualsiasi raccolta.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="f9ed8-113">Una sottoquery è un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="f9ed8-114">`e1 in e2`e `exists(e)` sono i costrutti di Entity SQL per eseguire queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-114">`e1 in e2` and `exists(e)` are the Entity SQL constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="f9ed8-115">Le operazioni Set, ad esempio `union`, `intersect` ed `except`, possono ora essere usate sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="f9ed8-116">I join funzionano sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="f9ed8-117">Supporto per le espressioni</span><span class="sxs-lookup"><span data-stu-id="f9ed8-117">Support for Expressions</span></span>  
 <span data-ttu-id="f9ed8-118">Transact-SQL include sottoquery (tabelle) ed espressioni (righe e colonne).</span><span class="sxs-lookup"><span data-stu-id="f9ed8-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="f9ed8-119">Per supportare raccolte e raccolte nidificate, Entity SQL rende ogni elemento un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-119">To support collections and nested collections, Entity SQL makes everything an expression.</span></span> <span data-ttu-id="f9ed8-120">Entity SQL è più componibile rispetto a Transact-SQL, ogni espressione può essere usata ovunque.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-120">Entity SQL is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="f9ed8-121">Le espressioni di query restituiscono sempre raccolte dei tipi previsti e possono essere usate in qualunque posizione in cui è consentita un'espressione sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="f9ed8-122">Per informazioni sulle espressioni Transact-SQL non supportate in Entity SQL, vedere [espressioni](unsupported-expressions-entity-sql.md)non supportate.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-122">For information about Transact-SQL expressions that are not supported in Entity SQL, see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="f9ed8-123">Di seguito sono riportate tutte le query di Entity SQL valide:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-123">The following are all valid Entity SQL queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="f9ed8-124">Modalità di gestione uniforme delle sottoquery</span><span class="sxs-lookup"><span data-stu-id="f9ed8-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="f9ed8-125">Data l'enfasi sulle tabelle, Transact-SQL esegue l'interpretazione contestuale delle sottoquery.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="f9ed8-126">Una sottoquery nella clausola, ad esempio, `from` viene considerata come multiset (tabella).</span><span class="sxs-lookup"><span data-stu-id="f9ed8-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="f9ed8-127">La stessa sottoquery usata nella clausola `select` viene invece considerata come una sottoquery scalare.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="f9ed8-128">Analogamente, una sottoquery utilizzata sul lato sinistro di un `in` operatore viene considerata una sottoquery scalare, mentre il lato destro dovrebbe essere una sottoquery multiset.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="f9ed8-129">Entity SQL Elimina queste differenze.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-129">Entity SQL eliminates these differences.</span></span> <span data-ttu-id="f9ed8-130">Un'espressione dispone di un'interpretazione uniforme che non dipende dal contesto in cui viene usata.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> <span data-ttu-id="f9ed8-131">Entity SQL considera tutte le sottoquery come sottoquery multiset.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-131">Entity SQL considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="f9ed8-132">Se si desidera un valore scalare dalla sottoquery, Entity SQL fornisce l' `anyelement` operatore che opera su una raccolta (in questo caso, la sottoquery) ed estrae un valore singleton dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-132">If a scalar value is desired from the subquery, Entity SQL provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="f9ed8-133">Eliminazione della presenza di coercizioni implicite per le sottoquery</span><span class="sxs-lookup"><span data-stu-id="f9ed8-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="f9ed8-134">Un effetto collaterale della modalità di gestione uniforme delle sottoquery è la conversione implicita delle sottoquery in valori scalari.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="f9ed8-135">In particolare, in Transact-SQL, un multiset di righe (con un singolo campo) viene convertito in modo implicito in un valore scalare il cui tipo di dati è quello del campo.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="f9ed8-136">Entity SQL non supporta questa coercizione implicita.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-136">Entity SQL does not support this implicit coercion.</span></span> <span data-ttu-id="f9ed8-137">Entity SQL fornisce l' `ANYELEMENT` operatore per estrarre un valore singleton da una raccolta e una `select value` clausola per evitare di creare un wrapper di riga durante un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-137">Entity SQL provides the `ANYELEMENT` operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="f9ed8-138">SELECT VALUE: eliminazione della presenza del wrapper di riga implicito</span><span class="sxs-lookup"><span data-stu-id="f9ed8-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="f9ed8-139">La clausola SELECT in una sottoquery Transact-SQL crea in modo implicito un wrapper di riga intorno agli elementi nella clausola.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="f9ed8-140">Questo implica che non si possono creare raccolte di scalari o oggetti.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="f9ed8-141">Transact-SQL consente una coercizione implicita tra un oggetto `rowtype` con un campo e un valore singleton dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-141">Transact-SQL allows an implicit coercion between a `rowtype` with one field and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="f9ed8-142">Entity SQL fornisce la `select value` clausola per ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-142">Entity SQL provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="f9ed8-143">Nella clausola `select value` è possibile specificare un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="f9ed8-144">Quando si utilizza tale clausola, non viene costruito alcun wrapper di riga intorno agli elementi nella `select` clausola ed è possibile che venga generata una raccolta della forma desiderata, ad esempio `select value a` .</span><span class="sxs-lookup"><span data-stu-id="f9ed8-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example, `select value a`.</span></span>  
  
 <span data-ttu-id="f9ed8-145">Entity SQL fornisce anche il costruttore Row per costruire righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-145">Entity SQL also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="f9ed8-146">`select`accetta uno o più elementi nella proiezione e restituisce un record di dati con campi:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-146">`select` takes one or more elements in the projection and results in a data record with fields:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="f9ed8-147">Correlazione sinistra e utilizzo di alias</span><span class="sxs-lookup"><span data-stu-id="f9ed8-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="f9ed8-148">In Transact-SQL le espressioni in un determinato ambito (una singola clausola come `select` o `from` ) non possono fare riferimento a espressioni definite in precedenza nello stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="f9ed8-149">Alcuni dialetti di SQL (incluso Transact-SQL) supportano formati limitati di questi nella `from` clausola.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 <span data-ttu-id="f9ed8-150">Entity SQL generalizza le correlazioni a sinistra nella `from` clausola e le gestisce in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-150">Entity SQL generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="f9ed8-151">Le espressioni nella clausola `from` possono fare riferimento a definizioni precedenti (definizioni a sinistra) nella stessa clausola senza che sia necessaria sintassi aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="f9ed8-152">Entity SQL impone anche restrizioni aggiuntive per le query che coinvolgono le `group by` clausole.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-152">Entity SQL also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="f9ed8-153">Le espressioni nella `select` clausola e nella `having` clausola di tali query possono fare riferimento solo alle `group by` chiavi tramite i relativi alias.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="f9ed8-154">Il costrutto seguente è valido in Transact-SQL, ma non in Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-154">The following construct is valid in Transact-SQL but are not in Entity SQL:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="f9ed8-155">A tale scopo, Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-155">To do this in Entity SQL:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="f9ed8-156">Riferimento a colonne (proprietà) di tabelle (raccolte)</span><span class="sxs-lookup"><span data-stu-id="f9ed8-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="f9ed8-157">Tutti i riferimenti alle colonne in Entity SQL devono essere qualificati con l'alias di tabella.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-157">All column references in Entity SQL must be qualified with the table alias.</span></span> <span data-ttu-id="f9ed8-158">Il costrutto seguente (presupponendo che `a` sia una colonna valida della tabella `T` ) è valido in Transact-SQL ma non in Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in Entity SQL.</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="f9ed8-159">Il modulo Entity SQL è</span><span class="sxs-lookup"><span data-stu-id="f9ed8-159">The Entity SQL form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="f9ed8-160">Gli alias di tabella sono facoltativi nella clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="f9ed8-161">Il nome della tabella viene usato come l'alias implicito.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-161">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="f9ed8-162">Entity SQL consente anche il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-162">Entity SQL allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="f9ed8-163">Navigazione negli oggetti</span><span class="sxs-lookup"><span data-stu-id="f9ed8-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="f9ed8-164">Transact-SQL utilizza la notazione "." per fare riferimento a colonne di (una riga di) una tabella.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="f9ed8-165">Entity SQL estende questa notazione (presa in prestito dai linguaggi di programmazione) per supportare la navigazione tra le proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-165">Entity SQL extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="f9ed8-166">Se, ad esempio, `p` è un'espressione di tipo Person, di seguito viene riportata la sintassi Entity SQL per fare riferimento alla città dell'indirizzo di questa persona.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-166">For example, if `p` is an expression of type Person, the following is the Entity SQL syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="f9ed8-167">Nessun supporto per\*</span><span class="sxs-lookup"><span data-stu-id="f9ed8-167">No Support for \*</span></span>  
 <span data-ttu-id="f9ed8-168">Transact-SQL supporta la sintassi non qualificata \* come alias per l'intera riga e la sintassi qualificata \* (t. \* ) come collegamento per i campi di tale tabella.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="f9ed8-169">Transact-SQL consente inoltre di effettuare un'aggregazione Count ( \* ) speciale, che include valori null.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="f9ed8-170">Entity SQL non supporta il costrutto \*.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-170">Entity SQL does not support the \* construct.</span></span> <span data-ttu-id="f9ed8-171">Le query Transact-SQL del form `select * from T` e `select T1.* from T1, T2...` possono essere espresse in Entity SQL `select value t from T as t` rispettivamente come e `select value t1 from T1 as t1, T2 as t2...` .</span><span class="sxs-lookup"><span data-stu-id="f9ed8-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in Entity SQL as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="f9ed8-172">Questi costrutti consentono inoltre di gestire l'ereditarietà (sostituibilità del valore), mentre le varianti `select *` sono limitate alle proprietà di primo livello del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="f9ed8-173">Entity SQL non supporta l' `count(*)` aggregazione.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-173">Entity SQL does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="f9ed8-174">Usare invece `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="f9ed8-175">Modifiche a Group By</span><span class="sxs-lookup"><span data-stu-id="f9ed8-175">Changes to Group By</span></span>  
 <span data-ttu-id="f9ed8-176">Entity SQL supporta l'aliasing delle `group by` chiavi.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-176">Entity SQL supports aliasing of `group by` keys.</span></span> <span data-ttu-id="f9ed8-177">Le espressioni nella clausola `select` e nella clausola `having` devono fare riferimento alle chiavi `group by` attraverso questi alias.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="f9ed8-178">Ad esempio, questo Entity SQL sintassi:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-178">For example, this Entity SQL syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="f9ed8-179">... equivale al seguente Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="f9ed8-180">Aggregazioni basate sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="f9ed8-180">Collection-Based Aggregates</span></span>  
 <span data-ttu-id="f9ed8-181">Entity SQL supporta due tipi di aggregati.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-181">Entity SQL supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="f9ed8-182">Le aggregazioni basate sulle raccolte operano sulle raccolte e producono il risultato aggregato.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="f9ed8-183">Possono essere presenti in un punto qualsiasi nella query e non richiedono una clausola `group by`.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="f9ed8-184">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 <span data-ttu-id="f9ed8-185">Entity SQL supporta inoltre le aggregazioni di tipo SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-185">Entity SQL also supports SQL-style aggregates.</span></span> <span data-ttu-id="f9ed8-186">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="f9ed8-187">Utilizzo della clausola ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f9ed8-187">ORDER BY Clause Usage</span></span>  
<span data-ttu-id="f9ed8-188">Transact-SQL consente `ORDER BY` di specificare le clausole solo nel blocco in primo piano `SELECT .. FROM .. WHERE` .</span><span class="sxs-lookup"><span data-stu-id="f9ed8-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="f9ed8-189">In Entity SQL, è possibile utilizzare un'espressione annidata che `ORDER BY` può essere inserita in un punto qualsiasi della query, ma l'ordinamento in una query nidificata non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-189">In Entity SQL, you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="f9ed8-190">Identificatori</span><span class="sxs-lookup"><span data-stu-id="f9ed8-190">Identifiers</span></span>  
 <span data-ttu-id="f9ed8-191">In Transact-SQL il confronto degli identificatori si basa sulle regole di confronto del database corrente.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="f9ed8-192">In Entity SQL gli identificatori sono sempre senza distinzione tra maiuscole e minuscole e con distinzione tra caratteri accentati, ovvero Entity SQL distingue tra caratteri accentati e non accentati. ad esempio,' a' non è uguale a' mentre viene operata '.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-192">In Entity SQL, identifiers are always case insensitive and accent sensitive (that is, Entity SQL distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="f9ed8-193">Entity SQL considera le versioni delle lettere che risultano uguali, ma che sono da tabelle codici diverse come caratteri diversi.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-193">Entity SQL treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="f9ed8-194">Per altre informazioni, vedere [set di caratteri di input](input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f9ed8-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="f9ed8-195">Funzionalità Transact-SQL non disponibili in Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f9ed8-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="f9ed8-196">Le seguenti funzionalità di Transact-SQL non sono disponibili in Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-196">The following Transact-SQL functionality is not available in Entity SQL.</span></span>  
  
 <span data-ttu-id="f9ed8-197">DML</span><span class="sxs-lookup"><span data-stu-id="f9ed8-197">DML</span></span>  
 <span data-ttu-id="f9ed8-198">Entity SQL attualmente non fornisce supporto per le istruzioni DML (Insert, Update, Delete).</span><span class="sxs-lookup"><span data-stu-id="f9ed8-198">Entity SQL currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="f9ed8-199">DDL</span><span class="sxs-lookup"><span data-stu-id="f9ed8-199">DDL</span></span>  
 <span data-ttu-id="f9ed8-200">Entity SQL non fornisce alcun supporto per DDL nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-200">Entity SQL provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="f9ed8-201">programmazione imperativa</span><span class="sxs-lookup"><span data-stu-id="f9ed8-201">Imperative Programming</span></span>  
 <span data-ttu-id="f9ed8-202">Entity SQL non fornisce alcun supporto per la programmazione imperativa, a differenza di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-202">Entity SQL provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="f9ed8-203">Usare invece un linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="f9ed8-204">Funzioni di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f9ed8-204">Grouping Functions</span></span>  
 <span data-ttu-id="f9ed8-205">Entity SQL non fornisce ancora supporto per le funzioni di raggruppamento, ad esempio CUBE, ROLLUP e GROUPING_SET.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-205">Entity SQL does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="f9ed8-206">Funzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="f9ed8-206">Analytic Functions</span></span>  
 <span data-ttu-id="f9ed8-207">Entity SQL non è ancora disponibile il supporto per le funzioni analitiche.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-207">Entity SQL does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="f9ed8-208">Funzioni e operatori predefiniti</span><span class="sxs-lookup"><span data-stu-id="f9ed8-208">Built-in Functions, Operators</span></span>  
 <span data-ttu-id="f9ed8-209">Entity SQL supporta un subset di funzioni e operatori predefiniti di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-209">Entity SQL supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="f9ed8-210">Questi operatori e funzioni saranno supportati probabilmente dai provider dell'archivio principali.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-210">These operators and functions are likely to be supported by the major store providers.</span></span> <span data-ttu-id="f9ed8-211">Entity SQL usa le funzioni specifiche dell'archivio dichiarate in un manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-211">Entity SQL uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="f9ed8-212">Inoltre, il Entity Framework consente di dichiarare le funzioni di archiviazione predefinite e definite dall'utente, che possono essere usate da Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for Entity SQL to use.</span></span>  
  
 <span data-ttu-id="f9ed8-213">Hint</span><span class="sxs-lookup"><span data-stu-id="f9ed8-213">Hints</span></span>  
 <span data-ttu-id="f9ed8-214">Entity SQL non fornisce meccanismi per gli hint per la query.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-214">Entity SQL does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="f9ed8-215">Invio in batch dei risultati di query</span><span class="sxs-lookup"><span data-stu-id="f9ed8-215">Batching Query Results</span></span>  
 <span data-ttu-id="f9ed8-216">Entity SQL non supporta l'invio in batch dei risultati di query.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-216">Entity SQL does not support batching query results.</span></span> <span data-ttu-id="f9ed8-217">Ad esempio, di seguito è riportato un codice Transact-SQL valido (inviato come batch):</span><span class="sxs-lookup"><span data-stu-id="f9ed8-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="f9ed8-218">Tuttavia, il Entity SQL equivalente non è supportato:</span><span class="sxs-lookup"><span data-stu-id="f9ed8-218">However, the equivalent Entity SQL is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 <span data-ttu-id="f9ed8-219">Entity SQL supporta solo un'istruzione di query che produce risultati per ogni comando.</span><span class="sxs-lookup"><span data-stu-id="f9ed8-219">Entity SQL only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ed8-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9ed8-220">See also</span></span>

- [<span data-ttu-id="f9ed8-221">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f9ed8-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="f9ed8-222">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="f9ed8-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
