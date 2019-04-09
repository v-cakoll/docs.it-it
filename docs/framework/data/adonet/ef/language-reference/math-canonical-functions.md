---
title: Funzioni matematiche canoniche
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228770"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="db1aa-102">Funzioni matematiche canoniche</span><span class="sxs-lookup"><span data-stu-id="db1aa-102">Math Canonical Functions</span></span>

<span data-ttu-id="db1aa-103">Entity SQL include le funzioni canoniche matematiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="db1aa-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="db1aa-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="db1aa-104">Abs(value)</span></span>

<span data-ttu-id="db1aa-105">Restituisce il valore assoluto di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-105">Returns the absolute value of `value`.</span></span>

**<span data-ttu-id="db1aa-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-106">Arguments</span></span>**

<span data-ttu-id="db1aa-107">Un' `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="db1aa-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-108">Return Value</span></span>**

<span data-ttu-id="db1aa-109">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-109">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-110">Example</span></span>**

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="db1aa-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="db1aa-111">Ceiling(value)</span></span>

<span data-ttu-id="db1aa-112">Restituisce il valore integer più piccolo non minore di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-112">Returns the smallest integer that is not less than `value`.</span></span>

**<span data-ttu-id="db1aa-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-113">Arguments</span></span>**

<span data-ttu-id="db1aa-114">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-114">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="db1aa-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-115">Return Value</span></span>**

<span data-ttu-id="db1aa-116">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-116">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-117">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="db1aa-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="db1aa-118">Floor(value)</span></span>

<span data-ttu-id="db1aa-119">Restituisce il valore integer più grande non maggiore di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-119">Returns the largest integer that is not greater than `value`.</span></span>

**<span data-ttu-id="db1aa-120">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-120">Arguments</span></span>**

<span data-ttu-id="db1aa-121">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-121">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="db1aa-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-122">Return Value</span></span>**

<span data-ttu-id="db1aa-123">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-123">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-124">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="db1aa-125">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="db1aa-125">Power(value, exponent)</span></span>

<span data-ttu-id="db1aa-126">Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.</span><span class="sxs-lookup"><span data-stu-id="db1aa-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

**<span data-ttu-id="db1aa-127">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-127">Arguments</span></span>**

|  |  |
|--|--|
|`value` | <span data-ttu-id="db1aa-128">Un' `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="db1aa-129">Un' `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

**<span data-ttu-id="db1aa-130">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-130">Return Value</span></span>**

<span data-ttu-id="db1aa-131">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-131">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-132">Example</span></span>**

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="db1aa-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="db1aa-133">Round(value)</span></span>

<span data-ttu-id="db1aa-134">Restituisce la parte intera di `value` arrotondata al valore integer più vicino.</span><span class="sxs-lookup"><span data-stu-id="db1aa-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

**<span data-ttu-id="db1aa-135">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-135">Arguments</span></span>**

<span data-ttu-id="db1aa-136">Oggetto `Single`, `Double`, e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-136">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="db1aa-137">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-137">Return Value</span></span>**

<span data-ttu-id="db1aa-138">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-138">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-139">Example</span></span>**

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="db1aa-140">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="db1aa-140">Round(value, digits)</span></span>

<span data-ttu-id="db1aa-141">Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="db1aa-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

**<span data-ttu-id="db1aa-142">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-142">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="db1aa-143">o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-143">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="db1aa-144">o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-144">or `Int32`.</span></span>|

**<span data-ttu-id="db1aa-145">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-145">Return Value</span></span>**

<span data-ttu-id="db1aa-146">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-146">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-147">Example</span></span>**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="db1aa-148">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="db1aa-148">Truncate(value, digits)</span></span>

<span data-ttu-id="db1aa-149">Restituisce `value`, troncato al valore di `digits` specificato più vicino.</span><span class="sxs-lookup"><span data-stu-id="db1aa-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

**<span data-ttu-id="db1aa-150">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db1aa-150">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="db1aa-151">o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-151">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="db1aa-152">o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-152">or `Int32`.</span></span>|

**<span data-ttu-id="db1aa-153">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db1aa-153">Return Value</span></span>**

<span data-ttu-id="db1aa-154">Tipo di `value`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-154">The type of `value`.</span></span>

**<span data-ttu-id="db1aa-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="db1aa-155">Example</span></span>**

`Truncate(748.58,1)`  
  
 <span data-ttu-id="db1aa-156">Queste funzioni restituiscono `null` se l'input è `null`.</span><span class="sxs-lookup"><span data-stu-id="db1aa-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="db1aa-157">Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="db1aa-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="db1aa-158">Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="db1aa-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1aa-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db1aa-159">See also</span></span>

- [<span data-ttu-id="db1aa-160">Funzioni canoniche</span><span class="sxs-lookup"><span data-stu-id="db1aa-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
