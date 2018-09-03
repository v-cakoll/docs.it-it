---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456451"
---
# <a name="mathematical-functions"></a><span data-ttu-id="2981e-102">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="2981e-102">Mathematical Functions</span></span>

<span data-ttu-id="2981e-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="2981e-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="2981e-104">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2981e-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="2981e-105">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Nella tabella che segue sono illustrate le funzioni matematiche SqlClient.</span><span class="sxs-lookup"><span data-stu-id="2981e-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="2981e-106">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-106">ABS(expression)</span></span>

<span data-ttu-id="2981e-107">Esegue la funzione relativa al valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="2981e-107">Performs the absolute value function.</span></span>

<span data-ttu-id="2981e-108">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-108">**Arguments**</span></span>

<span data-ttu-id="2981e-109">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2981e-110">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-110">**Return Value**</span></span>

<span data-ttu-id="2981e-111">Valore assoluto dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="2981e-112">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="2981e-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-113">ACOS(expression)</span></span>

<span data-ttu-id="2981e-114">Restituisce il valore dell'arcocoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="2981e-115">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-115">**Arguments**</span></span>

<span data-ttu-id="2981e-116">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="2981e-117">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-117">**Return Value**</span></span>

<span data-ttu-id="2981e-118">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-118">A `Double`.</span></span>

<span data-ttu-id="2981e-119">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="2981e-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-120">ASIN(expression)</span></span>

<span data-ttu-id="2981e-121">Restituisce il valore dell'arcoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="2981e-122">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-122">**Arguments**</span></span>

<span data-ttu-id="2981e-123">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="2981e-124">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-124">**Return Value**</span></span>

<span data-ttu-id="2981e-125">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-125">A `Double`.</span></span>

<span data-ttu-id="2981e-126">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="2981e-127">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-127">ATAN(expression)</span></span>

<span data-ttu-id="2981e-128">Restituisce il valore dell'arcotangente dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="2981e-129">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-129">**Arguments**</span></span>

<span data-ttu-id="2981e-130">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="2981e-131">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-131">**Return Value**</span></span>

<span data-ttu-id="2981e-132">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-132">A `Double`.</span></span>

<span data-ttu-id="2981e-133">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="2981e-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="2981e-135">Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.</span><span class="sxs-lookup"><span data-stu-id="2981e-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="2981e-136">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-136">**Arguments**</span></span>

<span data-ttu-id="2981e-137">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="2981e-138">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-138">**Return Value**</span></span>

<span data-ttu-id="2981e-139">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-139">A `Double`.</span></span>

<span data-ttu-id="2981e-140">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="2981e-141">Ceiling(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-141">CEILING(expression)</span></span>

<span data-ttu-id="2981e-142">Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="2981e-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="2981e-143">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-143">**Arguments**</span></span>

<span data-ttu-id="2981e-144">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2981e-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-145">**Return Value**</span></span>

<span data-ttu-id="2981e-146">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="2981e-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="2981e-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-148">COS(expression)</span></span>

<span data-ttu-id="2981e-149">Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="2981e-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="2981e-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-150">**Arguments**</span></span> 

<span data-ttu-id="2981e-151">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-152">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-152">**Return Value**</span></span> 

<span data-ttu-id="2981e-153">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-153">A `Double`.</span></span> 

<span data-ttu-id="2981e-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="2981e-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-155">COT(expression)</span></span>

<span data-ttu-id="2981e-156">Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="2981e-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="2981e-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-157">**Arguments**</span></span> 

<span data-ttu-id="2981e-158">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-159">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-159">**Return Value**</span></span> 

<span data-ttu-id="2981e-160">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-160">A `Double`.</span></span> 

<span data-ttu-id="2981e-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="2981e-162">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="2981e-162">DEGREES(radians)</span></span>

<span data-ttu-id="2981e-163">Restituisce l'angolo corrispondente in gradi.</span><span class="sxs-lookup"><span data-stu-id="2981e-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="2981e-164">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-164">**Arguments**</span></span> 

<span data-ttu-id="2981e-165">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2981e-166">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-166">**Return Value**</span></span> 

<span data-ttu-id="2981e-167">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2981e-168">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="2981e-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-169">EXP(expression)</span></span>

<span data-ttu-id="2981e-170">Calcola il valore esponenziale dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="2981e-171">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-171">**Arguments**</span></span> 

<span data-ttu-id="2981e-172">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-173">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-173">**Return Value**</span></span> 

<span data-ttu-id="2981e-174">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-174">A `Double`.</span></span> 

<span data-ttu-id="2981e-175">**Esempio** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="2981e-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="2981e-176">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-176">FLOOR(expression)</span></span>

<span data-ttu-id="2981e-177">Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="2981e-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="2981e-178">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-178">**Arguments**</span></span> 

<span data-ttu-id="2981e-179">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-180">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-180">**Return Value**</span></span> 

<span data-ttu-id="2981e-181">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-181">A `Double`.</span></span> 

<span data-ttu-id="2981e-182">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="2981e-183">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-183">LOG(expression)</span></span>

<span data-ttu-id="2981e-184">Calcola il logaritmo naturale dell'espressione `float` specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="2981e-185">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-185">**Arguments**</span></span> 

<span data-ttu-id="2981e-186">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-187">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-187">**Return Value**</span></span> 

<span data-ttu-id="2981e-188">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-188">A `Double`.</span></span> 

<span data-ttu-id="2981e-189">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="2981e-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-190">LOG10(expression)</span></span>

<span data-ttu-id="2981e-191">Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="2981e-192">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-192">**Arguments**</span></span> 

<span data-ttu-id="2981e-193">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-194">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-194">**Return Value**</span></span> 

<span data-ttu-id="2981e-195">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-195">A `Double`.</span></span> 

<span data-ttu-id="2981e-196">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="2981e-197">PI</span><span class="sxs-lookup"><span data-stu-id="2981e-197">PI()</span></span>

<span data-ttu-id="2981e-198">Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="2981e-199">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-199">**Return Value**</span></span> 

<span data-ttu-id="2981e-200">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-200">A `Double`.</span></span> 

<span data-ttu-id="2981e-201">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="2981e-202">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="2981e-203">Calcola il valore dell'espressione specificata elevato alla potenza indicata.</span><span class="sxs-lookup"><span data-stu-id="2981e-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="2981e-204">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="2981e-205">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="2981e-206">Oggetto `Double` che rappresenta la potenza a cui elevare il `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="2981e-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="2981e-207">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-207">**Return Value**</span></span> 

<span data-ttu-id="2981e-208">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="2981e-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="2981e-209">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="2981e-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-210">RADIANS(expression)</span></span>

<span data-ttu-id="2981e-211">Converte i gradi in radianti.</span><span class="sxs-lookup"><span data-stu-id="2981e-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="2981e-212">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-212">**Arguments**</span></span> 

<span data-ttu-id="2981e-213">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2981e-214">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-214">**Return Value**</span></span> 

<span data-ttu-id="2981e-215">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2981e-216">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="2981e-217">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="2981e-217">RAND([seed])</span></span>

<span data-ttu-id="2981e-218">Restituisce un valore casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="2981e-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="2981e-219">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-219">**Arguments**</span></span> 

<span data-ttu-id="2981e-220">Il valore di inizializzazione come un `Int32`.</span><span class="sxs-lookup"><span data-stu-id="2981e-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="2981e-221">Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="2981e-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="2981e-222">Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="2981e-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="2981e-223">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-223">**Return Value**</span></span> 

<span data-ttu-id="2981e-224">Valore `Double` casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="2981e-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="2981e-225">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="2981e-226">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="2981e-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="2981e-227">Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="2981e-228">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="2981e-229">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="2981e-230">Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="2981e-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="2981e-231">Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="2981e-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="2981e-232">Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="2981e-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="2981e-233">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2981e-233">Optional.</span></span> <span data-ttu-id="2981e-234">Un `Int32` che rappresenta il tipo di operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="2981e-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="2981e-235">Quando viene omesso oppure ha un valore pari a 0 (impostazione predefinita), `numeric_expression` viene arrotondato.</span><span class="sxs-lookup"><span data-stu-id="2981e-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="2981e-236">Quando un valore diverso da è specificato 0, `numeric_expression` viene troncato.</span><span class="sxs-lookup"><span data-stu-id="2981e-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="2981e-237">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-237">**Return Value**</span></span> 

<span data-ttu-id="2981e-238">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="2981e-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="2981e-239">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="2981e-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-240">SIGN(expression)</span></span> 

<span data-ttu-id="2981e-241">Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="2981e-242">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-242">**Arguments**</span></span> 

<span data-ttu-id="2981e-243">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="2981e-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="2981e-244">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-244">**Return Value**</span></span> 

<span data-ttu-id="2981e-245">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2981e-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="2981e-246">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="2981e-247">Sin(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-247">SIN(expression)</span></span>

<span data-ttu-id="2981e-248">Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="2981e-249">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-249">**Arguments**</span></span> 

<span data-ttu-id="2981e-250">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-251">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-251">**Return Value**</span></span> 

<span data-ttu-id="2981e-252">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-252">A `Double`.</span></span> 

<span data-ttu-id="2981e-253">**Esempio** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="2981e-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="2981e-254">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-254">SQRT(expression)</span></span>

<span data-ttu-id="2981e-255">Restituisce la radice quadrata dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="2981e-256">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-256">**Arguments**</span></span> 

<span data-ttu-id="2981e-257">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-258">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-258">**Return Value**</span></span> 

<span data-ttu-id="2981e-259">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-259">A `Double`.</span></span> 

<span data-ttu-id="2981e-260">**Esempio** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="2981e-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="2981e-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-261">SQUARE(expression)</span></span>

<span data-ttu-id="2981e-262">Restituisce la radice dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="2981e-263">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-263">**Arguments**</span></span> 

<span data-ttu-id="2981e-264">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="2981e-265">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-265">**Return Value**</span></span> 

<span data-ttu-id="2981e-266">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="2981e-266">A `Double`.</span></span> 

<span data-ttu-id="2981e-267">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="2981e-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="2981e-268">TAN(expression)</span></span>

<span data-ttu-id="2981e-269">Calcola la tangente di un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="2981e-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="2981e-270">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="2981e-270">**Arguments**</span></span> 

<span data-ttu-id="2981e-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="2981e-271">`expression`: `Double`</span></span> 

<span data-ttu-id="2981e-272">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="2981e-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="2981e-273">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="2981e-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="2981e-274">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2981e-274">See also</span></span>

<span data-ttu-id="2981e-275">Per altre informazioni sulle funzioni matematiche supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="2981e-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="2981e-276">**SQL Server 2005:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="2981e-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="2981e-277">**SQL Server 2008:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="2981e-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="2981e-278">**SQL Server 2012 e versioni successive:** [funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="2981e-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="2981e-279">SqlClient per funzioni Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2981e-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
