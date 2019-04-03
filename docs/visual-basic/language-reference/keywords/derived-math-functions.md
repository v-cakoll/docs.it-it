---
title: Funzioni matematiche derivate (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836584"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="f88fc-102">Funzioni matematiche derivate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f88fc-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="f88fc-103">Nella seguente tabella sono funzioni matematiche non intrinseco che possono essere derivate da funzioni matematiche intrinseco del <xref:System.Math?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f88fc-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="f88fc-104">È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al progetto o di file.</span><span class="sxs-lookup"><span data-stu-id="f88fc-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="f88fc-105">Funzione</span><span class="sxs-lookup"><span data-stu-id="f88fc-105">Function</span></span>|<span data-ttu-id="f88fc-106">Espressione equivalente</span><span class="sxs-lookup"><span data-stu-id="f88fc-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="f88fc-107">Secante (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-107">Secant (Sec(x))</span></span>|<span data-ttu-id="f88fc-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="f88fc-109">Cosecante (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="f88fc-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="f88fc-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="f88fc-112">1 / tan (x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="f88fc-113">Seno inverso (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="f88fc-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="f88fc-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="f88fc-115">Coseno inverso (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="f88fc-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="f88fc-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="f88fc-117">Secante inversa (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="f88fc-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="f88fc-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f88fc-119">Cosecante (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="f88fc-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="f88fc-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f88fc-121">Funzione inversa della cotangente (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="f88fc-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="f88fc-123">Seno iperbolico (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="f88fc-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="f88fc-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="f88fc-125">Coseno iperbolico (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="f88fc-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="f88fc-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="f88fc-127">Tangente iperbolica (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="f88fc-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="f88fc-129">Secante iperbolica (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="f88fc-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="f88fc-131">Cosecante iperbolica (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="f88fc-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="f88fc-133">Cotangente iperbolica (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="f88fc-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="f88fc-135">Seno iperbolico inverso (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="f88fc-136">Log (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="f88fc-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="f88fc-137">Coseno iperbolico inverso (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="f88fc-138">Log (x + Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="f88fc-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f88fc-139">Tangente iperbolica inversa (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="f88fc-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="f88fc-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="f88fc-141">Secante iperbolica (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="f88fc-142">Log ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="f88fc-143">Cosecante iperbolica (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="f88fc-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="f88fc-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="f88fc-145">Funzione inversa della cotangente iperbolica (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="f88fc-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="f88fc-146">Log ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="f88fc-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f88fc-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f88fc-147">See also</span></span>

- [<span data-ttu-id="f88fc-148">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="f88fc-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
