---
title: Funzioni di aggregazione canoniche
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e4772176130fc72a22645462921c90dd5b7967b2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506638"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="01aa5-102">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="01aa5-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="01aa5-103">Le aggregazioni sono espressioni che riducono una serie di valori di input, ad esempio, in un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="01aa5-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="01aa5-104">In genere, vengono usate insieme alla clausola GROUP BY dell'espressione SELECT. Il relativo uso è tuttavia soggetto ad alcuni vincoli.</span><span class="sxs-lookup"><span data-stu-id="01aa5-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggegate-entity-sql-canonical-functions"></a><span data-ttu-id="01aa5-105">Funzioni canoniche Aggegate Entity SQL</span><span class="sxs-lookup"><span data-stu-id="01aa5-105">Aggegate Entity SQL canonical functions</span></span>

<span data-ttu-id="01aa5-106">Di seguito sono le funzioni di aggregazione canoniche Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="01aa5-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="01aa5-107">Avg(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-107">Avg(expression)</span></span>

<span data-ttu-id="01aa5-108">Restituisce la media dei valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="01aa5-109">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-109">**Arguments**</span></span>

<span data-ttu-id="01aa5-110">Un' `Int32`, `Int64`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="01aa5-111">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-111">**Return Value**</span></span>

<span data-ttu-id="01aa5-112">Il tipo della `expression`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-113">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)] 
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="01aa5-114">BigCount(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-114">BigCount(expression)</span></span>

<span data-ttu-id="01aa5-115">Restituisce la dimensione dell'aggregazione, inclusi i valori Null e duplicati.</span><span class="sxs-lookup"><span data-stu-id="01aa5-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="01aa5-116">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-116">**Arguments**</span></span>

<span data-ttu-id="01aa5-117">Qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="01aa5-117">Any type.</span></span>

<span data-ttu-id="01aa5-118">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-118">**Return Value**</span></span>

<span data-ttu-id="01aa5-119">Oggetto `Int64`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-119">An `Int64`.</span></span>

<span data-ttu-id="01aa5-120">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)] 
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="01aa5-121">Count(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-121">Count(expression)</span></span> 

<span data-ttu-id="01aa5-122">Restituisce la dimensione dell'aggregazione, inclusi i valori Null e duplicati.</span><span class="sxs-lookup"><span data-stu-id="01aa5-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="01aa5-123">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-123">**Arguments**</span></span>

<span data-ttu-id="01aa5-124">Qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="01aa5-124">Any type.</span></span>

<span data-ttu-id="01aa5-125">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-125">**Return Value**</span></span>

<span data-ttu-id="01aa5-126">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-126">An `Int32`.</span></span>

<span data-ttu-id="01aa5-127">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="01aa5-128">Max(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-128">Max(expression)</span></span>

<span data-ttu-id="01aa5-129">Restituisce il numero massimo di valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="01aa5-130">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-130">**Arguments**</span></span>

<span data-ttu-id="01aa5-131">Valore `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="01aa5-132">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-132">**Return Value**</span></span>

<span data-ttu-id="01aa5-133">Il tipo della `expression`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-134">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="01aa5-135">Min(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-135">Min(expression)</span></span>

<span data-ttu-id="01aa5-136">Restituisce il numero minimo di valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="01aa5-137">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-137">**Arguments**</span></span>

<span data-ttu-id="01aa5-138">Valore `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="01aa5-139">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-139">**Return Value**</span></span>

<span data-ttu-id="01aa5-140">Il tipo della `expression`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-141">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="01aa5-142">StDev(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-142">StDev(expression)</span></span>

<span data-ttu-id="01aa5-143">Restituisce la deviazione standard dei valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="01aa5-144">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-144">**Arguments**</span></span>

<span data-ttu-id="01aa5-145">Valore `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="01aa5-146">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-146">**Return Value**</span></span>

<span data-ttu-id="01aa5-147">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-147">A `Double`.</span></span> <span data-ttu-id="01aa5-148">`Null`, se tutti i valori di input sono valori `null`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-149">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="01aa5-150">StDevP(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-150">StDevP(expression)</span></span>

<span data-ttu-id="01aa5-151">Restituisce la deviazione standard della popolazione di tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="01aa5-152">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-152">**Arguments**</span></span>

<span data-ttu-id="01aa5-153">Valore `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="01aa5-154">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-154">**Return Value**</span></span>

<span data-ttu-id="01aa5-155">Oggetto `Double`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-156">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="01aa5-157">Sum(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-157">Sum(expression)</span></span>

<span data-ttu-id="01aa5-158">Restituisce la somma dei valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="01aa5-159">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-159">**Arguments**</span></span>

<span data-ttu-id="01aa5-160">Valore `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="01aa5-161">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-161">**Return Value**</span></span>

<span data-ttu-id="01aa5-162">Oggetto `Double`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-163">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="01aa5-164">Var(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-164">Var(expression)</span></span>

<span data-ttu-id="01aa5-165">Restituisce la varianza di tutti i valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="01aa5-166">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-166">**Arguments**</span></span>

<span data-ttu-id="01aa5-167">Valore `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="01aa5-168">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-168">**Return Value**</span></span>

<span data-ttu-id="01aa5-169">Oggetto `Double`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-170">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="01aa5-171">VarP(expression)</span><span class="sxs-lookup"><span data-stu-id="01aa5-171">VarP(expression)</span></span>

<span data-ttu-id="01aa5-172">Restituisce la varianza della popolazione di tutti i valori non Null.</span><span class="sxs-lookup"><span data-stu-id="01aa5-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="01aa5-173">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="01aa5-173">**Arguments**</span></span>

<span data-ttu-id="01aa5-174">Valore `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="01aa5-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="01aa5-175">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="01aa5-175">**Return Value**</span></span>

<span data-ttu-id="01aa5-176">Oggetto `Double`, oppure `null` se tutti i valori di input sono `null` valori.</span><span class="sxs-lookup"><span data-stu-id="01aa5-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="01aa5-177">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="01aa5-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] 

<span data-ttu-id="01aa5-178">Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="01aa5-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="01aa5-179">Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="01aa5-179">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="01aa5-180">Aggregazioni basate su raccolta</span><span class="sxs-lookup"><span data-stu-id="01aa5-180">Collection-based aggregates</span></span>

<span data-ttu-id="01aa5-181">Le aggregazioni basate su raccolte (funzioni della Collection) operano sulle raccolte e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="01aa5-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="01aa5-182">Ad esempio se ORDERS è una raccolta di tutti gli ordini, è possibile calcolare la prima data di spedizione con l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="01aa5-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="01aa5-183">Le espressioni all'interno di aggregazioni basate su raccolte vengono valutate nell'ambito di risoluzione dei nomi di ambiente corrente.</span><span class="sxs-lookup"><span data-stu-id="01aa5-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="01aa5-184">Aggregazioni basate su gruppo</span><span class="sxs-lookup"><span data-stu-id="01aa5-184">Group-based aggregates</span></span>

<span data-ttu-id="01aa5-185">Le aggregazioni basate su gruppo vengono calcolate su un gruppo definito dalla clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="01aa5-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="01aa5-186">Per ogni gruppo nel risultato viene calcolata un'aggregazione distinta usando gli elementi in ciascun gruppo come input nel calcolo dell'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="01aa5-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="01aa5-187">Quando in un'espressione selezionata viene usata una clausola GROUP BY, nella proiezione o nella clausola ORDER BY possono essere presenti solo nomi di espressioni di raggruppamento, aggregazioni o espressioni costanti.</span><span class="sxs-lookup"><span data-stu-id="01aa5-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="01aa5-188">Nell'esempio seguente viene calcolata la quantità media ordinata per ciascun prodotto:</span><span class="sxs-lookup"><span data-stu-id="01aa5-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

<span data-ttu-id="01aa5-189">È possibile disporre di una funzione di aggregazione basate su gruppo senza una clausola group by esplicita nell'espressione SELECT.</span><span class="sxs-lookup"><span data-stu-id="01aa5-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="01aa5-190">In questo caso, tutti gli elementi vengono trattati come un unico gruppo.</span><span class="sxs-lookup"><span data-stu-id="01aa5-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="01aa5-191">È equivalente della specifica di un raggruppamento basato su una costante.</span><span class="sxs-lookup"><span data-stu-id="01aa5-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="01aa5-192">Si consideri, ad esempio, l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="01aa5-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="01aa5-193">L'espressione equivale alla seguente:</span><span class="sxs-lookup"><span data-stu-id="01aa5-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="01aa5-194">Le espressioni all'interno dell'aggregazione basata su gruppo vengono valutate nell'ambito della risoluzione dei nomi visibile per l'espressione della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="01aa5-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="01aa5-195">Come in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], aggregazioni basate su gruppo possono inoltre specificare un ALL o modificatore DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="01aa5-195">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="01aa5-196">Se è specificato il modificatore DISTINCT, eventuali duplicati vengono eliminati dalla raccolta di input di aggregazione prima del calcolo dell'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="01aa5-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="01aa5-197">Se è specificato il modificatore ALL o se non è specificato alcun modificatore, non viene eseguita l'eliminazione dei duplicati.</span><span class="sxs-lookup"><span data-stu-id="01aa5-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="01aa5-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01aa5-198">See also</span></span>

[<span data-ttu-id="01aa5-199">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="01aa5-199">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
