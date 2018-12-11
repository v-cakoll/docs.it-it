---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 63f83532c399f77e268913da3198327345b9c2ee
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143675"
---
# <a name="mathematical-functions"></a><span data-ttu-id="19e69-102">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="19e69-102">Mathematical Functions</span></span>

<span data-ttu-id="19e69-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="19e69-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="19e69-104">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="19e69-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="19e69-105">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="19e69-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="19e69-106">La tabella seguente descrive le funzioni matematiche SqlClient.</span><span class="sxs-lookup"><span data-stu-id="19e69-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="19e69-107">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-107">ABS(expression)</span></span>

<span data-ttu-id="19e69-108">Esegue la funzione relativa al valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="19e69-108">Performs the absolute value function.</span></span>

<span data-ttu-id="19e69-109">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-109">**Arguments**</span></span>

<span data-ttu-id="19e69-110">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="19e69-111">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-111">**Return Value**</span></span>

<span data-ttu-id="19e69-112">Valore assoluto dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="19e69-113">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="19e69-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-114">ACOS(expression)</span></span>

<span data-ttu-id="19e69-115">Restituisce il valore dell'arcocoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="19e69-116">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-116">**Arguments**</span></span>

<span data-ttu-id="19e69-117">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="19e69-118">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-118">**Return Value**</span></span>

<span data-ttu-id="19e69-119">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-119">A `Double`.</span></span>

<span data-ttu-id="19e69-120">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="19e69-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-121">ASIN(expression)</span></span>

<span data-ttu-id="19e69-122">Restituisce il valore dell'arcoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="19e69-123">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-123">**Arguments**</span></span>

<span data-ttu-id="19e69-124">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="19e69-125">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-125">**Return Value**</span></span>

<span data-ttu-id="19e69-126">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-126">A `Double`.</span></span>

<span data-ttu-id="19e69-127">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="19e69-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-128">ATAN(expression)</span></span>

<span data-ttu-id="19e69-129">Restituisce il valore dell'arcotangente dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="19e69-130">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-130">**Arguments**</span></span>

<span data-ttu-id="19e69-131">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="19e69-132">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-132">**Return Value**</span></span>

<span data-ttu-id="19e69-133">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-133">A `Double`.</span></span>

<span data-ttu-id="19e69-134">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="19e69-135">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="19e69-136">Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.</span><span class="sxs-lookup"><span data-stu-id="19e69-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="19e69-137">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-137">**Arguments**</span></span>

<span data-ttu-id="19e69-138">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="19e69-139">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-139">**Return Value**</span></span>

<span data-ttu-id="19e69-140">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-140">A `Double`.</span></span>

<span data-ttu-id="19e69-141">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="19e69-142">Ceiling(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-142">CEILING(expression)</span></span>

<span data-ttu-id="19e69-143">Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="19e69-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="19e69-144">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-144">**Arguments**</span></span>

<span data-ttu-id="19e69-145">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="19e69-146">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-146">**Return Value**</span></span>

<span data-ttu-id="19e69-147">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="19e69-148">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="19e69-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-149">COS(expression)</span></span>

<span data-ttu-id="19e69-150">Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="19e69-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="19e69-151">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-151">**Arguments**</span></span> 

<span data-ttu-id="19e69-152">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-153">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-153">**Return Value**</span></span> 

<span data-ttu-id="19e69-154">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-154">A `Double`.</span></span> 

<span data-ttu-id="19e69-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="19e69-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-156">COT(expression)</span></span>

<span data-ttu-id="19e69-157">Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="19e69-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="19e69-158">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-158">**Arguments**</span></span> 

<span data-ttu-id="19e69-159">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-160">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-160">**Return Value**</span></span> 

<span data-ttu-id="19e69-161">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-161">A `Double`.</span></span> 

<span data-ttu-id="19e69-162">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="19e69-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="19e69-163">DEGREES(radians)</span></span>

<span data-ttu-id="19e69-164">Restituisce l'angolo corrispondente in gradi.</span><span class="sxs-lookup"><span data-stu-id="19e69-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="19e69-165">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-165">**Arguments**</span></span> 

<span data-ttu-id="19e69-166">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="19e69-167">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-167">**Return Value**</span></span> 

<span data-ttu-id="19e69-168">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="19e69-169">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="19e69-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-170">EXP(expression)</span></span>

<span data-ttu-id="19e69-171">Calcola il valore esponenziale dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="19e69-172">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-172">**Arguments**</span></span> 

<span data-ttu-id="19e69-173">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-174">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-174">**Return Value**</span></span> 

<span data-ttu-id="19e69-175">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-175">A `Double`.</span></span> 

<span data-ttu-id="19e69-176">**Esempio** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="19e69-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="19e69-177">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-177">FLOOR(expression)</span></span>

<span data-ttu-id="19e69-178">Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="19e69-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="19e69-179">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-179">**Arguments**</span></span> 

<span data-ttu-id="19e69-180">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-181">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-181">**Return Value**</span></span> 

<span data-ttu-id="19e69-182">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-182">A `Double`.</span></span> 

<span data-ttu-id="19e69-183">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="19e69-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-184">LOG(expression)</span></span>

<span data-ttu-id="19e69-185">Calcola il logaritmo naturale dell'espressione `float` specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="19e69-186">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-186">**Arguments**</span></span> 

<span data-ttu-id="19e69-187">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-188">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-188">**Return Value**</span></span> 

<span data-ttu-id="19e69-189">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-189">A `Double`.</span></span> 

<span data-ttu-id="19e69-190">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="19e69-191">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-191">LOG10(expression)</span></span>

<span data-ttu-id="19e69-192">Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="19e69-193">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-193">**Arguments**</span></span> 

<span data-ttu-id="19e69-194">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-195">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-195">**Return Value**</span></span> 

<span data-ttu-id="19e69-196">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-196">A `Double`.</span></span> 

<span data-ttu-id="19e69-197">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="19e69-198">PI</span><span class="sxs-lookup"><span data-stu-id="19e69-198">PI()</span></span>

<span data-ttu-id="19e69-199">Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="19e69-200">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-200">**Return Value**</span></span> 

<span data-ttu-id="19e69-201">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-201">A `Double`.</span></span> 

<span data-ttu-id="19e69-202">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="19e69-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="19e69-204">Calcola il valore dell'espressione specificata elevato alla potenza indicata.</span><span class="sxs-lookup"><span data-stu-id="19e69-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="19e69-205">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="19e69-206">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="19e69-207">Oggetto `Double` che rappresenta la potenza a cui elevare il `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="19e69-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="19e69-208">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-208">**Return Value**</span></span> 

<span data-ttu-id="19e69-209">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="19e69-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="19e69-210">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="19e69-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-211">RADIANS(expression)</span></span>

<span data-ttu-id="19e69-212">Converte i gradi in radianti.</span><span class="sxs-lookup"><span data-stu-id="19e69-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="19e69-213">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-213">**Arguments**</span></span> 

<span data-ttu-id="19e69-214">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="19e69-215">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-215">**Return Value**</span></span> 

<span data-ttu-id="19e69-216">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="19e69-217">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="19e69-218">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="19e69-218">RAND([seed])</span></span>

<span data-ttu-id="19e69-219">Restituisce un valore casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="19e69-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="19e69-220">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-220">**Arguments**</span></span> 

<span data-ttu-id="19e69-221">Il valore di inizializzazione come un `Int32`.</span><span class="sxs-lookup"><span data-stu-id="19e69-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="19e69-222">Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="19e69-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="19e69-223">Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="19e69-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="19e69-224">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-224">**Return Value**</span></span> 

<span data-ttu-id="19e69-225">Valore `Double` casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="19e69-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="19e69-226">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="19e69-227">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="19e69-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="19e69-228">Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="19e69-229">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="19e69-230">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="19e69-231">Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="19e69-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="19e69-232">Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="19e69-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="19e69-233">Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="19e69-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="19e69-234">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="19e69-234">Optional.</span></span> <span data-ttu-id="19e69-235">Un `Int32` che rappresenta il tipo di operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19e69-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="19e69-236">Quando viene omesso oppure ha un valore pari a 0 (impostazione predefinita), `numeric_expression` viene arrotondato.</span><span class="sxs-lookup"><span data-stu-id="19e69-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="19e69-237">Quando un valore diverso da è specificato 0, `numeric_expression` viene troncato.</span><span class="sxs-lookup"><span data-stu-id="19e69-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="19e69-238">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-238">**Return Value**</span></span> 

<span data-ttu-id="19e69-239">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="19e69-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="19e69-240">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="19e69-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-241">SIGN(expression)</span></span> 

<span data-ttu-id="19e69-242">Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="19e69-243">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-243">**Arguments**</span></span> 

<span data-ttu-id="19e69-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="19e69-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="19e69-245">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-245">**Return Value**</span></span> 

<span data-ttu-id="19e69-246">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19e69-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="19e69-247">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="19e69-248">Sin(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-248">SIN(expression)</span></span>

<span data-ttu-id="19e69-249">Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="19e69-250">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-250">**Arguments**</span></span> 

<span data-ttu-id="19e69-251">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-252">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-252">**Return Value**</span></span> 

<span data-ttu-id="19e69-253">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-253">A `Double`.</span></span> 

<span data-ttu-id="19e69-254">**Esempio** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="19e69-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="19e69-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-255">SQRT(expression)</span></span>

<span data-ttu-id="19e69-256">Restituisce la radice quadrata dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="19e69-257">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-257">**Arguments**</span></span> 

<span data-ttu-id="19e69-258">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-259">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-259">**Return Value**</span></span> 

<span data-ttu-id="19e69-260">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-260">A `Double`.</span></span> 

<span data-ttu-id="19e69-261">**Esempio** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="19e69-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="19e69-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-262">SQUARE(expression)</span></span>

<span data-ttu-id="19e69-263">Restituisce la radice dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="19e69-264">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-264">**Arguments**</span></span> 

<span data-ttu-id="19e69-265">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="19e69-266">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-266">**Return Value**</span></span> 

<span data-ttu-id="19e69-267">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="19e69-267">A `Double`.</span></span> 

<span data-ttu-id="19e69-268">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="19e69-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="19e69-269">TAN(expression)</span></span>

<span data-ttu-id="19e69-270">Calcola la tangente di un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="19e69-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="19e69-271">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="19e69-271">**Arguments**</span></span> 

<span data-ttu-id="19e69-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="19e69-272">`expression`: `Double`</span></span> 

<span data-ttu-id="19e69-273">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="19e69-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="19e69-274">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="19e69-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="19e69-275">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19e69-275">See also</span></span>

<span data-ttu-id="19e69-276">Per altre informazioni sulle funzioni matematiche supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="19e69-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="19e69-277">**SQL Server 2005:** [Funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="19e69-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="19e69-278">**SQL Server 2008:** [Funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="19e69-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="19e69-279">**SQL Server 2012 e versioni successive:** [Funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="19e69-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="19e69-280">SqlClient per funzioni Entity Framework</span><span class="sxs-lookup"><span data-stu-id="19e69-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
