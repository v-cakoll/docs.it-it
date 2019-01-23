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
ms.openlocfilehash: 1273871faf65afdd1a894c03f13a2c93507c1b13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505861"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="342a6-102">Funzioni matematiche derivate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="342a6-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="342a6-103">Nella seguente tabella sono funzioni matematiche non intrinseco che possono essere derivate da funzioni matematiche intrinseco del <xref:System.Math?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="342a6-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="342a6-104">È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al progetto o di file.</span><span class="sxs-lookup"><span data-stu-id="342a6-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="342a6-105">Funzione</span><span class="sxs-lookup"><span data-stu-id="342a6-105">Function</span></span>|<span data-ttu-id="342a6-106">Espressione equivalente</span><span class="sxs-lookup"><span data-stu-id="342a6-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="342a6-107">Secante (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-107">Secant (Sec(x))</span></span>|<span data-ttu-id="342a6-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="342a6-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="342a6-109">Cosecante (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="342a6-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="342a6-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="342a6-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="342a6-112">1 / tan (x)</span><span class="sxs-lookup"><span data-stu-id="342a6-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="342a6-113">Seno inverso (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="342a6-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="342a6-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="342a6-115">Coseno inverso (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="342a6-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="342a6-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="342a6-117">Secante inversa (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="342a6-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="342a6-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="342a6-119">Cosecante (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="342a6-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="342a6-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="342a6-121">Funzione inversa della cotangente (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="342a6-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="342a6-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="342a6-123">Seno iperbolico (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="342a6-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="342a6-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="342a6-125">Coseno iperbolico (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="342a6-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="342a6-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="342a6-127">Tangente iperbolica (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="342a6-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="342a6-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="342a6-129">Secante iperbolica (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="342a6-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="342a6-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="342a6-131">Cosecante iperbolica (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="342a6-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="342a6-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="342a6-133">Cotangente iperbolica (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="342a6-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="342a6-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="342a6-135">Seno iperbolico inverso (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="342a6-136">Log (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="342a6-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="342a6-137">Coseno iperbolico inverso (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="342a6-138">Log (x + Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="342a6-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="342a6-139">Tangente iperbolica inversa (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="342a6-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="342a6-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="342a6-141">Secante iperbolica (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="342a6-142">Log ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="342a6-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="342a6-143">Cosecante iperbolica (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="342a6-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="342a6-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="342a6-145">Funzione inversa della cotangente iperbolica (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="342a6-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="342a6-146">Log ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="342a6-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="342a6-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="342a6-147">See also</span></span>
- [<span data-ttu-id="342a6-148">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="342a6-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
