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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836584"
---
# <a name="derived-math-functions-visual-basic"></a>Funzioni matematiche derivate (Visual Basic)
Nella seguente tabella sono funzioni matematiche non intrinseco che possono essere derivate da funzioni matematiche intrinseco del <xref:System.Math?displayProperty=nameWithType> oggetto. È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al progetto o di file.  
  
|Funzione|Espressione equivalente|  
|--------------|-------------------------|  
|Secante (Sec(x))|1 / Cos(x)|  
|Cosecante (Csc(x))|1 / Sin(x)|  
|Cotangent (Ctan(x))|1 / tan (x)|  
|Seno inverso (Asin(x))|Atan(x / Sqrt(-x * x + 1))|  
|Coseno inverso (Acos(x))|Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)|  
|Secante inversa (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))|  
|Cosecante (Acsc(x))|Atan(Sign(x) / Sqrt(x * x – 1))|  
|Funzione inversa della cotangente (Acot(x))|2 * Atan(1) - Atan(x)|  
|Seno iperbolico (Sinh(x))|(Exp(x) – Exp(-x)) / 2|  
|Coseno iperbolico (Cosh(x))|(Exp(x) + Exp(-x)) / 2|  
|Tangente iperbolica (Tanh(x))|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|Secante iperbolica (Sech(x))|2 / (Exp(x) + Exp(-x))|  
|Cosecante iperbolica (Csch(x))|2 / (Exp(x) – Exp(-x))|  
|Cotangente iperbolica (Coth(x))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|Seno iperbolico inverso (Asinh(x))|Log (x + Sqrt (x * x + 1))|  
|Coseno iperbolico inverso (Acosh(x))|Log (x + Sqrt (x * x-1))|  
|Tangente iperbolica inversa (Atanh(x))|Log((1 + x) / (1 – x)) / 2|  
|Secante iperbolica (AsecH(x))|Log ((Sqrt (-x * x + 1) + 1) / x)|  
|Cosecante iperbolica (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Funzione inversa della cotangente iperbolica (Acoth(x))|Log ((x + 1) / (x – 1)) / 2|  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni matematiche](../../../visual-basic/language-reference/functions/math-functions.md)
