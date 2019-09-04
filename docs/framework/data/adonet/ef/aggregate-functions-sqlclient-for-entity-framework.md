---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251699"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="08751-102">Funzioni di aggregazione (SqlClient per Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="08751-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="08751-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="08751-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="08751-104">che eseguono calcoli su un set di valori di input e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="08751-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="08751-105">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="08751-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="08751-106">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="08751-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="08751-107">Di seguito sono riportate le funzioni di aggregazione SqlClient.</span><span class="sxs-lookup"><span data-stu-id="08751-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="08751-108">AVG (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-108">AVG(expression)</span></span>

<span data-ttu-id="08751-109">Restituisce la media dei valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="08751-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="08751-110">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="08751-110">Null values are ignored.</span></span>

<span data-ttu-id="08751-111">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-111">**Arguments**</span></span>

<span data-ttu-id="08751-112">`Int32` ,`Int64`, E .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="08751-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="08751-113">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-113">**Return Value**</span></span>

<span data-ttu-id="08751-114">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="08751-114">The type of `expression`.</span></span>

<span data-ttu-id="08751-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="08751-116">CHECKSUM_AGG (raccolta)</span><span class="sxs-lookup"><span data-stu-id="08751-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="08751-117">Restituisce il checksum dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="08751-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="08751-118">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="08751-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="08751-119">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-119">**Arguments**</span></span>
 
 <span data-ttu-id="08751-120">Raccolta (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="08751-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="08751-121">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-121">**Return Value**</span></span>
 
 <span data-ttu-id="08751-122">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="08751-122">An `Int32`.</span></span>
 
 <span data-ttu-id="08751-123">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="08751-124">CONTEGGIO (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-124">COUNT(expression)</span></span>

<span data-ttu-id="08751-125">Restituisce il numero di elementi in una raccolta come un valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="08751-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="08751-126">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-126">**Arguments**</span></span>

<span data-ttu-id="08751-127">Una raccolta\<t >, dove t è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08751-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="08751-128">`Guid`(non restituito nel SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="08751-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="08751-129">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-129">**Return Value**</span></span>

<span data-ttu-id="08751-130">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="08751-130">An `Int32`.</span></span>

<span data-ttu-id="08751-131">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="08751-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="08751-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="count_bigexpression"></a><span data-ttu-id="08751-133">COUNT_BIG (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="08751-134">Restituisce il numero di elementi in una raccolta come un valore `bigint`.</span><span class="sxs-lookup"><span data-stu-id="08751-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="08751-135">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-135">**Arguments**</span></span>
 
 <span data-ttu-id="08751-136">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08751-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="08751-137">`Guid`(non restituito nel SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="08751-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="08751-138">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-138">**Return Value**</span></span>

<span data-ttu-id="08751-139">Oggetto `Int64`.</span><span class="sxs-lookup"><span data-stu-id="08751-139">An `Int64`.</span></span>

<span data-ttu-id="08751-140">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="08751-141">MAX (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-141">MAX(expression)</span></span>

<span data-ttu-id="08751-142">Restituisce il valore massimo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="08751-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="08751-143">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-143">**Arguments**</span></span>

<span data-ttu-id="08751-144">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08751-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="08751-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-145">**Return Value**</span></span>

<span data-ttu-id="08751-146">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="08751-146">The type of `expression`.</span></span>

<span data-ttu-id="08751-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="08751-148">MIN (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-148">MIN(expression)</span></span>

<span data-ttu-id="08751-149">Restituisce il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="08751-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="08751-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-150">**Arguments**</span></span>

<span data-ttu-id="08751-151">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="08751-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="08751-152">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-152">**Return Value**</span></span>

<span data-ttu-id="08751-153">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="08751-153">The type of `expression`.</span></span>

<span data-ttu-id="08751-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="08751-155">STDEV (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-155">STDEV(expression)</span></span>

<span data-ttu-id="08751-156">Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="08751-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="08751-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-157">**Arguments**</span></span>

<span data-ttu-id="08751-158">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="08751-158">A Collection(`Double`).</span></span>

<span data-ttu-id="08751-159">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-159">**Return Value**</span></span>

<span data-ttu-id="08751-160">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="08751-160">A `Double`.</span></span>

<span data-ttu-id="08751-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="08751-162">STDEVP (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-162">STDEVP(expression)</span></span>

<span data-ttu-id="08751-163">Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="08751-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="08751-164">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-164">**Arguments**</span></span>

<span data-ttu-id="08751-165">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="08751-165">A Collection(`Double`).</span></span>

<span data-ttu-id="08751-166">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-166">**Return Value**</span></span>

<span data-ttu-id="08751-167">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="08751-167">A `Double`.</span></span>

<span data-ttu-id="08751-168">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="08751-169">SUM (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-169">SUM(expression)</span></span>

<span data-ttu-id="08751-170">Restituisce la somma di tutti i valori della raccolta.</span><span class="sxs-lookup"><span data-stu-id="08751-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="08751-171">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-171">**Arguments**</span></span>

<span data-ttu-id="08751-172">`Int32`Raccolta (t) `Int64` `Decimal`, dove t è uno dei tipi seguenti:,, ,.`Double`</span><span class="sxs-lookup"><span data-stu-id="08751-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="08751-173">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-173">**Return Value**</span></span>

<span data-ttu-id="08751-174">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="08751-174">The type of `expression`.</span></span>

<span data-ttu-id="08751-175">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="08751-176">VAR (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-176">VAR(expression)</span></span>

<span data-ttu-id="08751-177">Restituisce la varianza statistica di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="08751-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="08751-178">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-178">**Arguments**</span></span>

<span data-ttu-id="08751-179">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="08751-179">A Collection(`Double`).</span></span>

<span data-ttu-id="08751-180">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-180">**Return Value**</span></span>

<span data-ttu-id="08751-181">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="08751-181">A `Double`.</span></span>

<span data-ttu-id="08751-182">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="08751-183">VARP (espressione)</span><span class="sxs-lookup"><span data-stu-id="08751-183">VARP(expression)</span></span>

<span data-ttu-id="08751-184">Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="08751-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="08751-185">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="08751-185">**Arguments**</span></span>

<span data-ttu-id="08751-186">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="08751-186">A Collection(`Double`).</span></span>

<span data-ttu-id="08751-187">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="08751-187">**Return Value**</span></span>

<span data-ttu-id="08751-188">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="08751-188">A `Double`.</span></span>

<span data-ttu-id="08751-189">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="08751-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="08751-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08751-190">See also</span></span>

<span data-ttu-id="08751-191">Per altre informazioni sulle funzioni di aggregazione supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="08751-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="08751-192">**SQL Server 2005:** [Funzioni di aggregazione (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="08751-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="08751-193">**SQL Server 2008 e versioni successive:** [Funzioni di aggregazione (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="08751-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="08751-194">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="08751-194">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="08751-195">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="08751-195">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
