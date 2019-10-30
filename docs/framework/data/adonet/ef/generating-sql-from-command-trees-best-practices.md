---
title: Procedure consigliate per la generazione di SQL dagli alberi dei comandi
ms.date: 03/30/2017
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
ms.openlocfilehash: 869722b91550855a184a74e706271c3e2d417b84
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039990"
---
# <a name="generating-sql-from-command-trees---best-practices"></a><span data-ttu-id="91e71-102">Procedure consigliate per la generazione di SQL dagli alberi dei comandi</span><span class="sxs-lookup"><span data-stu-id="91e71-102">Generating SQL from Command Trees - Best Practices</span></span>

<span data-ttu-id="91e71-103">Gli alberi dei comandi di query di output sono molto simili alle query esprimibili in SQL.</span><span class="sxs-lookup"><span data-stu-id="91e71-103">Output query command trees closely model queries expressible in SQL.</span></span> <span data-ttu-id="91e71-104">Per generare SQL da un albero dei comandi di output, tuttavia i writer del provider devono affrontare alcune difficoltà comuni.</span><span class="sxs-lookup"><span data-stu-id="91e71-104">However, there are certain common challenges for provider writers when generating SQL from an output command tree.</span></span> <span data-ttu-id="91e71-105">In questo argomento vengono illustrate tali difficoltà, mentre</span><span class="sxs-lookup"><span data-stu-id="91e71-105">This topic discusses these challenges.</span></span> <span data-ttu-id="91e71-106">nell'argomento successivo il provider di esempio mostra come risolverle.</span><span class="sxs-lookup"><span data-stu-id="91e71-106">In the next topic, the sample provider shows how to address these challenges.</span></span>

## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a><span data-ttu-id="91e71-107">Nodi DbExpression di gruppo in un'istruzione SQL SELECT</span><span class="sxs-lookup"><span data-stu-id="91e71-107">Group DbExpression Nodes in a SQL SELECT Statement</span></span>

<span data-ttu-id="91e71-108">Un'istruzione SQL tipica presenta una struttura annidata della forma seguente:</span><span class="sxs-lookup"><span data-stu-id="91e71-108">A typical SQL statement has a nested structure of the following shape:</span></span>

```sql
SELECT …
FROM …
WHERE …
GROUP BY …
ORDER BY …
```

<span data-ttu-id="91e71-109">Una o più clausole potrebbero essere vuote.</span><span class="sxs-lookup"><span data-stu-id="91e71-109">One or more clauses may be empty.</span></span>  <span data-ttu-id="91e71-110">In qualsiasi riga potrebbe essere presente un'istruzione SELECT annidata.</span><span class="sxs-lookup"><span data-stu-id="91e71-110">A nested SELECT statement could occur in any of the lines.</span></span>

<span data-ttu-id="91e71-111">Una possibile conversione di un albero dei comandi delle query in un'istruzione SQL SELECT produrrebbe una sottoquery per ogni operatore relazionale.</span><span class="sxs-lookup"><span data-stu-id="91e71-111">A possible translation of a query command tree into a SQL SELECT statement would produce one subquery for every relational operator.</span></span> <span data-ttu-id="91e71-112">Ciò comporterebbe tuttavia la creazione di sottoquery annidate non necessarie e di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="91e71-112">However, that would lead to unnecessary nested subqueries that would be difficult to read.</span></span>  <span data-ttu-id="91e71-113">Per alcuni archivi dati le prestazioni delle query potrebbero essere scarse.</span><span class="sxs-lookup"><span data-stu-id="91e71-113">On some data stores, the query may perform poorly.</span></span>

<span data-ttu-id="91e71-114">Si consideri, come esempio, l'albero dei comandi di query seguente</span><span class="sxs-lookup"><span data-stu-id="91e71-114">As an example, consider the following query command tree</span></span>

```csharp
Project (
a.x,
   a = Filter(
      b.y = 5,
      b = Scan("TableA")
   )
)
```

<span data-ttu-id="91e71-115">Una conversione non efficace produrrebbe:</span><span class="sxs-lookup"><span data-stu-id="91e71-115">An inefficient translation would produce:</span></span>

```sql
SELECT a.x
FROM (   SELECT *
         FROM TableA as b
         WHERE b.y = 5) as a
```

<span data-ttu-id="91e71-116">Si osservi come ogni nodo dell'espressione relazionale diventa una nuova istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="91e71-116">Note that every relational expression node becomes a new SQL SELECT statement.</span></span>

<span data-ttu-id="91e71-117">Pertanto, è importante aggregare il maggior numero di nodi dell'espressione possibile in una sola istruzione SQL SELECT senza compromettere la correttezza.</span><span class="sxs-lookup"><span data-stu-id="91e71-117">Therefore, it is important to aggregate as many expression nodes as possible into a single SQL SELECT statement while preserving correctness.</span></span>

<span data-ttu-id="91e71-118">Il risultato di un'aggregazione di questo tipo per l'esempio sopra presentato sarebbe:</span><span class="sxs-lookup"><span data-stu-id="91e71-118">The result of such aggregation for the example presented above would be:</span></span>

```sql
SELECT b.x
FROM TableA as b
WHERE b.y = 5
```

## <a name="flatten-joins-in-a-sql-select-statement"></a><span data-ttu-id="91e71-119">Rendere bidimensionali i join in un'istruzione SQL SELECT</span><span class="sxs-lookup"><span data-stu-id="91e71-119">Flatten Joins in a SQL SELECT Statement</span></span>

<span data-ttu-id="91e71-120">Un caso di aggregazione di più nodi in un'unica istruzione SQL SELECT consiste nell'aggregazione di più espressioni di join in un'unica istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="91e71-120">One case of aggregating multiple nodes into a single SQL SELECT statement is aggregating multiple join expressions into a single SQL SELECT statement.</span></span> <span data-ttu-id="91e71-121">DbJoinExpression rappresenta un unico join tra due input.</span><span class="sxs-lookup"><span data-stu-id="91e71-121">DbJoinExpression represents a single join between two inputs.</span></span> <span data-ttu-id="91e71-122">È tuttavia possibile specificare più di un join come parte di un'unica istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="91e71-122">However, as part of a single SQL SELECT statement, more than one join can be specified.</span></span> <span data-ttu-id="91e71-123">In questo caso i join vengono eseguiti nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="91e71-123">In that case the joins are performed in the order specified.</span></span>

<span data-ttu-id="91e71-124">I join del lato sinistro, ovvero quelli che vengono visualizzati come join figlio a sinistra di un altro join, possono essere più facilmente resi bidimensionali in un'unica istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="91e71-124">Left spine joins, (joins that appear as a left child of another join) can be more easily flattened into a single SQL SELECT statement.</span></span> <span data-ttu-id="91e71-125">Si consideri, come esempio, l'albero dei comandi di query seguente:</span><span class="sxs-lookup"><span data-stu-id="91e71-125">For example, consider the following query command tree:</span></span>

```csharp
InnerJoin(
   a = LeftOuterJoin(
   b = Extent("TableA")
   c = Extent("TableB")
   ON b.y = c.x ),
   d = Extent("TableC")
   ON a.b.y = d.z
)
```

<span data-ttu-id="91e71-126">Tale struttura può essere convertita correttamente in:</span><span class="sxs-lookup"><span data-stu-id="91e71-126">This can be correctly translated into:</span></span>

```sql
SELECT *
FROM TableA as b
LEFT OUTER JOIN TableB as c ON b.y = c.x
INNER JOIN TableC as d ON b.y = d.z
```

<span data-ttu-id="91e71-127">I join non di sinistra non possono tuttavia essere facilmente resi bidimensionali e non è consigliabile provare a eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="91e71-127">However, non-left spine joins cannot easily be flattened, and you should not try to flatten them.</span></span> <span data-ttu-id="91e71-128">Ad esempio, i join dell'albero dei comandi di query seguente:</span><span class="sxs-lookup"><span data-stu-id="91e71-128">For example, the joins in the following query command tree:</span></span>

```csharp
InnerJoin(
   a = Extent("TableA")
   b = LeftOuterJoin(
   c = Extent("TableB")
   d = Extent("TableC")
   ON c.y = d.x),
   ON a.z = b.c.y
)
```

<span data-ttu-id="91e71-129">Verrebbero convertiti in un'istruzione SQL SELECT con una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="91e71-129">Would be translated to a SQL SELECT statement with a sub-query.</span></span>

```sql
SELECT *
FROM TableA as a
INNER JOIN (SELECT *
   FROM TableB as c
   LEFT OUTER JOIN TableC as d
   ON c.y = d.x) as b
ON b.y = d.z
```

## <a name="input-alias-redirecting"></a><span data-ttu-id="91e71-130">Reindirizzamento degli alias di input</span><span class="sxs-lookup"><span data-stu-id="91e71-130">Input Alias Redirecting</span></span>

<span data-ttu-id="91e71-131">Per comprendere il reindirizzamento degli alias di input, si consideri la struttura delle espressioni relazionali, ad esempio DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression e DbSkipExpression.</span><span class="sxs-lookup"><span data-stu-id="91e71-131">To explain input alias redirecting, consider the structure of the relational expressions, such as DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression, and DbSkipExpression.</span></span>

<span data-ttu-id="91e71-132">Per ognuno di questi tipi sono disponibili una o più proprietà Input che descrivono una raccolta di input e, per rappresentare ogni elemento di tale input durante un attraversamento della raccolta, viene usata una variabile di associazione che corrisponde a ogni input.</span><span class="sxs-lookup"><span data-stu-id="91e71-132">Each of these types has one or more Input properties that describe an input collection, and a binding variable corresponding to each input is used to represent each element of that input during a collection traversal.</span></span> <span data-ttu-id="91e71-133">La variabile di associazione viene usata quando si fa riferimento all'elemento di input, ad esempio nella proprietà Predicate di un oggetto DbFilterExpression o nella proprietà Projection di un oggetto DbProjectExpression.</span><span class="sxs-lookup"><span data-stu-id="91e71-133">The binding variable is used when referring to the input element, for example in the Predicate property of a DbFilterExpression or the Projection property of a DbProjectExpression.</span></span>

<span data-ttu-id="91e71-134">Quando si aggregano più nodi dell'espressione relazionale in una sola istruzione SQL SELECT e si valuta un'espressione che fa parte di un'espressione relazionale, ad esempio parte della proprietà Projection di un oggetto DbProjectExpression, la variabile di associazione usata potrebbe non corrispondere all'alias dell'input, in quanto più associazioni di espressioni dovrebbero essere reindirizzate a un solo extent.</span><span class="sxs-lookup"><span data-stu-id="91e71-134">When aggregating more relational expression nodes into a single SQL SELECT statement, and evaluating an expression that is part of a relational expression (for example part of the Projection property of a DbProjectExpression) the binding variable that it uses may not be the same as the alias of the input, as multiple expression bindings would have to be redirected to a single extent.</span></span>  <span data-ttu-id="91e71-135">Questo problema viene definito ridenominazione degli alias.</span><span class="sxs-lookup"><span data-stu-id="91e71-135">This problem is called alias renaming.</span></span>

<span data-ttu-id="91e71-136">Si consideri il primo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="91e71-136">Consider the first example in this topic.</span></span> <span data-ttu-id="91e71-137">Se si esegue la conversione semplice e si converte Projection a.x (DbPropertyExpression(a, x)), è corretto convertirlo in `a.x`, in quanto all'input è stato associato l'alias "a" per creare corrispondenza con la variabile di associazione.</span><span class="sxs-lookup"><span data-stu-id="91e71-137">If doing the naïve translation and translating the Projection a.x (DbPropertyExpression(a, x)), it is correct to translate it into `a.x` because we have aliased the input as "a" to match the binding variable.</span></span>  <span data-ttu-id="91e71-138">Quando tuttavia si aggregano entrambi i nodi in un'unica istruzione SQL SELECT, è necessario convertire lo stesso oggetto DbPropertyExpression in `b.x`, in quanto all'input è stato associato l'alias "b".</span><span class="sxs-lookup"><span data-stu-id="91e71-138">However, when aggregating both the nodes into a single SQL SELECT statement, you need to translate the same DbPropertyExpression into `b.x`, as the input has been aliased with "b".</span></span>

## <a name="join-alias-flattening"></a><span data-ttu-id="91e71-139">Bidimensionalità degli alias di join</span><span class="sxs-lookup"><span data-stu-id="91e71-139">Join Alias Flattening</span></span>

<span data-ttu-id="91e71-140">A differenza di qualsiasi altra espressione relazionale di un albero dei comandi di output, DbJoinExpression restituisce un tipo di risultato costituito da una riga formata da due colonne, ognuna delle quali corrisponde a uno degli input.</span><span class="sxs-lookup"><span data-stu-id="91e71-140">Unlike any other relational expression in an output command tree, the DbJoinExpression outputs a result type that is a row consisting of two columns, each of which corresponds to one of the inputs.</span></span> <span data-ttu-id="91e71-141">Quando un DbPropertyExpression viene compilato per accedere a una proprietà scalare originata da un join, viene eseguita su un'altra DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="91e71-141">When a DbPropertyExpression is built to access a scalar property originating from a join, it is over another DbPropertyExpression.</span></span>

<span data-ttu-id="91e71-142">Gli esempi includono "a.b.y" nell'esempio 2 e "b.c.y" nell'esempio 3.</span><span class="sxs-lookup"><span data-stu-id="91e71-142">Examples include "a.b.y" in example 2 and "b.c.y" in example 3.</span></span> <span data-ttu-id="91e71-143">Nelle istruzioni SQL corrispondenti tuttavia vi si fa riferimento come a "b.y".</span><span class="sxs-lookup"><span data-stu-id="91e71-143">However in the corresponding SQL statements these are referred as "b.y".</span></span> <span data-ttu-id="91e71-144">Questa nuova assegnazione degli alias viene denominata bidimensionalità degli alias di join.</span><span class="sxs-lookup"><span data-stu-id="91e71-144">This re-aliasing is called join alias flattening.</span></span>

## <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="91e71-145">Ridenominazione dei nomi di colonna e degli alias degli extent</span><span class="sxs-lookup"><span data-stu-id="91e71-145">Column Name and Extent Alias Renaming</span></span>

<span data-ttu-id="91e71-146">Se è necessario completare con una proiezione una query SQL SELECT che presenta un join, quando si enumerano tutte le colonne coinvolte dagli input, è possibile che si verifichi un conflitto di nomi, in quanto più input potrebbero avere lo stesso nome di colonna.</span><span class="sxs-lookup"><span data-stu-id="91e71-146">If a SQL SELECT query that has a join has to be completed with a projection, when enumerating all the participating columns from the inputs, a name collision may occur, as more than one input may have the same column name.</span></span> <span data-ttu-id="91e71-147">Usare un nome diverso per la colonna per evitare il conflitto.</span><span class="sxs-lookup"><span data-stu-id="91e71-147">Use a different name for the column to avoid the collision.</span></span>

<span data-ttu-id="91e71-148">Inoltre, quando si rendono bidimensionali i join, è possibile che si verifichi un conflitto tra gli alias delle tabelle coinvolte (o sottoquery). In questo caso, è necessario rinominarle.</span><span class="sxs-lookup"><span data-stu-id="91e71-148">Also, when flattening joins, participating tables (or subqueries) may have colliding aliases in which case these need to be renamed.</span></span>

## <a name="avoid-select-"></a><span data-ttu-id="91e71-149">Evitare SELECT \*</span><span class="sxs-lookup"><span data-stu-id="91e71-149">Avoid SELECT \*</span></span>

<span data-ttu-id="91e71-150">Non usare `SELECT *` per effettuare la selezione dalle tabelle di base.</span><span class="sxs-lookup"><span data-stu-id="91e71-150">Do not use `SELECT *` to select from base tables.</span></span> <span data-ttu-id="91e71-151">Il modello di archiviazione in un'applicazione Entity Framework può includere solo un subset delle colonne presenti nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="91e71-151">The storage model in an Entity Framework application may only include a subset of the columns that are in the database table.</span></span> <span data-ttu-id="91e71-152">In questo caso, è possibile che `SELECT *` produca un risultato errato.</span><span class="sxs-lookup"><span data-stu-id="91e71-152">In this case, `SELECT *` may produce an incorrect result.</span></span> <span data-ttu-id="91e71-153">Al contrario, è necessario specificare tutte le colonne coinvolte tramite i nomi di colonna del tipo di risultato delle espressioni interessate.</span><span class="sxs-lookup"><span data-stu-id="91e71-153">Instead, you should specify all participating columns by using the column names from the result type of the participating expressions.</span></span>

## <a name="reuse-of-expressions"></a><span data-ttu-id="91e71-154">Riutilizzo delle espressioni</span><span class="sxs-lookup"><span data-stu-id="91e71-154">Reuse of Expressions</span></span>

<span data-ttu-id="91e71-155">È possibile riutilizzare le espressioni nell'albero dei comandi di query passato dal Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="91e71-155">Expressions may be reused in the query command tree passed by the Entity Framework.</span></span> <span data-ttu-id="91e71-156">Non presupporre che ogni espressione sia visualizzata solo una volta nell'albero dei comandi di query.</span><span class="sxs-lookup"><span data-stu-id="91e71-156">Do not assume that each expression appears only once in the query command tree.</span></span>

## <a name="mapping-primitive-types"></a><span data-ttu-id="91e71-157">Mapping di tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="91e71-157">Mapping Primitive Types</span></span>

<span data-ttu-id="91e71-158">Quando si esegue il mapping di tipi concettuali (EDM) ai tipi di provider, è necessario eseguire il mapping al tipo più ampio (Int32), in modo che sia possibile adattare tutti i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="91e71-158">When mapping conceptual (EDM) types to provider types, you should map to the widest type (Int32) so that all possible values fit.</span></span> <span data-ttu-id="91e71-159">Evitare inoltre di eseguire il mapping a tipi che non possono essere utilizzati per molte operazioni, come i tipi di BLOB, ad esempio `ntext` in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91e71-159">Also, avoid mapping to types that cannot be used for many operations, like BLOB types (for example, `ntext` in SQL Server).</span></span>

## <a name="see-also"></a><span data-ttu-id="91e71-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91e71-160">See also</span></span>

- [<span data-ttu-id="91e71-161">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="91e71-161">SQL Generation</span></span>](sql-generation.md)
