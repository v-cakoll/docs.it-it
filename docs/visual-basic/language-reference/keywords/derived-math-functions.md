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
# <a name="derived-math-functions-visual-basic"></a>Funzioni matematiche derivate (Visual Basic)
Nella tabella seguente vengono illustrate le funzioni matematiche non intrinseche che possono essere derivate dalle funzioni matematiche intrinseche dell'oggetto <xref:System.Math?displayProperty=nameWithType>. È possibile accedere alle funzioni matematiche intrinseche aggiungendo `Imports System.Math` al file o al progetto.  
  
|Funzione|Equivalenti derivati|  
|--------------|-------------------------|  
|Secante (sec (x))|1/cos (x)|  
|Cosecator (CSC (x))|1/sin (x)|  
|Cotangente (CTAN (x))|1/tan (x)|  
|Seno inverso (Asin (x))|Atan (x/sqrt (-x * x + 1))|  
|Coseno inverso (ARCCOS (x))|Atan (-x/sqrt (-x * x + 1)) + 2 \* Atan (1)|  
|Secante inversa (ASEC (x))|2 * Atan (1) – Atan (Sign (x)/sqrt (x \* x-1))|  
|Cosecante inverso (ACSC (x))|Atan (Sign (x)/sqrt (x * x-1))|  
|Cotangente inversa (acot (x))|2 * Atan (1)-Atan (x)|  
|Seno iperbolico ((x))|(Exp(x) – Exp(-x)) / 2|  
|Coseno iperbolico (cosh (x))|(Exp(x) + Exp(-x)) / 2|  
|Tangente iperbolica (tanh (x))|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|Secante iperbolica (sech (x))|2 / (Exp(x) + Exp(-x))|  
|Cosecante iperbolica (csch (x))|2 / (Exp(x) – Exp(-x))|  
|Cotangente iperbolica (coth (x))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|Seno iperbolico inverso (asinh (x))|Log (x + sqrt (x * x + 1))|  
|Coseno iperbolico inverso (acosh (x))|Log (x + sqrt (x * x-1))|  
|Tangente iperbolica inversa (atanh (x))|Log ((1 + x)/(1 – x))/2|  
|Secante iperbolica inversa (AsecH (x))|Log ((sqrt (-x * x + 1) + 1)/x)|  
|Cosecante iperbolica inversa (Acsch (x))|Log ((Sign (x) * sqrt (x \* x + 1) + 1)/x)|  
|Cotangente iperbolica inversa (Acoth (x))|Log ((x + 1)/(x-1))/2|  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni matematiche](../../../visual-basic/language-reference/functions/math-functions.md)
