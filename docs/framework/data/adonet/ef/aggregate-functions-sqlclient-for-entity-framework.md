---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 8ed9a58da9914724fe312876d6594cb526f2e0e9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856517"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="a83f8-102">Funzioni di aggregazione (SqlClient per Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="a83f8-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="a83f8-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="a83f8-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="a83f8-104">che eseguono calcoli su un set di valori di input e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="a83f8-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="a83f8-105">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="a83f8-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="a83f8-106">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="a83f8-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="a83f8-107">Di seguito sono le funzioni di aggregazione di SqlClient.</span><span class="sxs-lookup"><span data-stu-id="a83f8-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="a83f8-108">AVG(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-108">AVG(expression)</span></span>

<span data-ttu-id="a83f8-109">Restituisce la media dei valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="a83f8-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="a83f8-110">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a83f8-110">Null values are ignored.</span></span>

<span data-ttu-id="a83f8-111">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-111">**Arguments**</span></span>

<span data-ttu-id="a83f8-112">Un' `Int32`, `Int64`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="a83f8-113">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-113">**Return Value**</span></span>

<span data-ttu-id="a83f8-114">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-114">The type of `expression`.</span></span>

<span data-ttu-id="a83f8-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="a83f8-116">CHECKSUM_AGG(Collection)</span><span class="sxs-lookup"><span data-stu-id="a83f8-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="a83f8-117">Restituisce il checksum dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="a83f8-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="a83f8-118">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a83f8-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="a83f8-119">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-119">**Arguments**</span></span>
 
 <span data-ttu-id="a83f8-120">Una raccolta (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="a83f8-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="a83f8-121">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-121">**Return Value**</span></span>
 
 <span data-ttu-id="a83f8-122">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-122">An `Int32`.</span></span>
 
 <span data-ttu-id="a83f8-123">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="a83f8-124">Count(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-124">COUNT(expression)</span></span>

<span data-ttu-id="a83f8-125">Restituisce il numero di elementi in una raccolta come un valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="a83f8-126">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-126">**Arguments**</span></span>

<span data-ttu-id="a83f8-127">Una raccolta\<T >, dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a83f8-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a83f8-128">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="a83f8-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a83f8-129">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-129">**Return Value**</span></span>

<span data-ttu-id="a83f8-130">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-130">An `Int32`.</span></span>

<span data-ttu-id="a83f8-131">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="a83f8-132">[! codice sql[DP EntityServices concetti & SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="a83f8-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="a83f8-133">COUNT_BIG(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="a83f8-134">Restituisce il numero di elementi in una raccolta come un valore `bigint`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="a83f8-135">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-135">**Arguments**</span></span>
 
 <span data-ttu-id="a83f8-136">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a83f8-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a83f8-137">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="a83f8-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a83f8-138">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-138">**Return Value**</span></span>

<span data-ttu-id="a83f8-139">Oggetto `Int64`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-139">An `Int64`.</span></span>

<span data-ttu-id="a83f8-140">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="a83f8-141">MAX(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-141">MAX(expression)</span></span>

<span data-ttu-id="a83f8-142">Restituisce il valore massimo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="a83f8-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="a83f8-143">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-143">**Arguments**</span></span>

<span data-ttu-id="a83f8-144">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a83f8-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a83f8-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-145">**Return Value**</span></span>

<span data-ttu-id="a83f8-146">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-146">The type of `expression`.</span></span>

<span data-ttu-id="a83f8-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="a83f8-148">Min(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-148">MIN(expression)</span></span>

<span data-ttu-id="a83f8-149">Restituisce il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="a83f8-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="a83f8-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-150">**Arguments**</span></span>

<span data-ttu-id="a83f8-151">Collection(T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a83f8-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a83f8-152">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-152">**Return Value**</span></span>

<span data-ttu-id="a83f8-153">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-153">The type of `expression`.</span></span>

<span data-ttu-id="a83f8-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="a83f8-155">STDEV(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-155">STDEV(expression)</span></span>

<span data-ttu-id="a83f8-156">Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a83f8-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="a83f8-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-157">**Arguments**</span></span>

<span data-ttu-id="a83f8-158">Una raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="a83f8-158">A Collection(`Double`).</span></span>

<span data-ttu-id="a83f8-159">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-159">**Return Value**</span></span>

<span data-ttu-id="a83f8-160">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-160">A `Double`.</span></span>

<span data-ttu-id="a83f8-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="a83f8-162">StDevP(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-162">STDEVP(expression)</span></span>

<span data-ttu-id="a83f8-163">Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a83f8-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a83f8-164">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-164">**Arguments**</span></span>

<span data-ttu-id="a83f8-165">Una raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="a83f8-165">A Collection(`Double`).</span></span>

<span data-ttu-id="a83f8-166">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-166">**Return Value**</span></span>

<span data-ttu-id="a83f8-167">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-167">A `Double`.</span></span>

<span data-ttu-id="a83f8-168">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="a83f8-169">SUM(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-169">SUM(expression)</span></span>

<span data-ttu-id="a83f8-170">Restituisce la somma di tutti i valori della raccolta.</span><span class="sxs-lookup"><span data-stu-id="a83f8-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="a83f8-171">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-171">**Arguments**</span></span>

<span data-ttu-id="a83f8-172">Un Collection(T) dove T è uno dei tipi seguenti: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="a83f8-173">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-173">**Return Value**</span></span>

<span data-ttu-id="a83f8-174">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-174">The type of `expression`.</span></span>

<span data-ttu-id="a83f8-175">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="a83f8-176">VAR(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-176">VAR(expression)</span></span>

<span data-ttu-id="a83f8-177">Restituisce la varianza statistica di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a83f8-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="a83f8-178">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-178">**Arguments**</span></span>

<span data-ttu-id="a83f8-179">Una raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="a83f8-179">A Collection(`Double`).</span></span>

<span data-ttu-id="a83f8-180">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-180">**Return Value**</span></span>

<span data-ttu-id="a83f8-181">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-181">A `Double`.</span></span>

<span data-ttu-id="a83f8-182">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="a83f8-183">VarP(Expression)</span><span class="sxs-lookup"><span data-stu-id="a83f8-183">VARP(expression)</span></span>

<span data-ttu-id="a83f8-184">Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a83f8-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a83f8-185">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="a83f8-185">**Arguments**</span></span>

<span data-ttu-id="a83f8-186">Una raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="a83f8-186">A Collection(`Double`).</span></span>

<span data-ttu-id="a83f8-187">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="a83f8-187">**Return Value**</span></span>

<span data-ttu-id="a83f8-188">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="a83f8-188">A `Double`.</span></span>

<span data-ttu-id="a83f8-189">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="a83f8-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="a83f8-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a83f8-190">See also</span></span>

<span data-ttu-id="a83f8-191">Per altre informazioni sulle funzioni di aggregazione supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="a83f8-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="a83f8-192">**SQL Server 2005**: [funzioni di aggregazione (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="a83f8-192">**SQL Server 2005**: [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>  
<span data-ttu-id="a83f8-193">**SQL Server 2008 e versioni successive**: [funzioni di aggregazione (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="a83f8-193">**SQL Server 2008 and later**:  [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>  
[<span data-ttu-id="a83f8-194">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a83f8-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
[<span data-ttu-id="a83f8-195">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="a83f8-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
