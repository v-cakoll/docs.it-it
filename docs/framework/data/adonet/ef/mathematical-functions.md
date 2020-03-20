---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149765"
---
# <a name="mathematical-functions"></a><span data-ttu-id="13c1e-102">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="13c1e-102">Mathematical Functions</span></span>

<span data-ttu-id="13c1e-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="13c1e-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="13c1e-104">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="13c1e-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="13c1e-105">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="13c1e-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="13c1e-106">Nella tabella seguente vengono descritte le funzioni matematiche SqlClient.</span><span class="sxs-lookup"><span data-stu-id="13c1e-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="13c1e-107">ABS(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-107">ABS(expression)</span></span>

<span data-ttu-id="13c1e-108">Esegue la funzione relativa al valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="13c1e-108">Performs the absolute value function.</span></span>

<span data-ttu-id="13c1e-109">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-109">**Arguments**</span></span>

<span data-ttu-id="13c1e-110">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-111">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-111">**Return Value**</span></span>

<span data-ttu-id="13c1e-112">Valore assoluto dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="13c1e-113">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="13c1e-114">ARCCOS(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-114">ACOS(expression)</span></span>

<span data-ttu-id="13c1e-115">Restituisce il valore dell'arcocoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="13c1e-116">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-116">**Arguments**</span></span>

<span data-ttu-id="13c1e-117">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-118">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-118">**Return Value**</span></span>

<span data-ttu-id="13c1e-119">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-119">A `Double`.</span></span>

<span data-ttu-id="13c1e-120">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="13c1e-121">ASIN(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-121">ASIN(expression)</span></span>

<span data-ttu-id="13c1e-122">Restituisce il valore dell'arcoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="13c1e-123">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-123">**Arguments**</span></span>

<span data-ttu-id="13c1e-124">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-125">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-125">**Return Value**</span></span>

<span data-ttu-id="13c1e-126">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-126">A `Double`.</span></span>

<span data-ttu-id="13c1e-127">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="13c1e-128">ATAN(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-128">ATAN(expression)</span></span>

<span data-ttu-id="13c1e-129">Restituisce il valore dell'arcotangente dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="13c1e-130">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-130">**Arguments**</span></span>

<span data-ttu-id="13c1e-131">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-132">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-132">**Return Value**</span></span>

<span data-ttu-id="13c1e-133">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-133">A `Double`.</span></span>

<span data-ttu-id="13c1e-134">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="13c1e-135">ATN2(espressione; espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="13c1e-136">Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.</span><span class="sxs-lookup"><span data-stu-id="13c1e-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="13c1e-137">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-137">**Arguments**</span></span>

<span data-ttu-id="13c1e-138">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-139">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-139">**Return Value**</span></span>

<span data-ttu-id="13c1e-140">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-140">A `Double`.</span></span>

<span data-ttu-id="13c1e-141">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="13c1e-142">ARROTONDA.</span><span class="sxs-lookup"><span data-stu-id="13c1e-142">CEILING(expression)</span></span>

<span data-ttu-id="13c1e-143">Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="13c1e-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="13c1e-144">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-144">**Arguments**</span></span>

<span data-ttu-id="13c1e-145">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-146">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-146">**Return Value**</span></span>

<span data-ttu-id="13c1e-147">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-148">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="13c1e-149">COS(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-149">COS(expression)</span></span>

<span data-ttu-id="13c1e-150">Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="13c1e-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="13c1e-151">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-151">**Arguments**</span></span>

<span data-ttu-id="13c1e-152">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-153">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-153">**Return Value**</span></span>

<span data-ttu-id="13c1e-154">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-154">A `Double`.</span></span>

<span data-ttu-id="13c1e-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="13c1e-156">COT(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-156">COT(expression)</span></span>

<span data-ttu-id="13c1e-157">Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="13c1e-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="13c1e-158">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-158">**Arguments**</span></span>

<span data-ttu-id="13c1e-159">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-160">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-160">**Return Value**</span></span>

<span data-ttu-id="13c1e-161">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-161">A `Double`.</span></span>

<span data-ttu-id="13c1e-162">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="13c1e-163">GRADI(radianti)</span><span class="sxs-lookup"><span data-stu-id="13c1e-163">DEGREES(radians)</span></span>

<span data-ttu-id="13c1e-164">Restituisce l'angolo corrispondente in gradi.</span><span class="sxs-lookup"><span data-stu-id="13c1e-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="13c1e-165">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-165">**Arguments**</span></span>

<span data-ttu-id="13c1e-166">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-167">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-167">**Return Value**</span></span>

<span data-ttu-id="13c1e-168">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-169">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="13c1e-170">EXP(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-170">EXP(expression)</span></span>

<span data-ttu-id="13c1e-171">Calcola il valore esponenziale dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="13c1e-172">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-172">**Arguments**</span></span>

<span data-ttu-id="13c1e-173">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-174">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-174">**Return Value**</span></span>

<span data-ttu-id="13c1e-175">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-175">A `Double`.</span></span>

<span data-ttu-id="13c1e-176">**Esempio**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="13c1e-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="13c1e-177">FLOOR(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-177">FLOOR(expression)</span></span>

<span data-ttu-id="13c1e-178">Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="13c1e-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="13c1e-179">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-179">**Arguments**</span></span>

<span data-ttu-id="13c1e-180">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-181">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-181">**Return Value**</span></span>

<span data-ttu-id="13c1e-182">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-182">A `Double`.</span></span>

<span data-ttu-id="13c1e-183">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="13c1e-184">LOG(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-184">LOG(expression)</span></span>

<span data-ttu-id="13c1e-185">Calcola il logaritmo naturale dell'espressione `float` specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="13c1e-186">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-186">**Arguments**</span></span>

<span data-ttu-id="13c1e-187">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-188">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-188">**Return Value**</span></span>

<span data-ttu-id="13c1e-189">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-189">A `Double`.</span></span>

<span data-ttu-id="13c1e-190">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="13c1e-191">LOG10(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-191">LOG10(expression)</span></span>

<span data-ttu-id="13c1e-192">Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="13c1e-193">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-193">**Arguments**</span></span>

<span data-ttu-id="13c1e-194">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-195">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-195">**Return Value**</span></span>

<span data-ttu-id="13c1e-196">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-196">A `Double`.</span></span>

<span data-ttu-id="13c1e-197">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="13c1e-198">PI()</span><span class="sxs-lookup"><span data-stu-id="13c1e-198">PI()</span></span>

<span data-ttu-id="13c1e-199">Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="13c1e-200">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-200">**Return Value**</span></span>

<span data-ttu-id="13c1e-201">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-201">A `Double`.</span></span>

<span data-ttu-id="13c1e-202">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="13c1e-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="13c1e-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="13c1e-204">Calcola il valore dell'espressione specificata elevato alla potenza indicata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="13c1e-205">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="13c1e-206">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="13c1e-207">Oggetto `Double` che rappresenta la potenza `numeric_expression`a cui elevare il file .</span><span class="sxs-lookup"><span data-stu-id="13c1e-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="13c1e-208">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-208">**Return Value**</span></span>

<span data-ttu-id="13c1e-209">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="13c1e-210">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="13c1e-211">RADIANTI(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-211">RADIANS(expression)</span></span>

<span data-ttu-id="13c1e-212">Converte i gradi in radianti.</span><span class="sxs-lookup"><span data-stu-id="13c1e-212">Converts degrees to radians.</span></span>

<span data-ttu-id="13c1e-213">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-213">**Arguments**</span></span>

<span data-ttu-id="13c1e-214">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-215">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-215">**Return Value**</span></span>

<span data-ttu-id="13c1e-216">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-217">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="13c1e-218">RAND([seme])</span><span class="sxs-lookup"><span data-stu-id="13c1e-218">RAND([seed])</span></span>

<span data-ttu-id="13c1e-219">Restituisce un valore casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="13c1e-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="13c1e-220">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-220">**Arguments**</span></span>

<span data-ttu-id="13c1e-221">Valore del valore `Int32`di seme come oggetto .</span><span class="sxs-lookup"><span data-stu-id="13c1e-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="13c1e-222">Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="13c1e-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="13c1e-223">Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="13c1e-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="13c1e-224">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-224">**Return Value**</span></span>

<span data-ttu-id="13c1e-225">Valore `Double` casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="13c1e-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="13c1e-226">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="13c1e-227">ARROTONDA(numeric_expression, lunghezza[,funzione])</span><span class="sxs-lookup"><span data-stu-id="13c1e-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="13c1e-228">Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="13c1e-229">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="13c1e-230">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="13c1e-231">Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="13c1e-232">Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="13c1e-233">Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="13c1e-234">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="13c1e-234">Optional.</span></span> <span data-ttu-id="13c1e-235">Oggetto `Int32` che rappresenta il tipo di operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="13c1e-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="13c1e-236">Quando la funzione viene omessa o ha `numeric_expression` un valore pari a 0 (impostazione predefinita), viene arrotondata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="13c1e-237">Quando viene specificato un valore `numeric_expression` diverso da 0, viene troncato.</span><span class="sxs-lookup"><span data-stu-id="13c1e-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="13c1e-238">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-238">**Return Value**</span></span>

<span data-ttu-id="13c1e-239">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="13c1e-240">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="13c1e-241">SEGNO(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-241">SIGN(expression)</span></span>

<span data-ttu-id="13c1e-242">Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="13c1e-243">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-243">**Arguments**</span></span>

<span data-ttu-id="13c1e-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="13c1e-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="13c1e-245">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-245">**Return Value**</span></span>

<span data-ttu-id="13c1e-246">Un `Int32` `Int64`oggetto `Double`, `Decimal`, , o .</span><span class="sxs-lookup"><span data-stu-id="13c1e-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="13c1e-247">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="13c1e-248">SIN(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-248">SIN(expression)</span></span>

<span data-ttu-id="13c1e-249">Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="13c1e-250">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-250">**Arguments**</span></span>

<span data-ttu-id="13c1e-251">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-252">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-252">**Return Value**</span></span>

<span data-ttu-id="13c1e-253">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-253">A `Double`.</span></span>

<span data-ttu-id="13c1e-254">**Esempio**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="13c1e-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="13c1e-255">RADQ(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-255">SQRT(expression)</span></span>

<span data-ttu-id="13c1e-256">Restituisce la radice quadrata dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="13c1e-257">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-257">**Arguments**</span></span>

<span data-ttu-id="13c1e-258">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-259">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-259">**Return Value**</span></span>

<span data-ttu-id="13c1e-260">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-260">A `Double`.</span></span>

<span data-ttu-id="13c1e-261">**Esempio**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="13c1e-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="13c1e-262">SQUARE(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-262">SQUARE(expression)</span></span>

<span data-ttu-id="13c1e-263">Restituisce la radice dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="13c1e-264">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-264">**Arguments**</span></span>

<span data-ttu-id="13c1e-265">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="13c1e-266">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-266">**Return Value**</span></span>

<span data-ttu-id="13c1e-267">`Double`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-267">A `Double`.</span></span>

<span data-ttu-id="13c1e-268">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="13c1e-269">TAN(espressione)</span><span class="sxs-lookup"><span data-stu-id="13c1e-269">TAN(expression)</span></span>

<span data-ttu-id="13c1e-270">Calcola la tangente di un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="13c1e-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="13c1e-271">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="13c1e-271">**Arguments**</span></span>

<span data-ttu-id="13c1e-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="13c1e-272">`expression`: `Double`</span></span>

<span data-ttu-id="13c1e-273">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="13c1e-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="13c1e-274">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="13c1e-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="13c1e-275">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13c1e-275">See also</span></span>

- [<span data-ttu-id="13c1e-276">Funzioni matematiche (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="13c1e-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="13c1e-277">SqlClient per funzioni Entity Framework</span><span class="sxs-lookup"><span data-stu-id="13c1e-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
