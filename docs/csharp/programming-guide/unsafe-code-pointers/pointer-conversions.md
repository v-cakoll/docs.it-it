---
title: Conversioni di puntatori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 308d5e0646eeb94012dbe18d46d6d33f67dfeaf5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698365"
---
# <a name="pointer-conversions-c-programming-guide"></a>Conversioni di puntatori (Guida per programmatori C#)
Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite. Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.  
  
## <a name="implicit-pointer-conversions"></a>Conversioni di puntatori implicite  
  
|Da|Per|  
|----------|--------|  
|Qualsiasi tipo di puntatore|void*|  
|null|Qualsiasi tipo di puntatore|  
  
 La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita. La tabella seguente illustra queste conversioni.  
  
## <a name="explicit-pointer-conversions"></a>Conversioni di puntatori esplicite  
  
|Da|Per|  
|----------|--------|  
|Qualsiasi tipo di puntatore|Qualsiasi altro tipo di puntatore|  
|sbyte, byte, short, ushort, int, uint, long o ulong|Qualsiasi tipo di puntatore|  
|Qualsiasi tipo di puntatore|sbyte, byte, short, ushort, int, uint, long o ulong|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`. Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso. Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tipi di puntatori](pointer-types.md)
- [Tipi riferimento](../../language-reference/keywords/reference-types.md)
- [Tipi valore](../../language-reference/keywords/value-types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
- [Istruzione fixed](../../language-reference/keywords/fixed-statement.md)
- [stackalloc](../../language-reference/operators/stackalloc.md)
