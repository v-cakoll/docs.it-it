---
title: Operazioni aritmetiche sui puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: bfa81bc926b4fe81455cecb88bc55f4dcd69268e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977838"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
Questo argomento illustra l'uso degli operatori aritmetici `+` e `-` per modificare i puntatori.  
  
> [!NOTE]
>  È possibile eseguire qualsiasi operazione aritmetica sui puntatori void.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Aggiunta e sottrazione di valori numerici ai o dai puntatori  
 È possibile aggiungere un valore `n` di tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntatore. Se `p` è un puntatore di tipo `pointer-type*`, il risultato `p+n` è il puntatore risultante dall'aggiunta di `n * sizeof(pointer-type)` all'indirizzo di `p`. Analogamente, `p-n` è il puntatore risultante dalla sottrazione di `n * sizeof(pointer-type)` dall'indirizzo di `p`.  
  
## <a name="subtracting-pointers"></a>Sottrazione di puntatori  
 È anche possibile sottrarre puntatori dello stesso tipo. Il risultato è sempre il tipo `long`. Ad esempio, se `p1` e `p2` sono puntatori di tipo `pointer-type*`, l'espressione `p1-p2` è simile alla seguente:  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 Non viene generata nessuna eccezione quando l'operazione aritmetica supera il dominio del puntatore e il risultato dipende dall'implementazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
- [Modifica dei puntatori](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
