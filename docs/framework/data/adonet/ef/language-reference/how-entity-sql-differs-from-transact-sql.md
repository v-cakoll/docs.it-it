---
title: Differenze tra Entity SQL e Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: e0af0a415d812337d6abf449e9ee170526c3df0c
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833719"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="a2399-102">Differenze tra Entity SQL e Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2399-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="a2399-103">In questo argomento vengono descritte le [!INCLUDE[esql](../../../../../../includes/esql-md.md)] differenze tra e Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a2399-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="a2399-104">Supporto di ereditarietà e relazioni</span><span class="sxs-lookup"><span data-stu-id="a2399-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-105">interagisce direttamente con gli schemi di entità concettuali e supporta le funzionalità del modello concettuale, ad esempio l'ereditarietà e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="a2399-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="a2399-106">Quando si usa l'ereditarietà, è spesso utile selezionare le istanze di un sottotipo da una raccolta di istanze di supertipi.</span><span class="sxs-lookup"><span data-stu-id="a2399-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="a2399-107">Questa capacità è fornita dall'operatore [oftype](oftype-entity-sql.md) in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (simile a `oftype` nelle sequenze in C#).</span><span class="sxs-lookup"><span data-stu-id="a2399-107">The [oftype](oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="a2399-108">Supporto per le raccolte</span><span class="sxs-lookup"><span data-stu-id="a2399-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-109">Considera le raccolte come entità di prima classe.</span><span class="sxs-lookup"><span data-stu-id="a2399-109">treats collections as first-class entities.</span></span> <span data-ttu-id="a2399-110">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a2399-110">For example:</span></span>  
  
- <span data-ttu-id="a2399-111">Le espressioni della Collection sono valide in una clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="a2399-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="a2399-112">Le sottoquery `in` e `exists` sono state generalizzate per consentire qualsiasi raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2399-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="a2399-113">Una sottoquery è un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2399-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="a2399-114">`e1 in e2` e `exists(e)` sono i construct [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usati per eseguire queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="a2399-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="a2399-115">Le operazioni Set, ad esempio `union`, `intersect` ed `except`, possono ora essere usate sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a2399-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="a2399-116">I join funzionano sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a2399-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="a2399-117">Supporto per le espressioni</span><span class="sxs-lookup"><span data-stu-id="a2399-117">Support for Expressions</span></span>  
 <span data-ttu-id="a2399-118">Transact-SQL include sottoquery (tabelle) ed espressioni (righe e colonne).</span><span class="sxs-lookup"><span data-stu-id="a2399-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="a2399-119">Per supportare raccolte e raccolte nidificate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , in viene eseguita una qualsiasi espressione.</span><span class="sxs-lookup"><span data-stu-id="a2399-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-120">è più componibile rispetto a Transact-SQL: ogni espressione può essere usata ovunque.</span><span class="sxs-lookup"><span data-stu-id="a2399-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="a2399-121">Le espressioni di query restituiscono sempre raccolte dei tipi previsti e possono essere usate in qualunque posizione in cui è consentita un'espressione sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="a2399-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="a2399-122">Per informazioni sulle espressioni Transact-SQL non supportate in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere [espressioni](unsupported-expressions-entity-sql.md)non supportate.</span><span class="sxs-lookup"><span data-stu-id="a2399-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="a2399-123">Le query seguenti sono tutte query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] valide:</span><span class="sxs-lookup"><span data-stu-id="a2399-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="a2399-124">Modalità di gestione uniforme delle sottoquery</span><span class="sxs-lookup"><span data-stu-id="a2399-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="a2399-125">Data l'enfasi sulle tabelle, Transact-SQL esegue l'interpretazione contestuale delle sottoquery.</span><span class="sxs-lookup"><span data-stu-id="a2399-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="a2399-126">Una sottoquery nella `from` clausola, ad esempio, viene considerata come multiset (tabella).</span><span class="sxs-lookup"><span data-stu-id="a2399-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="a2399-127">La stessa sottoquery usata nella clausola `select` viene invece considerata come una sottoquery scalare.</span><span class="sxs-lookup"><span data-stu-id="a2399-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="a2399-128">Analogamente, una sottoquery utilizzata sul lato sinistro di un `in` operatore viene considerata una sottoquery scalare, mentre il lato destro dovrebbe essere una sottoquery multiset.</span><span class="sxs-lookup"><span data-stu-id="a2399-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="a2399-129">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono eliminate queste differenze.</span><span class="sxs-lookup"><span data-stu-id="a2399-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] eliminates these differences.</span></span> <span data-ttu-id="a2399-130">Un'espressione dispone di un'interpretazione uniforme che non dipende dal contesto in cui viene usata.</span><span class="sxs-lookup"><span data-stu-id="a2399-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-131">considera tutte le sottoquery come sottoquery multiset.</span><span class="sxs-lookup"><span data-stu-id="a2399-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="a2399-132">Se si desidera un valore scalare dalla sottoquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce l' `anyelement` operatore che opera su una raccolta (in questo caso, la sottoquery) ed estrae un valore singleton dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2399-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="a2399-133">Eliminazione della presenza di coercizioni implicite per le sottoquery</span><span class="sxs-lookup"><span data-stu-id="a2399-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="a2399-134">Un effetto collaterale della modalità di gestione uniforme delle sottoquery è la conversione implicita delle sottoquery in valori scalari.</span><span class="sxs-lookup"><span data-stu-id="a2399-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="a2399-135">In particolare, in Transact-SQL, un multiset di righe (con un singolo campo) viene convertito in modo implicito in un valore scalare il cui tipo di dati è quello del campo.</span><span class="sxs-lookup"><span data-stu-id="a2399-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-136">non supporta questa coercizione implicita.</span><span class="sxs-lookup"><span data-stu-id="a2399-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-137">fornisce un operatore ANYELEMENT per estrarre un valore Singleton da una raccolta e una clausola `select value` per evitare di creare un wrapper di riga durante un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="a2399-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="a2399-138">Seleziona valore: Evitare il wrapper di riga implicito</span><span class="sxs-lookup"><span data-stu-id="a2399-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="a2399-139">La clausola SELECT in una sottoquery Transact-SQL crea in modo implicito un wrapper di riga intorno agli elementi nella clausola.</span><span class="sxs-lookup"><span data-stu-id="a2399-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="a2399-140">Questo implica che non si possono creare raccolte di scalari o oggetti.</span><span class="sxs-lookup"><span data-stu-id="a2399-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="a2399-141">Transact-SQL consente una coercizione implicita tra un RowType con un campo e un valore singleton dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a2399-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-142">fornisce la clausola `select value` per ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="a2399-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="a2399-143">Nella clausola `select value` è possibile specificare un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="a2399-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="a2399-144">Quando viene usata questa clausola, non viene costruito alcun wrapper di riga intorno agli elementi nella clausola `select` e può essere prodotta una raccolta della forma desiderata, ad esempio `select value a`.</span><span class="sxs-lookup"><span data-stu-id="a2399-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-145">fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="a2399-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="a2399-146">`select` prende uno o più elementi nella proiezione e crea un record di dati con campi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a2399-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="a2399-147">Correlazione sinistra e utilizzo di alias</span><span class="sxs-lookup"><span data-stu-id="a2399-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="a2399-148">In Transact-SQL le espressioni in un determinato ambito (una singola clausola come `select` o `from`) non possono fare riferimento a espressioni definite in precedenza nello stesso ambito.</span><span class="sxs-lookup"><span data-stu-id="a2399-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="a2399-149">Alcuni dialetti di SQL (incluso Transact-SQL) supportano formati limitati di questi nella `from` clausola.</span><span class="sxs-lookup"><span data-stu-id="a2399-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-150">generalizza le `from` correlazioni a sinistra nella clausola e le gestisce in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="a2399-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="a2399-151">Le espressioni nella clausola `from` possono fare riferimento a definizioni precedenti (definizioni a sinistra) nella stessa clausola senza che sia necessaria sintassi aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a2399-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="a2399-152">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono inoltre imposte restrizioni aggiuntive sulle query che implicano l'uso di clausole `group by`.</span><span class="sxs-lookup"><span data-stu-id="a2399-152">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="a2399-153">Le espressioni nella `select` clausola e `having` nella clausola di tali query `group by` possono fare riferimento solo alle chiavi tramite i relativi alias.</span><span class="sxs-lookup"><span data-stu-id="a2399-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="a2399-154">Il costrutto seguente è valido in Transact-SQL, ma non [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in:</span><span class="sxs-lookup"><span data-stu-id="a2399-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="a2399-155">Per eseguire questa operazione in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2399-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="a2399-156">Riferimento a colonne (proprietà) di tabelle (raccolte)</span><span class="sxs-lookup"><span data-stu-id="a2399-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="a2399-157">Tutti i riferimenti alle colonne in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] devono essere qualificati con l'alias di tabella.</span><span class="sxs-lookup"><span data-stu-id="a2399-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="a2399-158">Il costrutto seguente (presupponendo che `a` sia una colonna valida della tabella `T`) è valido in Transact-SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)]ma non in.</span><span class="sxs-lookup"><span data-stu-id="a2399-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="a2399-159">Il formato in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è:</span><span class="sxs-lookup"><span data-stu-id="a2399-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="a2399-160">Gli alias di tabella sono facoltativi nella clausola `from`.</span><span class="sxs-lookup"><span data-stu-id="a2399-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="a2399-161">Il nome della tabella viene usato come l'alias implicito.</span><span class="sxs-lookup"><span data-stu-id="a2399-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-162">consente anche l'uso del formato seguente:</span><span class="sxs-lookup"><span data-stu-id="a2399-162">allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="a2399-163">Navigazione negli oggetti</span><span class="sxs-lookup"><span data-stu-id="a2399-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="a2399-164">Transact-SQL utilizza la notazione "." per fare riferimento a colonne di (una riga di) una tabella.</span><span class="sxs-lookup"><span data-stu-id="a2399-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-165">estende questa notazione (preso in prestito dai linguaggi di programmazione) per supportare la navigazione tra le proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a2399-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="a2399-166">Se, ad esempio, `p` è un'espressione del tipo Person, di seguito è riportata la sintassi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] che consente di fare riferimento alla città dell'indirizzo di tale persona.</span><span class="sxs-lookup"><span data-stu-id="a2399-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="a2399-167">Mancanza di supporto per \*</span><span class="sxs-lookup"><span data-stu-id="a2399-167">No Support for \*</span></span>  
 <span data-ttu-id="a2399-168">Transact-SQL supporta la sintassi \* non qualificata come alias per l'intera riga e la sintassi qualificata \* (t.\*) come collegamento per i campi di tale tabella.</span><span class="sxs-lookup"><span data-stu-id="a2399-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="a2399-169">Transact-SQL consente inoltre di effettuare un'aggregazione Count (\*) speciale, che include valori null.</span><span class="sxs-lookup"><span data-stu-id="a2399-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-170">non supporta il construct \*.</span><span class="sxs-lookup"><span data-stu-id="a2399-170">does not support the \* construct.</span></span> <span data-ttu-id="a2399-171">Le query Transact-SQL del form `select * from T` e `select T1.* from T1, T2...` possono essere espresse rispettivamente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in `select value t from T as t` come `select value t1 from T1 as t1, T2 as t2...`e.</span><span class="sxs-lookup"><span data-stu-id="a2399-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="a2399-172">Questi costrutti consentono inoltre di gestire l'ereditarietà (sostituibilità del valore), mentre le varianti `select *` sono limitate alle proprietà di primo livello del tipo dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a2399-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-173">non supporta l'aggregato `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="a2399-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="a2399-174">In alternativa, utilizzare `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="a2399-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="a2399-175">Modifiche a Group By</span><span class="sxs-lookup"><span data-stu-id="a2399-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-176">supporta l'uso di alias delle chiavi `group by`.</span><span class="sxs-lookup"><span data-stu-id="a2399-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="a2399-177">Le espressioni nella clausola `select` e nella clausola `having` devono fare riferimento alle chiavi `group by` attraverso questi alias.</span><span class="sxs-lookup"><span data-stu-id="a2399-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="a2399-178">La sintassi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="a2399-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="a2399-179">... equivale al seguente Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="a2399-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="a2399-180">Aggregazioni basate sulle raccolte</span><span class="sxs-lookup"><span data-stu-id="a2399-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-181">supporta due tipi di aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="a2399-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="a2399-182">Le aggregazioni basate sulle raccolte operano sulle raccolte e producono il risultato aggregato.</span><span class="sxs-lookup"><span data-stu-id="a2399-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="a2399-183">Possono essere presenti in un punto qualsiasi nella query e non richiedono una clausola `group by`.</span><span class="sxs-lookup"><span data-stu-id="a2399-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="a2399-184">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a2399-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-185">supporta inoltre le aggregazioni di tipo SQL.</span><span class="sxs-lookup"><span data-stu-id="a2399-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="a2399-186">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a2399-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="a2399-187">Utilizzo della clausola ORDER BY</span><span class="sxs-lookup"><span data-stu-id="a2399-187">ORDER BY Clause Usage</span></span>  
<span data-ttu-id="a2399-188">Transact-SQL consente di specificare le clausole `ORDER BY` solo nel blocco `SELECT .. FROM .. WHERE` in primo piano.</span><span class="sxs-lookup"><span data-stu-id="a2399-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="a2399-189">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è possibile utilizzare un'espressione `ORDER BY` annidata che può essere inserita in un punto qualsiasi della query, ma l'ordinamento in una query nidificata non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="a2399-189">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
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
  
## <a name="identifiers"></a><span data-ttu-id="a2399-190">Identificatori</span><span class="sxs-lookup"><span data-stu-id="a2399-190">Identifiers</span></span>  
 <span data-ttu-id="a2399-191">In Transact-SQL il confronto degli identificatori si basa sulle regole di confronto del database corrente.</span><span class="sxs-lookup"><span data-stu-id="a2399-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="a2399-192">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], gli identificatori non applicano mai la distinzione tra maiuscole e minuscole, mentre applicano la distinzione tra caratteri accentati e non accentati. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene infatti applicata la distinzione tra caratteri accentati e non accentati, ad esempio 'a' è diverso da 'à'.</span><span class="sxs-lookup"><span data-stu-id="a2399-192">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="a2399-193">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le versioni delle lettere che hanno lo stesso aspetto ma che provengono da tabelle codici diverse vengono gestite come caratteri differenti.</span><span class="sxs-lookup"><span data-stu-id="a2399-193">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="a2399-194">Per altre informazioni, vedere [set di caratteri di input](input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a2399-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="a2399-195">Funzionalità Transact-SQL non disponibili in Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a2399-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="a2399-196">La seguente funzionalità di Transact-SQL non è disponibile [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in.</span><span class="sxs-lookup"><span data-stu-id="a2399-196">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="a2399-197">DML</span><span class="sxs-lookup"><span data-stu-id="a2399-197">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-198">non fornisce attualmente supporto per le istruzioni DML (Insert, Update, Delete).</span><span class="sxs-lookup"><span data-stu-id="a2399-198">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="a2399-199">DDL</span><span class="sxs-lookup"><span data-stu-id="a2399-199">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-200">non fornisce supporto per DDL nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="a2399-200">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="a2399-201">programmazione imperativa</span><span class="sxs-lookup"><span data-stu-id="a2399-201">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-202">non fornisce supporto per la programmazione imperativa, a differenza di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a2399-202">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="a2399-203">Usare invece un linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="a2399-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="a2399-204">Funzioni di raggruppamento</span><span class="sxs-lookup"><span data-stu-id="a2399-204">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-205">non fornisce ancora supporto per le funzioni di raggruppamento (ad esempio CUBE, ROLLUP e GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="a2399-205">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="a2399-206">Funzioni analitiche</span><span class="sxs-lookup"><span data-stu-id="a2399-206">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-207">non fornisce (ancora) supporto per le funzioni analitiche.</span><span class="sxs-lookup"><span data-stu-id="a2399-207">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="a2399-208">Funzioni e operatori predefiniti</span><span class="sxs-lookup"><span data-stu-id="a2399-208">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-209">supporta un subset di funzioni e operatori predefiniti di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a2399-209">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="a2399-210">Questi operatori e funzioni saranno supportati probabilmente dai provider dell'archivio principali.</span><span class="sxs-lookup"><span data-stu-id="a2399-210">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a2399-211">Usa le funzioni specifiche dell'archivio dichiarate in un manifesto del provider.</span><span class="sxs-lookup"><span data-stu-id="a2399-211">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="a2399-212">Inoltre, il Entity Framework consente di dichiarare le funzioni di archiviazione predefinite e definite dall'utente, per [!INCLUDE[esql](../../../../../../includes/esql-md.md)] l'utilizzo di.</span><span class="sxs-lookup"><span data-stu-id="a2399-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="a2399-213">Hint</span><span class="sxs-lookup"><span data-stu-id="a2399-213">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-214">non fornisce meccanismi per gli hint per le query.</span><span class="sxs-lookup"><span data-stu-id="a2399-214">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="a2399-215">Invio in batch dei risultati di query</span><span class="sxs-lookup"><span data-stu-id="a2399-215">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-216">non supporta l'invio in batch dei risultati di query.</span><span class="sxs-lookup"><span data-stu-id="a2399-216">does not support batching query results.</span></span> <span data-ttu-id="a2399-217">Ad esempio, di seguito è riportato un codice Transact-SQL valido (inviato come batch):</span><span class="sxs-lookup"><span data-stu-id="a2399-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="a2399-218">Tuttavia, l'espressione equivalente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è supportata:</span><span class="sxs-lookup"><span data-stu-id="a2399-218">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a2399-219">supporta solo un'istruzione di query che restituisce un risultato per comando.</span><span class="sxs-lookup"><span data-stu-id="a2399-219">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2399-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2399-220">See also</span></span>

- [<span data-ttu-id="a2399-221">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a2399-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="a2399-222">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="a2399-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
