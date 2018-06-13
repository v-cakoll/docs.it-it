---
title: Operatore += (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bcd56acad8e2b08585e5ae60f1c3cf8183b5664a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171879"
---
# <a name="-operator-c-reference"></a>Operatore += (Riferimenti per C#)
Operatore di assegnazione di addizione.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `+=`, ad esempio  
  
```csharp  
x += y  
```  
  
 equivale a  
  
```csharp  
x = x + y  
```  
  
 con la differenza che `x` viene valutato una sola volta. Il significato dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) dipende dai tipi di `x` e `y` (addizione per gli operandi numerici, concatenazione per gli operandi stringa e così via).  
  
 L'operatore `+=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 L'operatore `+=` viene usato anche per specificare un metodo che verrà chiamato in risposta a un evento. I metodi di questo tipo sono chiamati gestori eventi. L'uso dell'operatore `+=` in questo contesto è detto *sottoscrizione di un evento*. Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) e [Delegati](../../../csharp/programming-guide/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
