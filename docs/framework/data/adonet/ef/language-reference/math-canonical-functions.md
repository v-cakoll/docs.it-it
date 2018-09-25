---
title: Funzioni matematiche canoniche
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111653"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="46c96-102">Funzioni matematiche canoniche</span><span class="sxs-lookup"><span data-stu-id="46c96-102">Math Canonical Functions</span></span>

<span data-ttu-id="46c96-103">Entity SQL include le funzioni canoniche matematiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="46c96-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="46c96-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="46c96-104">Abs(value)</span></span>

<span data-ttu-id="46c96-105">Restituisce il valore assoluto di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="46c96-106">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-106">**Arguments**</span></span>

<span data-ttu-id="46c96-107">Un' `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="46c96-108">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-108">**Return Value**</span></span>

<span data-ttu-id="46c96-109">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-109">The type of `value`.</span></span>

<span data-ttu-id="46c96-110">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="46c96-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="46c96-111">Ceiling(value)</span></span>

<span data-ttu-id="46c96-112">Restituisce il valore integer più piccolo non minore di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="46c96-113">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-113">**Arguments**</span></span>

<span data-ttu-id="46c96-114">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="46c96-115">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-115">**Return Value**</span></span>

<span data-ttu-id="46c96-116">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-116">The type of `value`.</span></span>

<span data-ttu-id="46c96-117">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="46c96-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="46c96-118">Floor(value)</span></span>

<span data-ttu-id="46c96-119">Restituisce il valore integer più grande non maggiore di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="46c96-120">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-120">**Arguments**</span></span>

<span data-ttu-id="46c96-121">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="46c96-122">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-122">**Return Value**</span></span>

<span data-ttu-id="46c96-123">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-123">The type of `value`.</span></span>

<span data-ttu-id="46c96-124">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="46c96-125">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="46c96-125">Power(value, exponent)</span></span>

<span data-ttu-id="46c96-126">Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.</span><span class="sxs-lookup"><span data-stu-id="46c96-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="46c96-127">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="46c96-128">Un' `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="46c96-129">Un' `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="46c96-130">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-130">**Return Value**</span></span>

<span data-ttu-id="46c96-131">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-131">The type of `value`.</span></span>

<span data-ttu-id="46c96-132">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="46c96-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="46c96-133">Round(value)</span></span>

<span data-ttu-id="46c96-134">Restituisce la parte intera di `value` arrotondata al valore integer più vicino.</span><span class="sxs-lookup"><span data-stu-id="46c96-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="46c96-135">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-135">**Arguments**</span></span>

<span data-ttu-id="46c96-136">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="46c96-137">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-137">**Return Value**</span></span>

<span data-ttu-id="46c96-138">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-138">The type of `value`.</span></span>

<span data-ttu-id="46c96-139">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="46c96-140">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="46c96-140">Round(value, digits)</span></span>

<span data-ttu-id="46c96-141">Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="46c96-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="46c96-142">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="46c96-143">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="46c96-144">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="46c96-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="46c96-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-145">**Return Value**</span></span>

<span data-ttu-id="46c96-146">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-146">The type of `value`.</span></span>

<span data-ttu-id="46c96-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="46c96-148">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="46c96-148">Truncate(value, digits)</span></span>

<span data-ttu-id="46c96-149">Restituisce `value`, troncato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="46c96-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="46c96-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="46c96-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="46c96-151">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46c96-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="46c96-152">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="46c96-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="46c96-153">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="46c96-153">**Return Value**</span></span>

<span data-ttu-id="46c96-154">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="46c96-154">The type of `value`.</span></span>

<span data-ttu-id="46c96-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="46c96-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="46c96-156">Queste funzioni restituiscono `null` se l'input è `null`.</span><span class="sxs-lookup"><span data-stu-id="46c96-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="46c96-157">Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="46c96-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="46c96-158">Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="46c96-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c96-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46c96-159">See Also</span></span>  
 [<span data-ttu-id="46c96-160">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="46c96-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
