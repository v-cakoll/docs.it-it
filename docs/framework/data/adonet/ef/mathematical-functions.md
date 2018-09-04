---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560652"
---
# <a name="mathematical-functions"></a><span data-ttu-id="ece11-102">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="ece11-102">Mathematical Functions</span></span>

<span data-ttu-id="ece11-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="ece11-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="ece11-104">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ece11-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="ece11-105">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Nella tabella che segue sono illustrate le funzioni matematiche SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ece11-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="ece11-106">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-106">ABS(expression)</span></span>

<span data-ttu-id="ece11-107">Esegue la funzione relativa al valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="ece11-107">Performs the absolute value function.</span></span>

<span data-ttu-id="ece11-108">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-108">**Arguments**</span></span>

<span data-ttu-id="ece11-109">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ece11-110">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-110">**Return Value**</span></span>

<span data-ttu-id="ece11-111">Valore assoluto dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="ece11-112">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="ece11-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-113">ACOS(expression)</span></span>

<span data-ttu-id="ece11-114">Restituisce il valore dell'arcocoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="ece11-115">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-115">**Arguments**</span></span>

<span data-ttu-id="ece11-116">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="ece11-117">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-117">**Return Value**</span></span>

<span data-ttu-id="ece11-118">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-118">A `Double`.</span></span>

<span data-ttu-id="ece11-119">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="ece11-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-120">ASIN(expression)</span></span>

<span data-ttu-id="ece11-121">Restituisce il valore dell'arcoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="ece11-122">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-122">**Arguments**</span></span>

<span data-ttu-id="ece11-123">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="ece11-124">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-124">**Return Value**</span></span>

<span data-ttu-id="ece11-125">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-125">A `Double`.</span></span>

<span data-ttu-id="ece11-126">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="ece11-127">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-127">ATAN(expression)</span></span>

<span data-ttu-id="ece11-128">Restituisce il valore dell'arcotangente dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="ece11-129">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-129">**Arguments**</span></span>

<span data-ttu-id="ece11-130">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="ece11-131">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-131">**Return Value**</span></span>

<span data-ttu-id="ece11-132">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-132">A `Double`.</span></span>

<span data-ttu-id="ece11-133">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="ece11-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="ece11-135">Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.</span><span class="sxs-lookup"><span data-stu-id="ece11-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="ece11-136">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-136">**Arguments**</span></span>

<span data-ttu-id="ece11-137">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="ece11-138">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-138">**Return Value**</span></span>

<span data-ttu-id="ece11-139">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-139">A `Double`.</span></span>

<span data-ttu-id="ece11-140">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="ece11-141">Ceiling(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-141">CEILING(expression)</span></span>

<span data-ttu-id="ece11-142">Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="ece11-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="ece11-143">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-143">**Arguments**</span></span>

<span data-ttu-id="ece11-144">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ece11-145">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-145">**Return Value**</span></span>

<span data-ttu-id="ece11-146">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ece11-147">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="ece11-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-148">COS(expression)</span></span>

<span data-ttu-id="ece11-149">Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="ece11-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="ece11-150">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-150">**Arguments**</span></span> 

<span data-ttu-id="ece11-151">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-152">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-152">**Return Value**</span></span> 

<span data-ttu-id="ece11-153">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-153">A `Double`.</span></span> 

<span data-ttu-id="ece11-154">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="ece11-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-155">COT(expression)</span></span>

<span data-ttu-id="ece11-156">Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="ece11-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="ece11-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-157">**Arguments**</span></span> 

<span data-ttu-id="ece11-158">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-159">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-159">**Return Value**</span></span> 

<span data-ttu-id="ece11-160">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-160">A `Double`.</span></span> 

<span data-ttu-id="ece11-161">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="ece11-162">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="ece11-162">DEGREES(radians)</span></span>

<span data-ttu-id="ece11-163">Restituisce l'angolo corrispondente in gradi.</span><span class="sxs-lookup"><span data-stu-id="ece11-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="ece11-164">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-164">**Arguments**</span></span> 

<span data-ttu-id="ece11-165">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ece11-166">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-166">**Return Value**</span></span> 

<span data-ttu-id="ece11-167">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ece11-168">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="ece11-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-169">EXP(expression)</span></span>

<span data-ttu-id="ece11-170">Calcola il valore esponenziale dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="ece11-171">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-171">**Arguments**</span></span> 

<span data-ttu-id="ece11-172">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-173">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-173">**Return Value**</span></span> 

<span data-ttu-id="ece11-174">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-174">A `Double`.</span></span> 

<span data-ttu-id="ece11-175">**Esempio** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="ece11-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="ece11-176">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-176">FLOOR(expression)</span></span>

<span data-ttu-id="ece11-177">Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="ece11-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="ece11-178">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-178">**Arguments**</span></span> 

<span data-ttu-id="ece11-179">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-180">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-180">**Return Value**</span></span> 

<span data-ttu-id="ece11-181">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-181">A `Double`.</span></span> 

<span data-ttu-id="ece11-182">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="ece11-183">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-183">LOG(expression)</span></span>

<span data-ttu-id="ece11-184">Calcola il logaritmo naturale dell'espressione `float` specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="ece11-185">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-185">**Arguments**</span></span> 

<span data-ttu-id="ece11-186">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-187">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-187">**Return Value**</span></span> 

<span data-ttu-id="ece11-188">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-188">A `Double`.</span></span> 

<span data-ttu-id="ece11-189">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="ece11-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-190">LOG10(expression)</span></span>

<span data-ttu-id="ece11-191">Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="ece11-192">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-192">**Arguments**</span></span> 

<span data-ttu-id="ece11-193">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-194">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-194">**Return Value**</span></span> 

<span data-ttu-id="ece11-195">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-195">A `Double`.</span></span> 

<span data-ttu-id="ece11-196">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="ece11-197">PI</span><span class="sxs-lookup"><span data-stu-id="ece11-197">PI()</span></span>

<span data-ttu-id="ece11-198">Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="ece11-199">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-199">**Return Value**</span></span> 

<span data-ttu-id="ece11-200">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-200">A `Double`.</span></span> 

<span data-ttu-id="ece11-201">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="ece11-202">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="ece11-203">Calcola il valore dell'espressione specificata elevato alla potenza indicata.</span><span class="sxs-lookup"><span data-stu-id="ece11-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="ece11-204">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="ece11-205">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="ece11-206">Oggetto `Double` che rappresenta la potenza a cui elevare il `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="ece11-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="ece11-207">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-207">**Return Value**</span></span> 

<span data-ttu-id="ece11-208">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="ece11-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="ece11-209">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="ece11-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-210">RADIANS(expression)</span></span>

<span data-ttu-id="ece11-211">Converte i gradi in radianti.</span><span class="sxs-lookup"><span data-stu-id="ece11-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="ece11-212">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-212">**Arguments**</span></span> 

<span data-ttu-id="ece11-213">`expression`: `Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ece11-214">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-214">**Return Value**</span></span> 

<span data-ttu-id="ece11-215">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ece11-216">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="ece11-217">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="ece11-217">RAND([seed])</span></span>

<span data-ttu-id="ece11-218">Restituisce un valore casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="ece11-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="ece11-219">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-219">**Arguments**</span></span> 

<span data-ttu-id="ece11-220">Il valore di inizializzazione come un `Int32`.</span><span class="sxs-lookup"><span data-stu-id="ece11-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="ece11-221">Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="ece11-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="ece11-222">Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ece11-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="ece11-223">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-223">**Return Value**</span></span> 

<span data-ttu-id="ece11-224">Valore `Double` casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="ece11-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="ece11-225">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="ece11-226">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="ece11-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="ece11-227">Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="ece11-228">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="ece11-229">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="ece11-230">Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="ece11-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="ece11-231">Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="ece11-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="ece11-232">Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="ece11-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="ece11-233">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ece11-233">Optional.</span></span> <span data-ttu-id="ece11-234">Un `Int32` che rappresenta il tipo di operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ece11-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="ece11-235">Quando viene omesso oppure ha un valore pari a 0 (impostazione predefinita), `numeric_expression` viene arrotondato.</span><span class="sxs-lookup"><span data-stu-id="ece11-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="ece11-236">Quando un valore diverso da è specificato 0, `numeric_expression` viene troncato.</span><span class="sxs-lookup"><span data-stu-id="ece11-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="ece11-237">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-237">**Return Value**</span></span> 

<span data-ttu-id="ece11-238">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="ece11-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="ece11-239">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="ece11-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-240">SIGN(expression)</span></span> 

<span data-ttu-id="ece11-241">Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="ece11-242">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-242">**Arguments**</span></span> 

<span data-ttu-id="ece11-243">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="ece11-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="ece11-244">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-244">**Return Value**</span></span> 

<span data-ttu-id="ece11-245">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ece11-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ece11-246">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="ece11-247">Sin(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-247">SIN(expression)</span></span>

<span data-ttu-id="ece11-248">Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="ece11-249">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-249">**Arguments**</span></span> 

<span data-ttu-id="ece11-250">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-251">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-251">**Return Value**</span></span> 

<span data-ttu-id="ece11-252">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-252">A `Double`.</span></span> 

<span data-ttu-id="ece11-253">**Esempio** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="ece11-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="ece11-254">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-254">SQRT(expression)</span></span>

<span data-ttu-id="ece11-255">Restituisce la radice quadrata dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="ece11-256">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-256">**Arguments**</span></span> 

<span data-ttu-id="ece11-257">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-258">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-258">**Return Value**</span></span> 

<span data-ttu-id="ece11-259">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-259">A `Double`.</span></span> 

<span data-ttu-id="ece11-260">**Esempio** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="ece11-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="ece11-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-261">SQUARE(expression)</span></span>

<span data-ttu-id="ece11-262">Restituisce la radice dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="ece11-263">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-263">**Arguments**</span></span> 

<span data-ttu-id="ece11-264">`expression`: valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ece11-265">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-265">**Return Value**</span></span> 

<span data-ttu-id="ece11-266">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ece11-266">A `Double`.</span></span> 

<span data-ttu-id="ece11-267">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="ece11-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ece11-268">TAN(expression)</span></span>

<span data-ttu-id="ece11-269">Calcola la tangente di un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ece11-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="ece11-270">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ece11-270">**Arguments**</span></span> 

<span data-ttu-id="ece11-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="ece11-271">`expression`: `Double`</span></span> 

<span data-ttu-id="ece11-272">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ece11-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="ece11-273">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ece11-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="ece11-274">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ece11-274">See also</span></span>

<span data-ttu-id="ece11-275">Per altre informazioni sulle funzioni matematiche supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="ece11-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="ece11-276">**SQL Server 2005:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="ece11-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="ece11-277">**SQL Server 2008:** [funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="ece11-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="ece11-278">**SQL Server 2012 e versioni successive:** [funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="ece11-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="ece11-279">SqlClient per funzioni Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ece11-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
