---
title: Funzioni matematiche
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: b6f248382f069df59a55e85e9a764b0df700fb26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780315"
---
# <a name="mathematical-functions"></a><span data-ttu-id="ad1bf-102">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="ad1bf-102">Mathematical Functions</span></span>

<span data-ttu-id="ad1bf-103">Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni matematiche che eseguono calcoli in valori di input forniti come argomenti e restituiscono un risultato di tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="ad1bf-104">Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="ad1bf-105">Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="ad1bf-106">La tabella seguente descrive le funzioni matematiche SqlClient.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="ad1bf-107">Abs(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-107">ABS(expression)</span></span>

<span data-ttu-id="ad1bf-108">Esegue la funzione relativa al valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-108">Performs the absolute value function.</span></span>

<span data-ttu-id="ad1bf-109">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-109">**Arguments**</span></span>

<span data-ttu-id="ad1bf-110">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ad1bf-111">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-111">**Return Value**</span></span>

<span data-ttu-id="ad1bf-112">Valore assoluto dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="ad1bf-113">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="ad1bf-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-114">ACOS(expression)</span></span>

<span data-ttu-id="ad1bf-115">Restituisce il valore dell'arcocoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="ad1bf-116">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-116">**Arguments**</span></span>

<span data-ttu-id="ad1bf-117">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="ad1bf-118">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-118">**Return Value**</span></span>

<span data-ttu-id="ad1bf-119">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-119">A `Double`.</span></span>

<span data-ttu-id="ad1bf-120">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="ad1bf-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-121">ASIN(expression)</span></span>

<span data-ttu-id="ad1bf-122">Restituisce il valore dell'arcoseno dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="ad1bf-123">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-123">**Arguments**</span></span>

<span data-ttu-id="ad1bf-124">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="ad1bf-125">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-125">**Return Value**</span></span>

<span data-ttu-id="ad1bf-126">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-126">A `Double`.</span></span>

<span data-ttu-id="ad1bf-127">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="ad1bf-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-128">ATAN(expression)</span></span>

<span data-ttu-id="ad1bf-129">Restituisce il valore dell'arcotangente dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="ad1bf-130">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-130">**Arguments**</span></span>

<span data-ttu-id="ad1bf-131">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="ad1bf-132">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-132">**Return Value**</span></span>

<span data-ttu-id="ad1bf-133">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-133">A `Double`.</span></span>

<span data-ttu-id="ad1bf-134">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="ad1bf-135">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="ad1bf-136">Restituisce l'angolo, in radianti, la cui tangente è compresa tra le due espressioni numeriche specificate.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="ad1bf-137">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-137">**Arguments**</span></span>

<span data-ttu-id="ad1bf-138">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="ad1bf-139">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-139">**Return Value**</span></span>

<span data-ttu-id="ad1bf-140">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-140">A `Double`.</span></span>

<span data-ttu-id="ad1bf-141">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="ad1bf-142">Ceiling(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-142">CEILING(expression)</span></span>

<span data-ttu-id="ad1bf-143">Converte l'espressione specificata nel valore Integer più piccolo che è maggiore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="ad1bf-144">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-144">**Arguments**</span></span>

<span data-ttu-id="ad1bf-145">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ad1bf-146">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-146">**Return Value**</span></span>

<span data-ttu-id="ad1bf-147">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="ad1bf-148">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="ad1bf-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-149">COS(expression)</span></span>

<span data-ttu-id="ad1bf-150">Calcola il coseno trigonometrico dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="ad1bf-151">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-151">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-152">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-153">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-153">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-154">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-154">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-155">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="ad1bf-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-156">COT(expression)</span></span>

<span data-ttu-id="ad1bf-157">Calcola la cotangente trigonometrica dell'angolo specificato espresso in radianti.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="ad1bf-158">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-158">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-159">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-160">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-160">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-161">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-161">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-162">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="ad1bf-163">DEGREES(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-163">DEGREES(radians)</span></span>

<span data-ttu-id="ad1bf-164">Restituisce l'angolo corrispondente in gradi.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="ad1bf-165">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-165">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-166">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ad1bf-167">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-167">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-168">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ad1bf-169">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="ad1bf-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-170">EXP(expression)</span></span>

<span data-ttu-id="ad1bf-171">Calcola il valore esponenziale dell'espressione numerica specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="ad1bf-172">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-172">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-173">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-174">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-174">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-175">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-175">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-176">**Esempio** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="ad1bf-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="ad1bf-177">FLOOR(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-177">FLOOR(expression)</span></span>

<span data-ttu-id="ad1bf-178">Converte l'espressione specificata nel valore Integer più grande che risulta minore o uguale a tale espressione.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="ad1bf-179">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-179">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-180">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-181">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-181">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-182">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-182">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-183">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="ad1bf-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-184">LOG(expression)</span></span>

<span data-ttu-id="ad1bf-185">Calcola il logaritmo naturale dell'espressione `float` specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="ad1bf-186">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-186">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-187">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-188">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-188">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-189">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-189">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-190">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="ad1bf-191">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-191">LOG10(expression)</span></span>

<span data-ttu-id="ad1bf-192">Restituisce il logaritmo in base 10 dell'espressione `Double` specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="ad1bf-193">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-193">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-194">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-195">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-195">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-196">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-196">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-197">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="ad1bf-198">PI()</span><span class="sxs-lookup"><span data-stu-id="ad1bf-198">PI()</span></span>

<span data-ttu-id="ad1bf-199">Restituisce il valore costante di pi greco sotto forma di oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="ad1bf-200">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-200">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-201">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-201">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-202">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="ad1bf-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="ad1bf-204">Calcola il valore dell'espressione specificata elevato alla potenza indicata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="ad1bf-205">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="ad1bf-206">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="ad1bf-207">Oggetto `Double` che rappresenta la potenza a cui elevare il `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="ad1bf-208">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-208">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-209">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="ad1bf-210">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="ad1bf-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-211">RADIANS(expression)</span></span>

<span data-ttu-id="ad1bf-212">Converte i gradi in radianti.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="ad1bf-213">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-213">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-214">`expression`: Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ad1bf-215">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-215">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-216">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ad1bf-217">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="ad1bf-218">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="ad1bf-218">RAND([seed])</span></span>

<span data-ttu-id="ad1bf-219">Restituisce un valore casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="ad1bf-220">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-220">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-221">Il valore di inizializzazione come un `Int32`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="ad1bf-222">Se non è specificato, il Motore di database di SQL Server assegna un valore di inizializzazione in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="ad1bf-223">Per un valore di inizializzazione specificato, il risultato restituito è sempre lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="ad1bf-224">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-224">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-225">Valore `Double` casuale compreso tra 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="ad1bf-226">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="ad1bf-227">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="ad1bf-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="ad1bf-228">Restituisce un'espressione numerica, arrotondata alla precisione o alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="ad1bf-229">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="ad1bf-230">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="ad1bf-231">Oggetto `Int32` che rappresenta la precisione a cui arrotondare `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="ad1bf-232">Quando `length` è un numero positivo, l'oggetto `numeric_expression` viene arrotondato al numero di posizioni decimali specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="ad1bf-233">Quando `length` è un numero negativo, l'oggetto `numeric_expression` viene arrotondato a sinistra del separatore decimale, in base a quanto specificato da `length`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="ad1bf-234">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-234">Optional.</span></span> <span data-ttu-id="ad1bf-235">Un `Int32` che rappresenta il tipo di operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="ad1bf-236">Quando viene omesso oppure ha un valore pari a 0 (impostazione predefinita), `numeric_expression` viene arrotondato.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="ad1bf-237">Quando un valore diverso da è specificato 0, `numeric_expression` viene troncato.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="ad1bf-238">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-238">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-239">Valore dell'oggetto `numeric_expression` specificato alla potenza `power_expression` indicata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="ad1bf-240">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="ad1bf-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-241">SIGN(expression)</span></span> 

<span data-ttu-id="ad1bf-242">Restituisce il segno positivo (+1), zero (0) o il segno negativo (-1) dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="ad1bf-243">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-243">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="ad1bf-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="ad1bf-245">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-245">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-246">Un' `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="ad1bf-247">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="ad1bf-248">Sin(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-248">SIN(expression)</span></span>

<span data-ttu-id="ad1bf-249">Calcola il seno trigonometrico dell'angolo specificato, espresso in radianti, e restituisce un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="ad1bf-250">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-250">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-251">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-252">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-252">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-253">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-253">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-254">**Esempio** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="ad1bf-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="ad1bf-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-255">SQRT(expression)</span></span>

<span data-ttu-id="ad1bf-256">Restituisce la radice quadrata dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="ad1bf-257">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-257">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-258">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-259">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-259">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-260">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-260">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-261">**Esempio** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="ad1bf-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="ad1bf-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-262">SQUARE(expression)</span></span>

<span data-ttu-id="ad1bf-263">Restituisce la radice dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="ad1bf-264">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-264">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-265">`expression`: OGGETTO `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="ad1bf-266">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-266">**Return Value**</span></span> 

<span data-ttu-id="ad1bf-267">Oggetto `Double`.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-267">A `Double`.</span></span> 

<span data-ttu-id="ad1bf-268">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="ad1bf-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-269">TAN(expression)</span></span>

<span data-ttu-id="ad1bf-270">Calcola la tangente di un'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ad1bf-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="ad1bf-271">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-271">**Arguments**</span></span> 

<span data-ttu-id="ad1bf-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="ad1bf-272">`expression`: `Double`</span></span> 

<span data-ttu-id="ad1bf-273">**Valore restituito**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="ad1bf-274">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="ad1bf-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="ad1bf-275">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad1bf-275">See also</span></span>

<span data-ttu-id="ad1bf-276">Per altre informazioni sulle funzioni matematiche supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:</span><span class="sxs-lookup"><span data-stu-id="ad1bf-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="ad1bf-277">**SQL Server 2005:** [Funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="ad1bf-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>
- <span data-ttu-id="ad1bf-278">**SQL Server 2008:** [Funzioni matematiche (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="ad1bf-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>
- <span data-ttu-id="ad1bf-279">**SQL Server 2012 e versioni successive:** [Funzioni matematiche (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="ad1bf-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>

- [<span data-ttu-id="ad1bf-280">SqlClient per funzioni Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ad1bf-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
