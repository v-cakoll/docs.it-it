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
ms.openlocfilehash: 87faa623f5b145eec8b88e350fce4171125324dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596808"
---
# <a name="derived-math-functions-visual-basic"></a>Funzioni matematiche derivate (Visual Basic)
La tabella seguente illustra le funzioni matematiche non intrinseche che possono essere derivate da funzioni matematiche intrinseche del <xref:System.Math?displayProperty=nameWithType> oggetto. È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al progetto o al file.  
  
|Funzione|Espressione equivalente|  
|--------------|-------------------------|  
|Secante (Sec(x))|1 / cos (x)|  
|Cosecante (Csc(x))|1 / SEN (x)|  
|Cotangente (Ctan(x))|1 / tan (x)|  
|Seno inverso (Asin(x))|Atan (x / Sqrt (-x * x + 1))|  
|Coseno inverso (Acos(x))|Atan (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|Secante inversa (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))|  
|Cosecante (Acsc(x))|Atan(Sign(x) / Sqrt (x * x – 1))|  
|Funzione inversa della cotangente (Acot(x))|2 * Atan(1) - ARCTAN (x)|  
|Seno iperbolico (Sinh(x))|(EXP (x) – Exp(-x)) / 2|  
|Coseno iperbolico (Cosh(x))|(EXP (x) + Exp(-x)) / 2|  
|Tangente iperbolica (Tanh(x))|(EXP (x) – Exp(-x)) / (EXP (x) + Exp(-x))|  
|Secante iperbolica (Sech(x))|2 / (EXP (x) + Exp(-x))|  
|Cosecante iperbolica (Csch(x))|2 / (EXP (x) – Exp(-x))|  
|Cotangente iperbolica (Coth(x))|(EXP (x) + Exp(-x)) / (EXP (x) – Exp(-x))|  
|Seno iperbolico inverso (Asinh(x))|Log (x + Sqrt (x * x + 1))|  
|Coseno iperbolico inverso (Acosh(x))|Log (x + Sqrt (x * x – 1))|  
|Tangente iperbolica inversa (Atanh(x))|Log ((1 + x) / (1 – x)) / 2|  
|Secante iperbolica (AsecH(x))|Log ((Sqrt (-x * x + 1) + 1) / x)|  
|Cosecante iperbolica (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Funzione inversa della cotangente iperbolica (Acoth(x))|Log ((x + 1) / (x-1)) / 2|  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni matematiche](../../../visual-basic/language-reference/functions/math-functions.md)
