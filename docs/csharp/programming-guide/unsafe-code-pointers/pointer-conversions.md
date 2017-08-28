---
title: Conversioni di puntatori (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a>Conversioni di puntatori (Guida per programmatori C#)
Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite. Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.  
  
## <a name="implicit-pointer-conversions"></a>Conversioni di puntatori implicite  
  
|Da|Per|  
|----------|--------|  
|Qualsiasi tipo di puntatore|void*|  
|Null|Qualsiasi tipo di puntatore|  
  
 La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita. La tabella seguente illustra queste conversioni.  
  
## <a name="explicit-pointer-conversions"></a>Conversioni di puntatori esplicite  
  
|Da|Per|  
|----------|--------|  
|Qualsiasi tipo di puntatore|Qualsiasi altro tipo di puntatore|  
|sbyte, byte, short, ushort, int, uint, long o ulong|Qualsiasi tipo di puntatore|  
|Qualsiasi tipo di puntatore|sbyte, byte, short, ushort, int, uint, long o ulong|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`. Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso. Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipi](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

