---
title: ?? Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8fa751654acaf5939fb8f8068c7323e365f7bdab
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="-operator-c-reference"></a>?? Operatore (Riferimenti per C#)
L'operatore `??` viene chiamato operatore null-coalescing.  Restituisce l'operando sinistro se non è Null. In caso contrario, restituisce l'operando destro.  
  
## <a name="remarks"></a>Note  
 Un tipo nullable può rappresentare un valore dal dominio del tipo oppure il valore può essere indefinito, nel qual caso è Null. È possibile usare l'espressività sintattica dell'operatore `??` per restituire un valore appropriato (l'operando destro) quando l'operando sinistro è un tipo nullable il cui valore è Null. Se si tenta di assegnare un tipo di valore nullable a un tipo non nullable senza utilizzare l'operatore `??`, verrà generato un errore in fase di compilazione. Se si utilizza un cast e il tipo di valore nullable non è attualmente definito, verrà generata un'eccezione `InvalidOperationException`.  
  
 Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Il risultato di un operatore ?? non viene considerato come una costante, anche se entrambi gli argomenti dell'operatore sono costanti.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)  
 [Cosa significa esattamente "elevato"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
