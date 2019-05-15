---
title: Tipi SQL-CLR non corrispondenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
ms.openlocfilehash: e51d999d5fcaf8180b4ea5189a3db9b6143a57db
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582728"
---
# <a name="sql-clr-type-mismatches"></a><span data-ttu-id="429c4-102">Tipi SQL-CLR non corrispondenti</span><span class="sxs-lookup"><span data-stu-id="429c4-102">SQL-CLR Type Mismatches</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="429c4-103">consente di automatizzare la maggior parte delle operazioni di conversione tra il modello a oggetti e SQL Server.</span><span class="sxs-lookup"><span data-stu-id="429c4-103">automates much of the translation between the object model and SQL Server.</span></span> <span data-ttu-id="429c4-104">Alcune situazioni impediscono tuttavia che la conversione venga eseguita esattamente.</span><span class="sxs-lookup"><span data-stu-id="429c4-104">Nevertheless, some situations prevent exact translation.</span></span> <span data-ttu-id="429c4-105">Nelle sezioni seguenti sono riepilogate queste chiavi mancate corrispondenze tra i tipi common language runtime (CLR) e i tipi di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="429c4-105">These key mismatches between the common language runtime (CLR) types and the SQL Server database types are summarized in the following sections.</span></span> <span data-ttu-id="429c4-106">È possibile trovare altre informazioni sui mapping dei tipi specifici e conversione di funzioni al [Mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) e [tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span><span class="sxs-lookup"><span data-stu-id="429c4-106">You can find more details about specific type mappings and function translation at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) and [Data Types and Functions](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span></span>

## <a name="data-types"></a><span data-ttu-id="429c4-107">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="429c4-107">Data Types</span></span>

<span data-ttu-id="429c4-108">La conversione tra CLR e SQL Server viene eseguita quando una query viene inviata al database e quando i risultati vengono restituiti al modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="429c4-108">Translation between the CLR and SQL Server occurs when a query is being sent to the database, and when the results are sent back to your object model.</span></span> <span data-ttu-id="429c4-109">Nella query Transact-SQL seguente sono ad esempio necessarie due conversioni di valori:</span><span class="sxs-lookup"><span data-stu-id="429c4-109">For example, the following Transact-SQL query requires two value conversions:</span></span>

```sql
Select DateOfBirth From Customer Where CustomerId = @id
```

<span data-ttu-id="429c4-110">Per poter eseguire la query in SQL Server, è necessario specificare il valore per il parametro Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-110">Before the query can be executed on SQL Server, the value for the Transact-SQL parameter must be specified.</span></span> <span data-ttu-id="429c4-111">In questo esempio il valore del parametro `id` deve prima essere convertito da un tipo <xref:System.Int32?displayProperty=nameWithType> CLR a un tipo `INT` SQL Server in modo da poter essere compreso dal database.</span><span class="sxs-lookup"><span data-stu-id="429c4-111">In this example, the `id` parameter value must first be translated from a CLR <xref:System.Int32?displayProperty=nameWithType> type to a SQL Server `INT` type so that the database can understand what the value is.</span></span> <span data-ttu-id="429c4-112">Per recuperare i risultati, la colonna `DateOfBirth` di SQL Server deve quindi essere convertita da un tipo `DATETIME` SQL Server a un tipo <xref:System.DateTime?displayProperty=nameWithType> CLR per l'uso nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="429c4-112">Then to retrieve the results, the SQL Server `DateOfBirth` column must be translated from a SQL Server `DATETIME` type to a CLR <xref:System.DateTime?displayProperty=nameWithType> type for use in the object model.</span></span> <span data-ttu-id="429c4-113">In questo esempio i tipi nel modello a oggetti CLR e nel database di SQL Server dispongono di mapping naturali.</span><span class="sxs-lookup"><span data-stu-id="429c4-113">In this example, the types in the CLR object model and SQL Server database have natural mappings.</span></span> <span data-ttu-id="429c4-114">Ma non sempre questo avviene.</span><span class="sxs-lookup"><span data-stu-id="429c4-114">But, this is not always the case.</span></span>

### <a name="missing-counterparts"></a><span data-ttu-id="429c4-115">Controparti mancanti</span><span class="sxs-lookup"><span data-stu-id="429c4-115">Missing Counterparts</span></span>

<span data-ttu-id="429c4-116">I tipi seguenti non dispongono di controparti logiche.</span><span class="sxs-lookup"><span data-stu-id="429c4-116">The following types do not have reasonable counterparts.</span></span>

- <span data-ttu-id="429c4-117">Mancate corrispondenze nello spazio dei nomi <xref:System> CLR:</span><span class="sxs-lookup"><span data-stu-id="429c4-117">Mismatches in the CLR <xref:System> namespace:</span></span>

  - <span data-ttu-id="429c4-118">**Unsigned Integer**.</span><span class="sxs-lookup"><span data-stu-id="429c4-118">**Unsigned integers**.</span></span> <span data-ttu-id="429c4-119">Per questi tipi viene in genere eseguito il mapping alle controparti con segno di dimensioni maggiori per evitare l'overflow.</span><span class="sxs-lookup"><span data-stu-id="429c4-119">These types are typically mapped to their signed counterparts of larger size to avoid overflow.</span></span> <span data-ttu-id="429c4-120">I valori letterali possono essere convertiti in un valore numerico con segno di dimensioni uguali o inferiori, in base al valore.</span><span class="sxs-lookup"><span data-stu-id="429c4-120">Literals can be converted to a signed numeric of the same or smaller size, based on value.</span></span>

  - <span data-ttu-id="429c4-121">**Booleano**.</span><span class="sxs-lookup"><span data-stu-id="429c4-121">**Boolean**.</span></span> <span data-ttu-id="429c4-122">Per questi tipi può essere eseguito il mapping a un valore numerico o stringa di un bit o maggiore.</span><span class="sxs-lookup"><span data-stu-id="429c4-122">These types can be mapped to a bit or larger numeric or string.</span></span> <span data-ttu-id="429c4-123">È possibile eseguire il mapping di un valore letterale a un'espressione che restituisca lo stesso valore, ad esempio, `1=1` in SQL per `True` in CLS.</span><span class="sxs-lookup"><span data-stu-id="429c4-123">A literal can be mapped to an expression that evaluates to the same value (for example, `1=1` in SQL for `True` in CLS).</span></span>

  - <span data-ttu-id="429c4-124">**TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="429c4-124">**TimeSpan**.</span></span> <span data-ttu-id="429c4-125">Questo tipo rappresenta la differenza tra due valori `DateTime` e non corrisponde al valore `timestamp` di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="429c4-125">This type represents the difference between two `DateTime` values and does not correspond to the `timestamp` of SQL Server.</span></span> <span data-ttu-id="429c4-126">In alcuni casi, è anche possibile eseguire il mapping del tipo <xref:System.TimeSpan?displayProperty=nameWithType> CLR al tipo `TIME` SQL Server.</span><span class="sxs-lookup"><span data-stu-id="429c4-126">The CLR <xref:System.TimeSpan?displayProperty=nameWithType> may also map to the SQL Server `TIME` type in some cases.</span></span> <span data-ttu-id="429c4-127">Il tipo `TIME` SQL Server consente di rappresentare solo valori positivi inferiori alle 24 ore.</span><span class="sxs-lookup"><span data-stu-id="429c4-127">The SQL Server `TIME` type was only intended to represent positive values less than 24 hours.</span></span> <span data-ttu-id="429c4-128">Il tipo <xref:System.TimeSpan> consente di rappresentare un intervallo molto più ampio.</span><span class="sxs-lookup"><span data-stu-id="429c4-128">The CLR <xref:System.TimeSpan> has a much larger range.</span></span>

  > [!NOTE]
  > <span data-ttu-id="429c4-129">I tipi di .NET Framework di SQL Server specifici <xref:System.Data.SqlTypes> non sono inclusi in questo confronto.</span><span class="sxs-lookup"><span data-stu-id="429c4-129">SQL Server-specific .NET Framework types in <xref:System.Data.SqlTypes> are not included in this comparison.</span></span>

- <span data-ttu-id="429c4-130">Mancate corrispondenze in SQL Server:</span><span class="sxs-lookup"><span data-stu-id="429c4-130">Mismatches in SQL Server:</span></span>

  - <span data-ttu-id="429c4-131">**Tipi di carattere a lunghezza fissa**.</span><span class="sxs-lookup"><span data-stu-id="429c4-131">**Fixed length character types**.</span></span> <span data-ttu-id="429c4-132">Transact-SQL viene fatta distinzione tra categorie Unicode e non Unicode e sono disponibili tre tipi distinti di ogni categoria: lunghezza fissa `nchar` / `char`, di lunghezza variabile `nvarchar` / `varchar`, e con dimensioni maggiori `ntext` / `text`.</span><span class="sxs-lookup"><span data-stu-id="429c4-132">Transact-SQL distinguishes between Unicode and non-Unicode categories and has three distinct types in each category: fixed length `nchar`/`char`, variable length `nvarchar`/`varchar`, and larger-sized `ntext`/`text`.</span></span> <span data-ttu-id="429c4-133">I tipi di carattere a lunghezza fissa possono essere mappati al tipo <xref:System.Char?displayProperty=nameWithType> CLR per il recupero di caratteri, ma in realtà non corrispondono esattamente allo stesso tipo sia in termini di conversione che di comportamento.</span><span class="sxs-lookup"><span data-stu-id="429c4-133">The fixed length character types could be mapped to the CLR <xref:System.Char?displayProperty=nameWithType> type for retrieving characters, but they do not really correspond to the same type in conversions and behavior.</span></span>

  - <span data-ttu-id="429c4-134">**Bit**.</span><span class="sxs-lookup"><span data-stu-id="429c4-134">**Bit**.</span></span> <span data-ttu-id="429c4-135">Anche se nel dominio `bit` è presente lo stesso numero di valori di `Nullable<Boolean>`, i due tipi sono diversi.</span><span class="sxs-lookup"><span data-stu-id="429c4-135">Although the `bit` domain has the same number of values as `Nullable<Boolean>`, the two are different types.</span></span> <span data-ttu-id="429c4-136">`Bit` accetta i valori `1` e `0` invece di `true` / `false`e non può essere usato come equivalente delle espressioni booleane.</span><span class="sxs-lookup"><span data-stu-id="429c4-136">`Bit` takes values `1` and `0` instead of `true`/`false`, and cannot be used as an equivalent to Boolean expressions.</span></span>

  - <span data-ttu-id="429c4-137">**Timestamp**.</span><span class="sxs-lookup"><span data-stu-id="429c4-137">**Timestamp**.</span></span> <span data-ttu-id="429c4-138">A differenza del tipo <xref:System.TimeSpan?displayProperty=nameWithType> CLR, il tipo `TIMESTAMP` SQL Server rappresenta un numero di 8 byte generato dal database, univoco per ogni aggiornamento e non basato sulla differenza tra valori <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="429c4-138">Unlike the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type, the SQL Server `TIMESTAMP` type represents an 8-byte number generated by the database that is unique for each update and is not based on the difference between <xref:System.DateTime> values.</span></span>

  - <span data-ttu-id="429c4-139">**Denaro** e **SmallMoney**.</span><span class="sxs-lookup"><span data-stu-id="429c4-139">**Money** and **SmallMoney**.</span></span> <span data-ttu-id="429c4-140">Per questi tipi è possibile eseguire il mapping a <xref:System.Decimal>, ma si tratta di tipi fondamentalmente diversi e come tali vengono gestiti dalle funzioni e conversioni basate su server.</span><span class="sxs-lookup"><span data-stu-id="429c4-140">These types can be mapped to <xref:System.Decimal> but are basically different types and are treated as such by server-based functions and conversions.</span></span>

### <a name="multiple-mappings"></a><span data-ttu-id="429c4-141">Più mapping</span><span class="sxs-lookup"><span data-stu-id="429c4-141">Multiple Mappings</span></span>

<span data-ttu-id="429c4-142">Vi sono molti tipi di dati SQL Server che è possibile mappare a uno o più tipi di dati CLR,</span><span class="sxs-lookup"><span data-stu-id="429c4-142">There are many SQL Server data types that you can map to one or more CLR data types.</span></span> <span data-ttu-id="429c4-143">nonché molti tipi di dati CLR che è possibile mappare a uno o più tipi SQL Server.</span><span class="sxs-lookup"><span data-stu-id="429c4-143">There are also many CLR types that you can map to one or more SQL Server types.</span></span> <span data-ttu-id="429c4-144">Anche se un mapping è supportato da LINQ to SQL, questo non significa che vi sia una perfetta corrispondenza tra i due tipi mappati tra CLR e SQL Server per quanto riguarda precisione, intervallo e semantica.</span><span class="sxs-lookup"><span data-stu-id="429c4-144">Although a mapping may be supported by LINQ to SQL, it does not mean that the two types mapped between the CLR and SQL Server are a perfect match in precision, range, and semantics.</span></span> <span data-ttu-id="429c4-145">Alcuni mapping possono includere differenze per quanto riguarda una o tutte queste dimensioni.</span><span class="sxs-lookup"><span data-stu-id="429c4-145">Some mappings may include differences in any or all of these dimensions.</span></span> <span data-ttu-id="429c4-146">È possibile trovare informazioni dettagliate su queste differenze potenziali per le varie possibilità di mapping in [Mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="429c4-146">You can find details about these potential differences for the various mapping possibilities at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>

### <a name="user-defined-types"></a><span data-ttu-id="429c4-147">Tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="429c4-147">User-defined Types</span></span>

<span data-ttu-id="429c4-148">I tipi CLR definiti dall'utente sono progettati per consentire di colmare la lacuna nel sistema di tipi.</span><span class="sxs-lookup"><span data-stu-id="429c4-148">User-defined CLR types are designed to help bridge the type system gap.</span></span> <span data-ttu-id="429c4-149">Tuttavia, fanno emergere problemi che richiamano l'attenzione sul controllo delle versioni dei tipi.</span><span class="sxs-lookup"><span data-stu-id="429c4-149">Nevertheless they surface interesting issues about type versioning.</span></span> <span data-ttu-id="429c4-150">Una modifica nella versione sul client potrebbe non corrispondere a una modifica nel tipo archiviato sul server database.</span><span class="sxs-lookup"><span data-stu-id="429c4-150">A change in the version on the client might not be matched by a change in the type stored on the database server.</span></span> <span data-ttu-id="429c4-151">Una modifica di questo genere causa un altro tipo non corrispondente in cui la semantica del tipo potrebbe non corrispondere e la lacuna nel controllo delle versioni diventerà molto probabilmente visibile.</span><span class="sxs-lookup"><span data-stu-id="429c4-151">Any such change causes another type mismatch where the type semantics might not match and the version gap is likely to become visible.</span></span> <span data-ttu-id="429c4-152">Ulteriori problemi si verificano durante il refactoring delle gerarchie di ereditarietà nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="429c4-152">Further complications occur as inheritance hierarchies are refactored in successive versions.</span></span>

## <a name="expression-semantics"></a><span data-ttu-id="429c4-153">Semantica dell'espressione</span><span class="sxs-lookup"><span data-stu-id="429c4-153">Expression Semantics</span></span>

<span data-ttu-id="429c4-154">Oltre alle coppie non corrispondenti tra tipi CLR e tipi di database, le espressioni aggiungono complessità ai casi di mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="429c4-154">In addition to the pairwise mismatch between CLR and database types, expressions add complexity to the mismatch.</span></span> <span data-ttu-id="429c4-155">È necessario considerare le errate corrispondenze nella semantica degli operatori, nella semantica delle funzioni, nella conversione implicita dei tipi e nelle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="429c4-155">Mismatches in operator semantics, function semantics, implicit type conversion, and precedence rules must be considered.</span></span>

<span data-ttu-id="429c4-156">Nelle sottosezioni seguenti viene illustrata l'errata corrispondenza tra espressioni apparentemente simili.</span><span class="sxs-lookup"><span data-stu-id="429c4-156">The following subsections illustrate the mismatch between apparently similar expressions.</span></span> <span data-ttu-id="429c4-157">È possibile generare espressioni SQL semanticamente equivalenti a una particolare espressione CLR.</span><span class="sxs-lookup"><span data-stu-id="429c4-157">It might be possible to generate SQL expressions that are semantically equivalent to a given CLR expression.</span></span> <span data-ttu-id="429c4-158">Non è tuttavia chiaro se le differenze semantiche tra espressioni apparentemente simili siano evidenti a un utente CLR e, pertanto, se le modifiche richieste per l'equivalenza semantica possano essere intenzionali o meno.</span><span class="sxs-lookup"><span data-stu-id="429c4-158">However, it is not clear whether the semantic differences between apparently similar expressions are evident to a CLR user, and therefore whether the changes that are required for semantic equivalence are intended or not.</span></span> <span data-ttu-id="429c4-159">Si tratta di un problema particolarmente critico quando un'espressione viene valutata per un set di valori.</span><span class="sxs-lookup"><span data-stu-id="429c4-159">This is an especially critical issue when an expression is evaluated for a set of values.</span></span> <span data-ttu-id="429c4-160">La visibilità della differenza può dipendere da dati ed essere difficilmente identificabile durante la scrittura del codice e il debug.</span><span class="sxs-lookup"><span data-stu-id="429c4-160">The visibility of the difference might depend on data- and be hard to identify during coding and debugging.</span></span>

### <a name="null-semantics"></a><span data-ttu-id="429c4-161">Semantica Null</span><span class="sxs-lookup"><span data-stu-id="429c4-161">Null Semantics</span></span>

<span data-ttu-id="429c4-162">Le espressioni SQL forniscono una logica a tre valori per le espressioni booleane.</span><span class="sxs-lookup"><span data-stu-id="429c4-162">SQL expressions provide three-valued logic for Boolean expressions.</span></span> <span data-ttu-id="429c4-163">Il risultato può essere vero, falso o null.</span><span class="sxs-lookup"><span data-stu-id="429c4-163">The result can be true, false, or null.</span></span> <span data-ttu-id="429c4-164">In CLR, invece, viene specificato un risultato booleano a due valori per i confronti che prevedono valori null.</span><span class="sxs-lookup"><span data-stu-id="429c4-164">By contrast, CLR specifies two-valued Boolean result for comparisons involving null values.</span></span> <span data-ttu-id="429c4-165">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="429c4-165">Consider the following code:</span></span>

[!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
[!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]

```sql
-- Assume col1 and col2 are integer columns with null values.
-- Assume that ANSI null behavior has not been explicitly
--  turned off.
Select …
From …
Where col1 = col2
-- Evaluates to null, not true and the corresponding row is not
--   selected.
-- To obtain matching behavior (i -> col1, j -> col2) change
--   the query to the following:
Select …
From …
Where
    col1 = col2
or (col1 is null and col2 is null)
-- (Visual Basic 'Nothing'.)
```

<span data-ttu-id="429c4-166">Si verifica un problema analogo presupponendo risultati a due valori.</span><span class="sxs-lookup"><span data-stu-id="429c4-166">A similar problem occurs with the assumption about two-valued results.</span></span>

[!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
[!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]

```sql
-- Assume col1 and col2 are nullable columns.
-- Assume that ANSI null behavior has not been explicitly
--   turned off.
Select …
From …
Where
    col1 = col2
or col1 != col2
-- Visual Basic: col1 <> col2.

-- Excludes the case where the boolean expression evaluates
--   to null. Therefore the where clause does not always
--   evaluate to true.
```

<span data-ttu-id="429c4-167">Nel caso precedente è possibile ottenere un comportamento equivalente nella generazione di codice SQL, tuttavia la conversione potrebbe non riflettere esattamente l'intenzione.</span><span class="sxs-lookup"><span data-stu-id="429c4-167">In the previous case, you can get equivalent behavior in generating SQL, but the translation might not accurately reflect your intention.</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="429c4-168">non è previsto C# `null` o Visual Basic `nothing` la semantica di confronto in SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-168">does not impose C# `null` or Visual Basic `nothing` comparison semantics on SQL.</span></span> <span data-ttu-id="429c4-169">Gli operatori di confronto vengono sintatticamente convertiti negli equivalenti SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-169">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="429c4-170">La semantica riflette la semantica SQL secondo quanto definito nelle impostazioni di connessione o del server.</span><span class="sxs-lookup"><span data-stu-id="429c4-170">The semantics reflect SQL semantics as defined by server or connection settings.</span></span> <span data-ttu-id="429c4-171">Due valori null sono considerati non uguali secondo le impostazioni di SQL Server predefinite, anche se è possibile modificare tali impostazioni per modificare la semantica.</span><span class="sxs-lookup"><span data-stu-id="429c4-171">Two null values are considered unequal under default SQL Server settings (although you can change the settings to change the semantics).</span></span> <span data-ttu-id="429c4-172">Indipendentemente da questa premessa, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non considera le impostazioni del server nella conversione della query.</span><span class="sxs-lookup"><span data-stu-id="429c4-172">Regardless, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings in query translation.</span></span>

<span data-ttu-id="429c4-173">Un confronto con il valore letterale `null` (`nothing`) viene convertito nella versione SQL appropriata (`is null` o `is not null`).</span><span class="sxs-lookup"><span data-stu-id="429c4-173">A comparison with the literal `null` (`nothing`) is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="429c4-174">Il valore di `null` (`nothing`) nelle regole di confronto viene definito da SQL Server. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non modifica le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="429c4-174">The value of `null` (`nothing`) in collation is defined by SQL Server; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not change the collation.</span></span>

### <a name="type-conversion-and-promotion"></a><span data-ttu-id="429c4-175">Conversione e promozione del tipo</span><span class="sxs-lookup"><span data-stu-id="429c4-175">Type Conversion and Promotion</span></span>

<span data-ttu-id="429c4-176">SQL supporta un vasta gamma di conversioni implicite nelle espressioni.</span><span class="sxs-lookup"><span data-stu-id="429c4-176">SQL supports a rich set of implicit conversions in expressions.</span></span> <span data-ttu-id="429c4-177">Espressioni simili in C# richiederebbero un cast esplicito.</span><span class="sxs-lookup"><span data-stu-id="429c4-177">Similar expressions in C# would require an explicit cast.</span></span> <span data-ttu-id="429c4-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="429c4-178">For example:</span></span>

- <span data-ttu-id="429c4-179">I tipi `Nvarchar` e `DateTime` possono essere confrontati in SQL senza cast espliciti, mentre in C# è richiesta la conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="429c4-179">`Nvarchar` and `DateTime` types can be compared in SQL without any explicit casts; C# requires explicit conversion.</span></span>

- <span data-ttu-id="429c4-180">In SQL `Decimal` viene convertito implicitamente in `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="429c4-180">`Decimal` is implicitly converted to `DateTime` in SQL.</span></span> <span data-ttu-id="429c4-181">C# non consente una conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="429c4-181">C# does not allow for an implicit conversion.</span></span>

<span data-ttu-id="429c4-182">In modo analogo, la precedenza dei tipi in Transact-SQL è diversa da quella in C#, in quanto il set di tipi sottostante è diverso.</span><span class="sxs-lookup"><span data-stu-id="429c4-182">Likewise, type precedence in Transact-SQL differs from type precedence in C# because the underlying set of types is different.</span></span> <span data-ttu-id="429c4-183">Non esiste infatti una chiara relazione di subset o superset tra gli elenchi di precedenza.</span><span class="sxs-lookup"><span data-stu-id="429c4-183">In fact, there is no clear subset/superset relationship between the precedence lists.</span></span> <span data-ttu-id="429c4-184">Ad esempio, il confronto di un tipo `nvarchar` con un tipo `varchar` causa la conversione implicita dell'espressione `varchar` in `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="429c4-184">For example, comparing an `nvarchar` with a `varchar` causes the implicit conversion of the `varchar` expression to `nvarchar`.</span></span> <span data-ttu-id="429c4-185">In CLR non viene fornita alcuna promozione equivalente.</span><span class="sxs-lookup"><span data-stu-id="429c4-185">The CLR provides no equivalent promotion.</span></span>

<span data-ttu-id="429c4-186">Nei casi più semplici queste differenze provocano la ridondanza di espressioni CLR con cast per un'espressione SQL corrispondente.</span><span class="sxs-lookup"><span data-stu-id="429c4-186">In simple cases, these differences cause CLR expressions with casts to be redundant for a corresponding SQL expression.</span></span> <span data-ttu-id="429c4-187">È importante notare che i risultati intermedi di un'espressione SQL potrebbero essere implicitamente promossi in un tipo privo di un'esatta controparte in C# e viceversa.</span><span class="sxs-lookup"><span data-stu-id="429c4-187">More importantly, the intermediate results of a SQL expression might be implicitly promoted to a type that has no accurate counterpart in C#, and vice versa.</span></span> <span data-ttu-id="429c4-188">Complessivamente le operazioni di test, debug e convalida di tali espressioni comportano un carico di lavoro significativo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="429c4-188">Overall, the testing, debugging, and validation of such expressions adds significant burden on the user.</span></span>

### <a name="collation"></a><span data-ttu-id="429c4-189">Regole di confronto</span><span class="sxs-lookup"><span data-stu-id="429c4-189">Collation</span></span>

<span data-ttu-id="429c4-190">Transact-SQL supporta regole di confronto esplicite come annotazioni ai tipi stringa di caratteri.</span><span class="sxs-lookup"><span data-stu-id="429c4-190">Transact-SQL supports explicit collations as annotations to character string types.</span></span> <span data-ttu-id="429c4-191">Queste regole di confronto determinano la validità di certi confronti.</span><span class="sxs-lookup"><span data-stu-id="429c4-191">These collations determine the validity of certain comparisons.</span></span> <span data-ttu-id="429c4-192">Ad esempio, è errato confrontare due colonne con regole di confronto esplicite diverse.</span><span class="sxs-lookup"><span data-stu-id="429c4-192">For example, comparing two columns with different explicit collations is an error.</span></span> <span data-ttu-id="429c4-193">L'utilizzo di un tipo stringa CTS molto semplificato non provoca tali errori.</span><span class="sxs-lookup"><span data-stu-id="429c4-193">The use of much simplified CTS string type does not cause such errors.</span></span> <span data-ttu-id="429c4-194">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="429c4-194">Consider the following example:</span></span>

```sql
create table T2 (
    Col1 nvarchar(10),
    Col2      nvarchar(10) collate Latin_general_ci_as
)
```

[!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
[!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]

```sql
Select …
From …
Where Col1 = Col2
-- Error, collation conflict.
```

<span data-ttu-id="429c4-195">In effetti, la sottoclausola delle regole di confronto crea un *tipo limitato* non sostituibile.</span><span class="sxs-lookup"><span data-stu-id="429c4-195">In effect, the collation subclause creates a *restricted type* that is not substitutable.</span></span>

<span data-ttu-id="429c4-196">In modo analogo, il criterio di ordinamento può essere significativamente diverso nei diversi sistemi di tipi.</span><span class="sxs-lookup"><span data-stu-id="429c4-196">Similarly, the sort order can be significantly different across the type systems.</span></span> <span data-ttu-id="429c4-197">Questa differenza influisce sull'ordinamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="429c4-197">This difference affects the sorting of results.</span></span> <span data-ttu-id="429c4-198"><xref:System.Guid> viene ordinato in base a tutti i 16 byte in ordine lessicografico (`IComparable()`), mentre in T-SQL vengono confrontati i GUID in base all'ordine seguente: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span><span class="sxs-lookup"><span data-stu-id="429c4-198"><xref:System.Guid> is sorted on all 16 bytes by lexicographic order (`IComparable()`), whereas T-SQL compares GUIDs in the following order: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span></span> <span data-ttu-id="429c4-199">Questo ordinamento veniva eseguito in SQL 7.0 dove i GUID generati da NT erano caratterizzati da tale ordine di ottetti.</span><span class="sxs-lookup"><span data-stu-id="429c4-199">This ordering was done in SQL 7.0 when NT-generated GUIDs had such an octet order.</span></span> <span data-ttu-id="429c4-200">Questo approccio assicura che i GUID generati nello stesso cluster del nodo vengano uniti in ordine sequenziale in base al timestamp.</span><span class="sxs-lookup"><span data-stu-id="429c4-200">The approach ensured that GUIDs generated at the same node cluster came together in sequential order according to timestamp.</span></span> <span data-ttu-id="429c4-201">L'approccio è inoltre utile per la compilazione di indici (gli inserimenti diventano aggiunte anziché I/O casuali).</span><span class="sxs-lookup"><span data-stu-id="429c4-201">The approach was also useful for building indexes (inserts become appends instead of random IOs).</span></span> <span data-ttu-id="429c4-202">Successivamente questo ordine è stato codificato in Windows per evitare problemi di privacy, ma in SQL è stata mantenuta la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="429c4-202">The order was scrambled later in Windows because of privacy concerns, but SQL must maintain compatibility.</span></span> <span data-ttu-id="429c4-203">Soluzione alternativa consiste nell'usare <xref:System.Data.SqlTypes.SqlGuid> invece di <xref:System.Guid>.</span><span class="sxs-lookup"><span data-stu-id="429c4-203">A workaround is to use <xref:System.Data.SqlTypes.SqlGuid> instead of <xref:System.Guid>.</span></span>

### <a name="operator-and-function-differences"></a><span data-ttu-id="429c4-204">Differenze di operatori e funzioni</span><span class="sxs-lookup"><span data-stu-id="429c4-204">Operator and Function Differences</span></span>

<span data-ttu-id="429c4-205">Operatori e funzioni essenzialmente simili presentano tuttavia una semantica leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="429c4-205">Operators and functions that are essentially comparable have subtly different semantics.</span></span> <span data-ttu-id="429c4-206">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="429c4-206">For example:</span></span>

- <span data-ttu-id="429c4-207">In C# viene specificata una semantica di corto circuito basata su un ordine lessicale di operandi per gli operatori logici `&&` e `||`.</span><span class="sxs-lookup"><span data-stu-id="429c4-207">C# specifies short circuit semantics based on lexical order of operands for logical operators `&&` and `||`.</span></span> <span data-ttu-id="429c4-208">D'altra parte, SQL è destinato alle query basate su set, pertanto consente all'utilità di ottimizzazione di stabilire più liberamente l'ordine di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="429c4-208">SQL on the other hand is targeted for set-based queries and therefore provides more freedom for the optimizer to decide the order of execution.</span></span> <span data-ttu-id="429c4-209">Di seguito sono riportate alcune implicazioni:</span><span class="sxs-lookup"><span data-stu-id="429c4-209">Some of the implications include the following:</span></span>

  - <span data-ttu-id="429c4-210">Conversione semanticamente equivalente richiederebbe "`CASE` ...</span><span class="sxs-lookup"><span data-stu-id="429c4-210">Semantically equivalent translation would require "`CASE` …</span></span> <span data-ttu-id="429c4-211">`WHEN` …</span><span class="sxs-lookup"><span data-stu-id="429c4-211">`WHEN` …</span></span> <span data-ttu-id="429c4-212">`THEN`"un costrutto in SQL per evitare di riordinare l'esecuzione dell'operando.</span><span class="sxs-lookup"><span data-stu-id="429c4-212">`THEN`" construct in SQL to avoid reordering of operand execution.</span></span>

  - <span data-ttu-id="429c4-213">Una conversione non rigida al `AND` / `OR` operatori potrebbe provocare errori imprevisti se il C# espressione si basa sulla valutazione del secondo operando in corso in base al risultato della valutazione del primo operando.</span><span class="sxs-lookup"><span data-stu-id="429c4-213">A loose translation to `AND`/`OR` operators could cause unexpected errors if the C# expression relies on evaluation the second operand being based on the result of the evaluation of the first operand.</span></span>

- <span data-ttu-id="429c4-214">`Round()` funzione ha una semantica diversa in .NET Framework e in T-SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-214">`Round()` function has different semantics in .NET Framework and in T-SQL.</span></span>

- <span data-ttu-id="429c4-215">L'indice iniziale per le stringhe è 0 in CLR, ma 1 in SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-215">Starting index for strings is 0 in the CLR but 1 in SQL.</span></span> <span data-ttu-id="429c4-216">Pertanto, qualsiasi funzione con un indice deve essere sottoposta alla conversione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="429c4-216">Therefore, any function that has index needs index translation.</span></span>

- <span data-ttu-id="429c4-217">CLR supporta l'operatore modulo ("%") per i numeri a virgola mobile, al contrario di SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-217">The CLR supports modulus (‘%’) operator for floating point numbers but SQL does not.</span></span>

- <span data-ttu-id="429c4-218">L'operatore `Like` acquisisce efficacemente gli overload automatici in base a conversioni implicite.</span><span class="sxs-lookup"><span data-stu-id="429c4-218">The `Like` operator effectively acquires automatic overloads based on implicit conversions.</span></span> <span data-ttu-id="429c4-219">Anche se l'operatore `Like` viene definito per il funzionamento con tipi stringa di caratteri, la conversione implicita da tipi numerici o tipi `DateTime` consente di usare anche i tipi non stringa con `Like`.</span><span class="sxs-lookup"><span data-stu-id="429c4-219">Although the `Like` operator is defined to operate on character string types, implicit conversion from numeric types or `DateTime` types allows for those non-string types to be used with `Like` just as well.</span></span> <span data-ttu-id="429c4-220">In CTS non esistono conversioni implicite confrontabili.</span><span class="sxs-lookup"><span data-stu-id="429c4-220">In CTS, comparable implicit conversions do not exist.</span></span> <span data-ttu-id="429c4-221">Di conseguenza sono necessari overload aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="429c4-221">Therefore, additional overloads are needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="429c4-222">Questo comportamento dell'operatore `Like` si applica solo a C#; la parola chiave `Like` di Visual Basic rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="429c4-222">This `Like` operator behavior applies to C# only; the Visual Basic `Like` keyword is unchanged.</span></span>

- <span data-ttu-id="429c4-223">Overflow viene sempre controllato in SQL, ma deve essere specificato in modo esplicito C# (non in Visual Basic) per evitare wraparound.</span><span class="sxs-lookup"><span data-stu-id="429c4-223">Overflow is always checked in SQL but it has to be explicitly specified in C# (not in Visual Basic) to avoid wraparound.</span></span> <span data-ttu-id="429c4-224">Date le colonne di valori integer C1, C2 e C3, se C1+C2 viene archiviato in C3 (aggiorna il set T C3 = C1 + C2).</span><span class="sxs-lookup"><span data-stu-id="429c4-224">Given integer columns C1, C2 and C3, if C1+C2 is stored in C3 (Update T Set C3 = C1 + C2).</span></span>

    ```sql
    create table T3 (
        Col1      integer,
        Col2      integer
    )
    insert into T3 (col1, col2) values (2147483647, 5)
    -- Valid values: max integer value and 5.
    select * from T3 where col1 + col2 < 0
    -- Produces arithmetic overflow error.
    ```

[!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
[!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]

- <span data-ttu-id="429c4-225">SQL esegue l'arrotondamento aritmetico simmetrico, mentre .NET Framework Usa l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="429c4-225">SQL performs symmetric arithmetic rounding while .NET Framework uses banker’s rounding.</span></span> <span data-ttu-id="429c4-226">Per ulteriori dettagli, vedere l'articolo della Knowledge Base 196652.</span><span class="sxs-lookup"><span data-stu-id="429c4-226">See Knowledgebase article 196652 for additional details.</span></span>

- <span data-ttu-id="429c4-227">Per impostazione predefinita, in SQL non viene fatta distinzione tra maiuscole e minuscole nelle operazioni di confronto tra stringhe di caratteri per le impostazioni locali comuni.</span><span class="sxs-lookup"><span data-stu-id="429c4-227">By default, for common locales, character-string comparisons are case-insensitive in SQL.</span></span> <span data-ttu-id="429c4-228">In Visual Basic e in C#, invece, viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="429c4-228">In Visual Basic and in C#, they are case-sensitive.</span></span> <span data-ttu-id="429c4-229">Ad esempio, `s == "Food"` (`s = "Food"` in Visual Basic) e `s == "Food"` può restituire risultati diversi se `s` è `food`.</span><span class="sxs-lookup"><span data-stu-id="429c4-229">For example, `s == "Food"` (`s = "Food"` in Visual Basic) and `s == "Food"` can yield different results if `s` is `food`.</span></span>

    ```sql
    -- Assume default US-English locale (case insensitive).
    create table T4 (
        Col1      nvarchar (256)
    )
    insert into T4 values (‘Food’)
    insert into T4 values (‘FOOD’)
    select * from T4 where Col1 = ‘food’
    -- Both the rows are returned because of case-insensitive matching.
    ```

[!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
[!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]

- <span data-ttu-id="429c4-230">Le funzioni o gli operatori applicati agli argomenti tipo di carattere a lunghezza fissa in SQL hanno una semantica significativamente diversa rispetto alle funzioni o agli operatori analoghi applicati a <xref:System.String?displayProperty=nameWithType> CLR.</span><span class="sxs-lookup"><span data-stu-id="429c4-230">Operators/ functions applied to fixed length character type arguments in SQL have significantly different semantics than the same operators/functions applied to the CLR <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="429c4-231">Anche questo può essere considerato come un'estensione del problema relativo alle controparti mancanti discusso nella sezione sui tipi.</span><span class="sxs-lookup"><span data-stu-id="429c4-231">This could also be viewed as an extension of the missing counterpart problem discussed in the section about types.</span></span>

    ```sql
    create table T4 (
        Col1      nchar(4)
    )
    Insert into T5(Col1) values ('21');
    Insert into T5(Col1) values ('1021');
    Select * from T5 where Col1 like '%1'
    -- Only the second row with Col1 = '1021' is returned.
    -- Not the first row!
    ```

     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]

     <span data-ttu-id="429c4-232">Un problema analogo si verifica con la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="429c4-232">A similar problem occurs with string concatenation.</span></span>

    ```sql
    create table T6 (
        Col1      nchar(4)
        Col2       nchar(4)
    )
    Insert into T6 values ('a', 'b');
    Select Col1+Col2 from T6
    -- Returns concatenation of padded strings "a   b   " and not "ab".
    ```

<span data-ttu-id="429c4-233">In sintesi, per le espressioni CLR potrebbe essere necessaria una conversione complessa, mentre per esporre le funzionalità SQL potrebbero essere necessari funzioni o operatori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="429c4-233">In summary, a convoluted translation might be required for CLR expressions and additional operators/functions may be necessary to expose SQL functionality.</span></span>

### <a name="type-casting"></a><span data-ttu-id="429c4-234">Cast di tipo</span><span class="sxs-lookup"><span data-stu-id="429c4-234">Type Casting</span></span>

<span data-ttu-id="429c4-235">In C# e in SQL gli utenti possono eseguire l'override della semantica delle espressioni predefinita usando cast di tipo espliciti (`Cast` e `Convert`).</span><span class="sxs-lookup"><span data-stu-id="429c4-235">In C# and in SQL, users can override the default semantics of expressions by using explicit type casts (`Cast` and `Convert`).</span></span> <span data-ttu-id="429c4-236">Tuttavia, l'esposizione di questa funzionalità oltre il limite del sistema di tipi costituisce un dilemma.</span><span class="sxs-lookup"><span data-stu-id="429c4-236">However, exposing this capability across the type system boundary poses a dilemma.</span></span> <span data-ttu-id="429c4-237">Un cast SQL che fornisce la semantica desiderata non può essere convertito facilmente nel corrispondente cast C#.</span><span class="sxs-lookup"><span data-stu-id="429c4-237">A SQL cast that provides the desired semantics cannot be easily translated to a corresponding C# cast.</span></span> <span data-ttu-id="429c4-238">D'altra parte un cast C# non può essere convertito direttamente in un cast SQL equivalente a causa di tipi non corrispondenti, controparti mancanti e gerarchie di precedenza dei tipi diverse.</span><span class="sxs-lookup"><span data-stu-id="429c4-238">On the other hand, a C# cast cannot be directly translated into an equivalent SQL cast because of type mismatches, missing counterparts, and different type precedence hierarchies.</span></span> <span data-ttu-id="429c4-239">Esiste un compromesso tra l'esposizione del sistema di tipi non corrispondente e la perdita significativa di potenza di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="429c4-239">There is a trade-off between exposing the type system mismatch and losing significant power of expression.</span></span>

<span data-ttu-id="429c4-240">Negli altri casi il cast dei tipi potrebbe non essere necessario in alcun dominio per la convalida di un'espressione, ma potrebbe essere richiesto per garantire che un mapping non predefinito venga applicato correttamente all'espressione.</span><span class="sxs-lookup"><span data-stu-id="429c4-240">In other cases, type casting might not be needed in either domain for validation of an expression but might be required to make sure that a non-default mapping is correctly applied to the expression.</span></span>

```sql
-- Example from "Non-default Mapping" section extended
create table T5 (
    Col1      nvarchar(10),
    Col2      nvarchar(10)
)
Insert into T5(col1, col2) values (‘3’, ‘2’);
```

[!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
[!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]

```sql
Select *
From T5
Where Col1 + Col2 > 4
-- "Col1 + Col2" expr evaluates to '32'
```

## <a name="performance-issues"></a><span data-ttu-id="429c4-241">Problemi relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="429c4-241">Performance Issues</span></span>

<span data-ttu-id="429c4-242">Tenendo conto di alcuni-CLR di SQL Server le differenze di tipo possono comportare una riduzione delle prestazioni quando si usa tra CLR e SQL Server, sistemi di tipi.</span><span class="sxs-lookup"><span data-stu-id="429c4-242">Accounting for some SQL Server-CLR type differences may result in a decrease in performance when crossing between the CLR and SQL Server type systems.</span></span> <span data-ttu-id="429c4-243">Di seguito vengono indicati alcuni esempi di scenari che influenzano le prestazioni:</span><span class="sxs-lookup"><span data-stu-id="429c4-243">Examples of scenarios impacting performance include the following:</span></span>

- <span data-ttu-id="429c4-244">Ordine di valutazione forzato per gli operatori And/Or logici</span><span class="sxs-lookup"><span data-stu-id="429c4-244">Forced order of evaluation for logical and/or operators</span></span>

- <span data-ttu-id="429c4-245">La generazione di codice SQL per applicare l'ordine di valutazione del predicato limita la funzionalità dell'utilità di ottimizzatore SQL.</span><span class="sxs-lookup"><span data-stu-id="429c4-245">Generating SQL to enforce order of predicate evaluation restricts the SQL optimizer’s ability.</span></span>

- <span data-ttu-id="429c4-246">Le conversioni dei tipi, che vengano introdotte da un compilatore CLR o dall'implementazione di una query relazionale a oggetti, possono limitare l'uso dell'indice.</span><span class="sxs-lookup"><span data-stu-id="429c4-246">Type conversions, whether introduced by a CLR compiler or by an Object-Relational query implementation, may curtail index usage.</span></span>

     <span data-ttu-id="429c4-247">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="429c4-247">For example,</span></span>

    ```sql
    -- Table DDL
    create table T5 (
        Col1      varchar(100)
    )
    ```

     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]

     <span data-ttu-id="429c4-248">Considerare la conversione dell'espressione `(s = SOME_STRING_CONSTANT)`.</span><span class="sxs-lookup"><span data-stu-id="429c4-248">Consider the translation of expression `(s = SOME_STRING_CONSTANT)`.</span></span>

    ```sql
    -- Corresponding part of SQL where clause
    Where …
    Col1 = SOME_STRING_CONSTANT
    -- This expression is of the form <varchar> = <nvarchar>.
    -- Hence SQL introduces a conversion from varchar to nvarchar,
    --   resulting in
    Where …
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT
    -- Cannot use the index for column Col1 for some implementations.
    ```

<span data-ttu-id="429c4-249">Oltre alle differenze semantiche, è importante considerare l'impatto sulle prestazioni nel passaggio tra i sistemi di tipi SQL Server e CLR.</span><span class="sxs-lookup"><span data-stu-id="429c4-249">In addition to semantic differences, it is important to consider impacts to performance when crossing between the SQL Server and CLR type systems.</span></span> <span data-ttu-id="429c4-250">Per i set di dati di grandi dimensioni questi problemi di prestazioni possono determinare l'implementazione o meno di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="429c4-250">For large data sets, such performance issues can determine whether an application is deployable.</span></span>

## <a name="see-also"></a><span data-ttu-id="429c4-251">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="429c4-251">See also</span></span>

- [<span data-ttu-id="429c4-252">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="429c4-252">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
