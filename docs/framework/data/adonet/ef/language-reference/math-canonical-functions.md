---
title: Funzioni matematiche canoniche
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228770"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="79357-102">Funzioni matematiche canoniche</span><span class="sxs-lookup"><span data-stu-id="79357-102">Math Canonical Functions</span></span>

<span data-ttu-id="79357-103">Entity SQL include le funzioni canoniche matematiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="79357-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="79357-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="79357-104">Abs(value)</span></span>

<span data-ttu-id="79357-105">Restituisce il valore assoluto di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="79357-106">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-106">**Arguments**</span></span>

<span data-ttu-id="79357-107">Un' `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="79357-108">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-108">**Return Value**</span></span>

<span data-ttu-id="79357-109">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-109">The type of `value`.</span></span>

<span data-ttu-id="79357-110">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="79357-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="79357-111">Ceiling(value)</span></span>

<span data-ttu-id="79357-112">Restituisce il valore integer più piccolo non minore di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="79357-113">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-113">**Arguments**</span></span>

<span data-ttu-id="79357-114">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="79357-115">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-115">**Return Value**</span></span>

<span data-ttu-id="79357-116">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-116">The type of `value`.</span></span>

<span data-ttu-id="79357-117">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="79357-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="79357-118">Floor(value)</span></span>

<span data-ttu-id="79357-119">Restituisce il valore integer più grande non maggiore di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="79357-120">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-120">**Arguments**</span></span>

<span data-ttu-id="79357-121">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="79357-122">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-122">**Return Value**</span></span>

<span data-ttu-id="79357-123">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-123">The type of `value`.</span></span>

<span data-ttu-id="79357-124">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="79357-125">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="79357-125">Power(value, exponent)</span></span>

<span data-ttu-id="79357-126">Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.</span><span class="sxs-lookup"><span data-stu-id="79357-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="79357-127">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="79357-128">Un' `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="79357-129">Un' `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="79357-130">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-130">**Return Value**</span></span>

<span data-ttu-id="79357-131">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-131">The type of `value`.</span></span>

<span data-ttu-id="79357-132">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="79357-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="79357-133">Round(value)</span></span>

<span data-ttu-id="79357-134">Restituisce la parte intera di `value` arrotondata al valore integer più vicino.</span><span class="sxs-lookup"><span data-stu-id="79357-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="79357-135">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-135">**Arguments**</span></span>

<span data-ttu-id="79357-136">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="79357-137">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-137">**Return Value**</span></span>

<span data-ttu-id="79357-138">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-138">The type of `value`.</span></span>

<span data-ttu-id="79357-139">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="79357-140">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="79357-140">Round(value, digits)</span></span>

<span data-ttu-id="79357-141">Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="79357-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="79357-142">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="79357-143">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="79357-144">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="79357-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="79357-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-145">**Return Value**</span></span>

<span data-ttu-id="79357-146">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-146">The type of `value`.</span></span>

<span data-ttu-id="79357-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="79357-148">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="79357-148">Truncate(value, digits)</span></span>

<span data-ttu-id="79357-149">Restituisce `value`, troncato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="79357-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="79357-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="79357-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="79357-151">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="79357-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="79357-152">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="79357-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="79357-153">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="79357-153">**Return Value**</span></span>

<span data-ttu-id="79357-154">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="79357-154">The type of `value`.</span></span>

<span data-ttu-id="79357-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="79357-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="79357-156">Queste funzioni restituiscono `null` se l'input è `null`.</span><span class="sxs-lookup"><span data-stu-id="79357-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="79357-157">Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="79357-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="79357-158">Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="79357-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79357-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79357-159">See also</span></span>

- [<span data-ttu-id="79357-160">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="79357-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
