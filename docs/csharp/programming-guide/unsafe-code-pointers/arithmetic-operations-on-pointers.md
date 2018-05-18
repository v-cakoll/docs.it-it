---
title: Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: c40b125e42649093aa1f1fe860a3e8f5d2690359
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
Questo argomento illustra l'uso degli operatori aritmetici `+` e **-** per modificare i puntatori.  
  
> [!NOTE]
>  È possibile eseguire qualsiasi operazione aritmetica sui puntatori void.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Aggiunta e sottrazione di valori numerici dai puntatori  
 È possibile aggiungere un valore `n` di tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntatore `p` di qualsiasi tipo, ad eccezione di `void*`. `p+n` è il puntatore risultante dall'aggiunta di `n * sizeof(p) to the address of p`. Analogamente, `p-n` è il puntatore risultante dalla sottrazione di `n * sizeof(p)` dall'indirizzo di `p`.  
  
## <a name="subtracting-pointers"></a>Sottrazione di puntatori  
 È anche possibile sottrarre puntatori dello stesso tipo. Il risultato è sempre il tipo `long`. Ad esempio, se `p1` e `p2` sono puntatori di tipo `pointer-type*`, l'espressione `p1-p2` è simile alla seguente:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 Non viene generata nessuna eccezione quando l'operazione aritmetica supera il dominio del puntatore e il risultato dipende dall'implementazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [Modifica dei puntatori](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipi](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
