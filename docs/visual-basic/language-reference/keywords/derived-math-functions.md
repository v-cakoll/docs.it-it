---
title: Funzioni matematiche derivate (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5816fa4c8c384eca116fa1512950a3588c6e3392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="e39c3-102">Funzioni matematiche derivate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e39c3-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="e39c3-103">La tabella seguente illustra le funzioni matematiche non intrinseche che possono essere derivate da funzioni matematiche intrinseche del <xref:System.Math?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e39c3-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="e39c3-104">È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al progetto o al file.</span><span class="sxs-lookup"><span data-stu-id="e39c3-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="e39c3-105">Funzione</span><span class="sxs-lookup"><span data-stu-id="e39c3-105">Function</span></span>|<span data-ttu-id="e39c3-106">Espressione equivalente</span><span class="sxs-lookup"><span data-stu-id="e39c3-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="e39c3-107">Secante (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-107">Secant (Sec(x))</span></span>|<span data-ttu-id="e39c3-108">1 / cos (x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="e39c3-109">Cosecante (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="e39c3-110">1 / SEN (x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="e39c3-111">Cotangente (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="e39c3-112">1 / tan (x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="e39c3-113">Seno inverso (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="e39c3-114">Atan (x / Sqrt (-x * x + 1))</span><span class="sxs-lookup"><span data-stu-id="e39c3-114">Atan(x / Sqrt(-x * x + 1))</span></span>|  
|<span data-ttu-id="e39c3-115">Coseno inverso (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="e39c3-116">Atan (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="e39c3-116">Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="e39c3-117">Secante inversa (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="e39c3-118">2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="e39c3-118">2 * Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="e39c3-119">Cosecante (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="e39c3-120">Atan(Sign(x) / Sqrt (x * x – 1))</span><span class="sxs-lookup"><span data-stu-id="e39c3-120">Atan(Sign(x) / Sqrt(x * x – 1))</span></span>|  
|<span data-ttu-id="e39c3-121">Funzione inversa della cotangente (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="e39c3-122">2 * Atan(1) - ARCTAN (x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-122">2 * Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="e39c3-123">Seno iperbolico (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="e39c3-124">(EXP (x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="e39c3-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="e39c3-125">Coseno iperbolico (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="e39c3-126">(EXP (x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="e39c3-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="e39c3-127">Tangente iperbolica (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="e39c3-128">(EXP (x) – Exp(-x)) / (EXP (x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="e39c3-129">Secante iperbolica (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="e39c3-130">2 / (EXP (x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="e39c3-131">Cosecante iperbolica (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="e39c3-132">2 / (EXP (x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="e39c3-133">Cotangente iperbolica (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="e39c3-134">(EXP (x) + Exp(-x)) / (EXP (x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="e39c3-135">Seno iperbolico inverso (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="e39c3-136">Log (x + Sqrt (x * x + 1))</span><span class="sxs-lookup"><span data-stu-id="e39c3-136">Log(x + Sqrt(x * x + 1))</span></span>|  
|<span data-ttu-id="e39c3-137">Coseno iperbolico inverso (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="e39c3-138">Log (x + Sqrt (x * x – 1))</span><span class="sxs-lookup"><span data-stu-id="e39c3-138">Log(x + Sqrt(x * x – 1))</span></span>|  
|<span data-ttu-id="e39c3-139">Tangente iperbolica inversa (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="e39c3-140">Log ((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="e39c3-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="e39c3-141">Secante iperbolica (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="e39c3-142">Log ((Sqrt (-x * x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-142">Log((Sqrt(-x * x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="e39c3-143">Cosecante iperbolica (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="e39c3-144">Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="e39c3-144">Log((Sign(x) * Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="e39c3-145">Funzione inversa della cotangente iperbolica (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="e39c3-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="e39c3-146">Log ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="e39c3-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e39c3-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e39c3-147">See Also</span></span>  
 [<span data-ttu-id="e39c3-148">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="e39c3-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
