---
title: Funzioni di aggregazione (SqlClient per Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700050"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="cbd35-102">Funzioni di aggregazione (SqlClient per Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="cbd35-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="cbd35-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="cbd35-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="cbd35-104">che eseguono calcoli su un set di valori di input e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="cbd35-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="cbd35-105">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="cbd35-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="cbd35-106">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="cbd35-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="cbd35-107">Di seguito sono riportate le funzioni di aggregazione SqlClient.</span><span class="sxs-lookup"><span data-stu-id="cbd35-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="cbd35-108">AVG (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-108">AVG(expression)</span></span>

<span data-ttu-id="cbd35-109">Restituisce la media dei valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbd35-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="cbd35-110">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="cbd35-110">Null values are ignored.</span></span>

<span data-ttu-id="cbd35-111">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-111">**Arguments**</span></span>

<span data-ttu-id="cbd35-112">`Int32`, `Int64`, `Double`e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="cbd35-113">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-113">**Return Value**</span></span>

<span data-ttu-id="cbd35-114">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-114">The type of `expression`.</span></span>

<span data-ttu-id="cbd35-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="cbd35-116">CHECKSUM_AGG (raccolta)</span><span class="sxs-lookup"><span data-stu-id="cbd35-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="cbd35-117">Restituisce il checksum dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbd35-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="cbd35-118">I valori Null vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="cbd35-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="cbd35-119">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-119">**Arguments**</span></span>
 
 <span data-ttu-id="cbd35-120">Raccolta (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="cbd35-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="cbd35-121">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-121">**Return Value**</span></span>
 
 <span data-ttu-id="cbd35-122">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-122">An `Int32`.</span></span>
 
 <span data-ttu-id="cbd35-123">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-123">**Example**</span></span>
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="cbd35-124">CONTEGGIO (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-124">COUNT(expression)</span></span>

<span data-ttu-id="cbd35-125">Restituisce il numero di elementi in una raccolta come un valore `Int32`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="cbd35-126">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-126">**Arguments**</span></span>

<span data-ttu-id="cbd35-127">Raccolta\<T >, dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbd35-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="cbd35-128">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="cbd35-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="cbd35-129">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-129">**Return Value**</span></span>

<span data-ttu-id="cbd35-130">Oggetto `Int32`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-130">An `Int32`.</span></span>

<span data-ttu-id="cbd35-131">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a><span data-ttu-id="cbd35-132">COUNT_BIG (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-132">COUNT_BIG(expression)</span></span>
 
<span data-ttu-id="cbd35-133">Restituisce il numero di elementi in una raccolta come un valore `bigint`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-133">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="cbd35-134">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-134">**Arguments**</span></span>
 
 <span data-ttu-id="cbd35-135">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbd35-135">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="cbd35-136">`Guid` (non restituito in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="cbd35-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="cbd35-137">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-137">**Return Value**</span></span>

<span data-ttu-id="cbd35-138">Oggetto `Int64`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-138">An `Int64`.</span></span>

<span data-ttu-id="cbd35-139">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="cbd35-140">MAX (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-140">MAX(expression)</span></span>

<span data-ttu-id="cbd35-141">Restituisce il valore massimo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbd35-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="cbd35-142">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-142">**Arguments**</span></span>

<span data-ttu-id="cbd35-143">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbd35-143">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="cbd35-144">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-144">**Return Value**</span></span>

<span data-ttu-id="cbd35-145">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-145">The type of `expression`.</span></span>

<span data-ttu-id="cbd35-146">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="cbd35-147">MIN (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-147">MIN(expression)</span></span>

<span data-ttu-id="cbd35-148">Restituisce il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbd35-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="cbd35-149">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-149">**Arguments**</span></span>

<span data-ttu-id="cbd35-150">Raccolta (T), dove T è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbd35-150">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="cbd35-151">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-151">**Return Value**</span></span>

<span data-ttu-id="cbd35-152">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-152">The type of `expression`.</span></span>

<span data-ttu-id="cbd35-153">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="cbd35-154">STDEV (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-154">STDEV(expression)</span></span>

<span data-ttu-id="cbd35-155">Restituisce la deviazione statistica standard di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="cbd35-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="cbd35-156">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-156">**Arguments**</span></span>

<span data-ttu-id="cbd35-157">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="cbd35-157">A Collection(`Double`).</span></span>

<span data-ttu-id="cbd35-158">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-158">**Return Value**</span></span>

<span data-ttu-id="cbd35-159">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-159">A `Double`.</span></span>

<span data-ttu-id="cbd35-160">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="cbd35-161">STDEVP (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-161">STDEVP(expression)</span></span>

<span data-ttu-id="cbd35-162">Restituisce la deviazione statistica standard relativa alla popolazione per tutti i valori dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="cbd35-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="cbd35-163">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-163">**Arguments**</span></span>

<span data-ttu-id="cbd35-164">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="cbd35-164">A Collection(`Double`).</span></span>

<span data-ttu-id="cbd35-165">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-165">**Return Value**</span></span>

<span data-ttu-id="cbd35-166">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-166">A `Double`.</span></span>

<span data-ttu-id="cbd35-167">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="cbd35-168">SUM (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-168">SUM(expression)</span></span>

<span data-ttu-id="cbd35-169">Restituisce la somma di tutti i valori della raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbd35-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="cbd35-170">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-170">**Arguments**</span></span>

<span data-ttu-id="cbd35-171">Raccolta (T), dove T è uno dei tipi seguenti: `Int32`, `Int64`, `Double``Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="cbd35-172">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-172">**Return Value**</span></span>

<span data-ttu-id="cbd35-173">Tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-173">The type of `expression`.</span></span>

<span data-ttu-id="cbd35-174">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="cbd35-175">VAR (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-175">VAR(expression)</span></span>

<span data-ttu-id="cbd35-176">Restituisce la varianza statistica di tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="cbd35-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="cbd35-177">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-177">**Arguments**</span></span>

<span data-ttu-id="cbd35-178">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="cbd35-178">A Collection(`Double`).</span></span>

<span data-ttu-id="cbd35-179">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-179">**Return Value**</span></span>

<span data-ttu-id="cbd35-180">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-180">A `Double`.</span></span>

<span data-ttu-id="cbd35-181">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="cbd35-182">VARP (espressione)</span><span class="sxs-lookup"><span data-stu-id="cbd35-182">VARP(expression)</span></span>

<span data-ttu-id="cbd35-183">Restituisce la varianza statistica della popolazione per tutti i valori nell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="cbd35-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="cbd35-184">**argomenti**</span><span class="sxs-lookup"><span data-stu-id="cbd35-184">**Arguments**</span></span>

<span data-ttu-id="cbd35-185">Raccolta (`Double`).</span><span class="sxs-lookup"><span data-stu-id="cbd35-185">A Collection(`Double`).</span></span>

<span data-ttu-id="cbd35-186">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="cbd35-186">**Return Value**</span></span>

<span data-ttu-id="cbd35-187">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="cbd35-187">A `Double`.</span></span>

<span data-ttu-id="cbd35-188">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cbd35-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="cbd35-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbd35-189">See also</span></span>

- [<span data-ttu-id="cbd35-190">Funzioni di aggregazione (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cbd35-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="cbd35-191">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cbd35-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="cbd35-192">Funzioni di aggregazione canoniche</span><span class="sxs-lookup"><span data-stu-id="cbd35-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
