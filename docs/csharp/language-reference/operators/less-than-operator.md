---
title: Operatore &lt; (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: eceb6214e4e625aa71e12788d5dd5e8324c75443
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270231"
---
# <a name="lt-operator-c-reference"></a>Operatore &lt; (Riferimenti per C#)
Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore di" (`<`), che restituisce `true` se il primo operando è minore del secondo, in caso contrario `false`.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Se `<` è sottoposto a overload, deve esserlo anche [>](../../../csharp/language-reference/operators/greater-than-operator.md). Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
