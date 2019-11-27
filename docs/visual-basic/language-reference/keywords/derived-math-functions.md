---
title: Funzioni matematiche derivate
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
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349844"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="35701-102">Funzioni matematiche derivate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35701-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="35701-103">Nella tabella seguente vengono illustrate le funzioni matematiche non intrinseche che possono essere derivate dalle funzioni matematiche intrinseche dell'oggetto <xref:System.Math?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35701-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="35701-104">È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al file o al progetto.</span><span class="sxs-lookup"><span data-stu-id="35701-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="35701-105">Funzione</span><span class="sxs-lookup"><span data-stu-id="35701-105">Function</span></span>|<span data-ttu-id="35701-106">Equivalenti derivati</span><span class="sxs-lookup"><span data-stu-id="35701-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="35701-107">Secante (sec (x))</span><span class="sxs-lookup"><span data-stu-id="35701-107">Secant (Sec(x))</span></span>|<span data-ttu-id="35701-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="35701-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="35701-109">Cosecator (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="35701-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="35701-110">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="35701-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="35701-111">Cotangente (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="35701-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="35701-112">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="35701-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="35701-113">Seno inverso (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="35701-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="35701-114">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="35701-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="35701-115">Coseno inverso (ARCCOS (x))</span><span class="sxs-lookup"><span data-stu-id="35701-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="35701-116">Atan (-x/sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="35701-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="35701-117">Secante inversa (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="35701-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="35701-118">2 \* Atan (1) – Atan (Sign (x)/sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="35701-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="35701-119">Cosecante inverso (ACSC (x))</span><span class="sxs-lookup"><span data-stu-id="35701-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="35701-120">Atan (Sign (x)/sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="35701-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="35701-121">Cotangente inversa (acot (x))</span><span class="sxs-lookup"><span data-stu-id="35701-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="35701-122">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="35701-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="35701-123">Seno iperbolico ((x))</span><span class="sxs-lookup"><span data-stu-id="35701-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="35701-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="35701-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="35701-125">Coseno iperbolico (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="35701-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="35701-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="35701-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="35701-127">Tangente iperbolica (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="35701-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="35701-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="35701-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="35701-129">Secante iperbolica (sech (x))</span><span class="sxs-lookup"><span data-stu-id="35701-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="35701-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="35701-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="35701-131">Cosecante iperbolica (csch (x))</span><span class="sxs-lookup"><span data-stu-id="35701-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="35701-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="35701-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="35701-133">Cotangente iperbolica (coth (x))</span><span class="sxs-lookup"><span data-stu-id="35701-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="35701-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="35701-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="35701-135">Seno iperbolico inverso (asinh (x))</span><span class="sxs-lookup"><span data-stu-id="35701-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="35701-136">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="35701-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="35701-137">Coseno iperbolico inverso (acosh (x))</span><span class="sxs-lookup"><span data-stu-id="35701-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="35701-138">Log (x + sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="35701-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="35701-139">Tangente iperbolica inversa (atanh (x))</span><span class="sxs-lookup"><span data-stu-id="35701-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="35701-140">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="35701-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="35701-141">Secante iperbolica inversa (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="35701-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="35701-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="35701-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="35701-143">Cosecante iperbolica inversa (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="35701-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="35701-144">Log ((Sign (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="35701-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="35701-145">Cotangente iperbolica inversa (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="35701-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="35701-146">Log ((x + 1)/(x-1))/2</span><span class="sxs-lookup"><span data-stu-id="35701-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35701-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35701-147">See also</span></span>

- [<span data-ttu-id="35701-148">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="35701-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
