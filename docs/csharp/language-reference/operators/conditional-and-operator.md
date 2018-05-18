---
title: '&amp;&amp; Operatore (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 86508c6eeb2998c6f202608f9204b72b60786e4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp; Operatore (Riferimenti per C#)
L'operatore AND condizionale (`&&`) esegue un AND logico sugli operandi `bool`, ma valuta il secondo operando solo se necessario.  
  
## <a name="remarks"></a>Note  
 L'operazione  
  
```  
x && y  
```  
  
 corrisponde all'operazione  
  
```  
x & y  
```  
  
 tuttavia se `x` è `false`, `y` non viene valutato, poiché il risultato dell'operazione AND sarà `false` indipendentemente dal valore di `y`. Questa condizione è denominata "valutazione short circuit".  
  
 L'operatore AND condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente l'espressione condizionale nella seconda istruzione `if` valuta solo il primo operando, perché l'operando restituisce `false`.  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
