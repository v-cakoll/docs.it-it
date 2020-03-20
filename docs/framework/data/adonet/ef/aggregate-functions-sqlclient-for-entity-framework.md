---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150649"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="9ef8e-102">Funzioni di aggregazione (SqlClient per Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="9ef8e-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="9ef8e-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="9ef8e-104">che eseguono calcoli su un set di valori di input e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="9ef8e-105">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="9ef8e-106">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="9ef8e-107">Di seguito sono riportate le funzioni di aggregazione SqlClient.The following are the SqlClient aggregate functions.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="9ef8e-108">AVG(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-108">AVG(expression)</span></span>

<span data-ttu-id="9ef8e-109">Restituisce la media dei valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="9ef8e-110">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-110">Null values are ignored.</span></span>

<span data-ttu-id="9ef8e-111">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-111">**Arguments**</span></span>

<span data-ttu-id="9ef8e-112">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , e .</span><span class="sxs-lookup"><span data-stu-id="9ef8e-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="9ef8e-113">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-113">**Return Value**</span></span>

<span data-ttu-id="9ef8e-114">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-114">The type of `expression`.</span></span>

<span data-ttu-id="9ef8e-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="9ef8e-116">CHECKSUM_AGG(raccolta)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="9ef8e-117">Restituisce il checksum dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="9ef8e-118">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-118">Null values are ignored.</span></span>

 <span data-ttu-id="9ef8e-119">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-119">**Arguments**</span></span>

 <span data-ttu-id="9ef8e-120">Una raccolta(`Int32`).</span><span class="sxs-lookup"><span data-stu-id="9ef8e-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="9ef8e-121">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-121">**Return Value**</span></span>

 <span data-ttu-id="9ef8e-122">Valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-122">An `Int32`.</span></span>

 <span data-ttu-id="9ef8e-123">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="9ef8e-124">CONTA.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-124">COUNT(expression)</span></span>

<span data-ttu-id="9ef8e-125">Restituisce il numero di elementi in una raccolta come un valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="9ef8e-126">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-126">**Arguments**</span></span>

<span data-ttu-id="9ef8e-127">Una\<raccolta T>, dove T è uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="9ef8e-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="9ef8e-128">`Guid`(non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="9ef8e-129">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-129">**Return Value**</span></span>

<span data-ttu-id="9ef8e-130">Valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-130">An `Int32`.</span></span>

<span data-ttu-id="9ef8e-131">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="9ef8e-132">COUNT_BIG(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="9ef8e-133">Restituisce il numero di elementi in una raccolta come un valore `bigint`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="9ef8e-134">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-134">**Arguments**</span></span>

 <span data-ttu-id="9ef8e-135">Una Collection(T), dove T è uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="9ef8e-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="9ef8e-136">`Guid`(non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="9ef8e-137">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-137">**Return Value**</span></span>

<span data-ttu-id="9ef8e-138">Valore `Int64`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-138">An `Int64`.</span></span>

<span data-ttu-id="9ef8e-139">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="9ef8e-140">MAX(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-140">MAX(expression)</span></span>

<span data-ttu-id="9ef8e-141">Restituisce il valore massimo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="9ef8e-142">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-142">**Arguments**</span></span>

<span data-ttu-id="9ef8e-143">Una Collection(T), dove T è uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="9ef8e-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="9ef8e-144">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-144">**Return Value**</span></span>

<span data-ttu-id="9ef8e-145">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-145">The type of `expression`.</span></span>

<span data-ttu-id="9ef8e-146">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="9ef8e-147">MIN(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-147">MIN(expression)</span></span>

<span data-ttu-id="9ef8e-148">Restituisce il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="9ef8e-149">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-149">**Arguments**</span></span>

<span data-ttu-id="9ef8e-150">Una Collection(T), dove T è uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="9ef8e-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="9ef8e-151">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-151">**Return Value**</span></span>

<span data-ttu-id="9ef8e-152">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-152">The type of `expression`.</span></span>

<span data-ttu-id="9ef8e-153">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="9ef8e-154">DEV.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-154">STDEV(expression)</span></span>

<span data-ttu-id="9ef8e-155">Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="9ef8e-156">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-156">**Arguments**</span></span>

<span data-ttu-id="9ef8e-157">Una raccolta(`Double`).</span><span class="sxs-lookup"><span data-stu-id="9ef8e-157">A Collection(`Double`).</span></span>

<span data-ttu-id="9ef8e-158">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-158">**Return Value**</span></span>

<span data-ttu-id="9ef8e-159">`Double`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-159">A `Double`.</span></span>

<span data-ttu-id="9ef8e-160">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="9ef8e-161">DEV.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-161">STDEVP(expression)</span></span>

<span data-ttu-id="9ef8e-162">Restituisce la deviazione statistica standard relativa al popolamento di tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="9ef8e-163">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-163">**Arguments**</span></span>

<span data-ttu-id="9ef8e-164">Una raccolta(`Double`).</span><span class="sxs-lookup"><span data-stu-id="9ef8e-164">A Collection(`Double`).</span></span>

<span data-ttu-id="9ef8e-165">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-165">**Return Value**</span></span>

<span data-ttu-id="9ef8e-166">`Double`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-166">A `Double`.</span></span>

<span data-ttu-id="9ef8e-167">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="9ef8e-168">SOMMA(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-168">SUM(expression)</span></span>

<span data-ttu-id="9ef8e-169">Restituisce la somma di tutti i valori della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="9ef8e-170">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-170">**Arguments**</span></span>

<span data-ttu-id="9ef8e-171">Oggetto Collection(T) dove T è uno `Int32` `Int64`dei `Double` `Decimal`seguenti tipi: , , , , .</span><span class="sxs-lookup"><span data-stu-id="9ef8e-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="9ef8e-172">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-172">**Return Value**</span></span>

<span data-ttu-id="9ef8e-173">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-173">The type of `expression`.</span></span>

<span data-ttu-id="9ef8e-174">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="9ef8e-175">VAR(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-175">VAR(expression)</span></span>

<span data-ttu-id="9ef8e-176">Restituisce lo scostamento statistico di tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="9ef8e-177">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-177">**Arguments**</span></span>

<span data-ttu-id="9ef8e-178">Una raccolta(`Double`).</span><span class="sxs-lookup"><span data-stu-id="9ef8e-178">A Collection(`Double`).</span></span>

<span data-ttu-id="9ef8e-179">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-179">**Return Value**</span></span>

<span data-ttu-id="9ef8e-180">`Double`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-180">A `Double`.</span></span>

<span data-ttu-id="9ef8e-181">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="9ef8e-182">VARP(espressione)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-182">VARP(expression)</span></span>

<span data-ttu-id="9ef8e-183">Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="9ef8e-184">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-184">**Arguments**</span></span>

<span data-ttu-id="9ef8e-185">Una raccolta(`Double`).</span><span class="sxs-lookup"><span data-stu-id="9ef8e-185">A Collection(`Double`).</span></span>

<span data-ttu-id="9ef8e-186">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-186">**Return Value**</span></span>

<span data-ttu-id="9ef8e-187">`Double`.</span><span class="sxs-lookup"><span data-stu-id="9ef8e-187">A `Double`.</span></span>

<span data-ttu-id="9ef8e-188">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="9ef8e-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="9ef8e-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef8e-189">See also</span></span>

- [<span data-ttu-id="9ef8e-190">Funzioni di aggregazione (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9ef8e-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="9ef8e-191">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9ef8e-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="9ef8e-192">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="9ef8e-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
