---
title: Operatore || (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 58e5fd72a3748e7af0894093fc461c4efb543608
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925540"
---
# <a name="-operator-c-reference"></a>Operatore || (Riferimenti per C#)
L'operatore OR condizionale (`||`) esegue un'operazione OR logica sui propri operandi `bool`. Se il primo operando restituisce `true`, il secondo operando non viene valutato. Se il primo operando restituisce `false`, il secondo operando determina se l'espressione OR nel suo complesso restituisce `true` o `false`.  
  
## <a name="remarks"></a>Note  
 L'operazione  
  
```csharp  
x || y  
```  
  
 corrisponde all'operazione  
  
```csharp  
x | y  
```  
  
 tuttavia se `x` è `true`, `y` non viene valutato, perché l'operazione OR è `true` indipendentemente dal valore di `y`. Questa concetto è noto come "valutazione a corto circuito".  
  
 L'operatore OR condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti l'espressione che usa `||` valuta solo il primo operando. L'espressione che usa `|` valuta entrambi gli operandi. Nel secondo esempio, si verifica un'eccezione in fase di esecuzione se vengono valutati entrambi gli operandi.  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
