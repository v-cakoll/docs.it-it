---
title: 'Procedura: Incrementare e decrementare i puntatori (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: c75432d88a1e96742573a6e69a4e035066a387c4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128336"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Procedura: Incrementare e decrementare i puntatori (Guida per programmatori C#)

Gli operatori di incremento e decremento `++` e `--` consentono di modificare la posizione del puntatore in base a `sizeof(pointer-type)` per un puntatore di tipo `pointer-type*`. Il formato delle espressioni di incremento e decremento è il seguente:  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 È possibile applicare gli operatori di incremento e decremento ai puntatori di qualsiasi tipo, ad eccezione del tipo `void*`.  
  
 Quando si applica l'operatore di incremento a un puntatore di tipo `pointer-type*`, si aggiunge `sizeof(pointer-type)` all'indirizzo contenuto nella variabile del puntatore.  
  
 Quando si applica l'operatore di decremento a un puntatore di tipo `pointer-type*`, si sottrae `sizeof(pointer-type)` dall'indirizzo contenuto nella variabile del puntatore.  
  
 Quando l'operazione causa un overflow del dominio del puntatore, non vengono generate eccezioni e il risultato dipende dall'implementazione.  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra come passare da un elemento di una matrice all'altro incrementando il puntatore della dimensione di `int`. A ogni passaggio vengono visualizzati l'indirizzo e il contenuto dell'elemento della matrice.  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
**Valore:0 @ Address:12860272**
**Valore:1 @ Address:12860276**
**Valore:2 @ Address:12860280**
**Valore:3 @ Address:12860284**
**Valore:4 @ Address:12860288**

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)  
- [Modifica dei puntatori](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Tipi](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
- [sizeof](../../../csharp/language-reference/keywords/sizeof.md)
