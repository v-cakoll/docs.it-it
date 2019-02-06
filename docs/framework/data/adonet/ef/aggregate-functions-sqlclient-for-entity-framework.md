---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758700"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="008d1-102">Funzioni di aggregazione (SqlClient per Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="008d1-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="008d1-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="008d1-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="008d1-104">che eseguono calcoli su un set di valori di input e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="008d1-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="008d1-105">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="008d1-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="008d1-106">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="008d1-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="008d1-107">Di seguito sono le funzioni di aggregazione di SqlClient.</span><span class="sxs-lookup"><span data-stu-id="008d1-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="008d1-108">AVG(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-108">AVG(expression)</span></span>

<span data-ttu-id="008d1-109">Restituisce la media dei valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="008d1-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="008d1-110">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="008d1-110">Null values are ignored.</span></span>

<span data-ttu-id="008d1-111">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-111">**Arguments**</span></span>

<span data-ttu-id="008d1-112">Un' `Int32`, `Int64`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="008d1-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="008d1-113">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-113">**Return Value**</span></span>

<span data-ttu-id="008d1-114">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="008d1-114">The type of `expression`.</span></span>

<span data-ttu-id="008d1-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="008d1-116">CHECKSUM_AGG(Collection)</span><span class="sxs-lookup"><span data-stu-id="008d1-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="008d1-117">Restituisce il checksum dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="008d1-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="008d1-118">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="008d1-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="008d1-119">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-119">**Arguments**</span></span>
 
 <span data-ttu-id="008d1-120">A Collection(`Int32`).</span><span class="sxs-lookup"><span data-stu-id="008d1-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="008d1-121">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-121">**Return Value**</span></span>
 
 <span data-ttu-id="008d1-122">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="008d1-122">An `Int32`.</span></span>
 
 <span data-ttu-id="008d1-123">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="008d1-124">Count(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-124">COUNT(expression)</span></span>

<span data-ttu-id="008d1-125">Restituisce il numero di elementi in una raccolta come un valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="008d1-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="008d1-126">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-126">**Arguments**</span></span>

<span data-ttu-id="008d1-127">Una raccolta\<T >, dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="008d1-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="008d1-128">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="008d1-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="008d1-129">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-129">**Return Value**</span></span>

<span data-ttu-id="008d1-130">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="008d1-130">An `Int32`.</span></span>

<span data-ttu-id="008d1-131">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="008d1-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="008d1-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="008d1-133">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="008d1-134">Restituisce il numero di elementi in una raccolta come un valore `bigint`.</span><span class="sxs-lookup"><span data-stu-id="008d1-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="008d1-135">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-135">**Arguments**</span></span>
 
 <span data-ttu-id="008d1-136">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="008d1-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="008d1-137">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="008d1-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="008d1-138">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-138">**Return Value**</span></span>

<span data-ttu-id="008d1-139">Oggetto `Int64`.</span><span class="sxs-lookup"><span data-stu-id="008d1-139">An `Int64`.</span></span>

<span data-ttu-id="008d1-140">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="008d1-141">MAX(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-141">MAX(expression)</span></span>

<span data-ttu-id="008d1-142">Restituisce il valore massimo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="008d1-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="008d1-143">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-143">**Arguments**</span></span>

<span data-ttu-id="008d1-144">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="008d1-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="008d1-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-145">**Return Value**</span></span>

<span data-ttu-id="008d1-146">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="008d1-146">The type of `expression`.</span></span>

<span data-ttu-id="008d1-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="008d1-148">Min(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-148">MIN(expression)</span></span>

<span data-ttu-id="008d1-149">Restituisce il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="008d1-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="008d1-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-150">**Arguments**</span></span>

<span data-ttu-id="008d1-151">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="008d1-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="008d1-152">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-152">**Return Value**</span></span>

<span data-ttu-id="008d1-153">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="008d1-153">The type of `expression`.</span></span>

<span data-ttu-id="008d1-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="008d1-155">STDEV(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-155">STDEV(expression)</span></span>

<span data-ttu-id="008d1-156">Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="008d1-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="008d1-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-157">**Arguments**</span></span>

<span data-ttu-id="008d1-158">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="008d1-158">A Collection(`Double`).</span></span>

<span data-ttu-id="008d1-159">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-159">**Return Value**</span></span>

<span data-ttu-id="008d1-160">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="008d1-160">A `Double`.</span></span>

<span data-ttu-id="008d1-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="008d1-162">StDevP(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-162">STDEVP(expression)</span></span>

<span data-ttu-id="008d1-163">Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="008d1-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="008d1-164">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-164">**Arguments**</span></span>

<span data-ttu-id="008d1-165">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="008d1-165">A Collection(`Double`).</span></span>

<span data-ttu-id="008d1-166">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-166">**Return Value**</span></span>

<span data-ttu-id="008d1-167">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="008d1-167">A `Double`.</span></span>

<span data-ttu-id="008d1-168">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="008d1-169">SUM(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-169">SUM(expression)</span></span>

<span data-ttu-id="008d1-170">Restituisce la somma di tutti i valori della raccolta.</span><span class="sxs-lookup"><span data-stu-id="008d1-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="008d1-171">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-171">**Arguments**</span></span>

<span data-ttu-id="008d1-172">Un Collection(T) dove T è uno dei tipi seguenti: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="008d1-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="008d1-173">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-173">**Return Value**</span></span>

<span data-ttu-id="008d1-174">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="008d1-174">The type of `expression`.</span></span>

<span data-ttu-id="008d1-175">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="008d1-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-176">VAR(expression)</span></span>

<span data-ttu-id="008d1-177">Restituisce la varianza statistica di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="008d1-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="008d1-178">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-178">**Arguments**</span></span>

<span data-ttu-id="008d1-179">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="008d1-179">A Collection(`Double`).</span></span>

<span data-ttu-id="008d1-180">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-180">**Return Value**</span></span>

<span data-ttu-id="008d1-181">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="008d1-181">A `Double`.</span></span>

<span data-ttu-id="008d1-182">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="008d1-183">VarP(Expression)</span><span class="sxs-lookup"><span data-stu-id="008d1-183">VARP(expression)</span></span>

<span data-ttu-id="008d1-184">Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="008d1-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="008d1-185">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="008d1-185">**Arguments**</span></span>

<span data-ttu-id="008d1-186">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="008d1-186">A Collection(`Double`).</span></span>

<span data-ttu-id="008d1-187">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="008d1-187">**Return Value**</span></span>

<span data-ttu-id="008d1-188">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="008d1-188">A `Double`.</span></span>

<span data-ttu-id="008d1-189">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="008d1-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="008d1-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="008d1-190">See also</span></span>

<span data-ttu-id="008d1-191">Per altre informazioni sulle funzioni di aggregazione supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="008d1-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="008d1-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="008d1-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="008d1-193">**SQL Server 2008 e versioni successive:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="008d1-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="008d1-194">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="008d1-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="008d1-195">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="008d1-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
