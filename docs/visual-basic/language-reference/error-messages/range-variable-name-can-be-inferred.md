---
title: Il nome di variabile di intervallo può essere dedotto solo da un nome semplice o completo senza argomenti
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: f448f34dc5909b9128fc700abab5b4f00e911edf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701019"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Il nome di variabile di intervallo può essere dedotto solo da un nome semplice o completo senza argomenti
Un elemento di programmazione che accetta uno o più argomenti è incluso in una query LINQ. Il compilatore non è in grado di dedurre una variabile di intervallo da tale elemento di programmazione.  
  
 **ID errore:** BC36599  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Specificare un nome di variabile esplicito per l'elemento di programmazione, come illustrato nel codice seguente:  
  
```vb  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
