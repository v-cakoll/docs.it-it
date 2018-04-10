---
title: Operatore -= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 443f0d717288a491838d23eaa63218150bd346d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-c-reference"></a>Operatore -= (Riferimenti per C#)
Operatore di assegnazione di sottrazione.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `-=`, ad esempio  
  
```  
x -= y  
```  
  
 equivale a  
  
```  
x = x - y  
```  
  
 con la differenza che `x` viene valutato una sola volta. Il significato dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) dipende dai tipi di `x` e `y` (sottrazione per gli operandi numerici, rimozione del delegato per gli operandi delegati e così via).  
  
 L'operatore `-=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 L'operatore -= viene anche usato in C# per annullare la sottoscrizione a un evento. Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
