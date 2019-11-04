---
title: Conversioni di puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: b0a517eacc505376c9502e9d095c7aac0cd54555
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417525"
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
- [Tipi di puntatori](./pointer-types.md)
- [Tipi](/dotnet/csharp/language-reference/keywords)
- [unsafe](../../language-reference/keywords/unsafe.md)
- [Istruzione fixed](../../language-reference/keywords/fixed-statement.md)
- [stackalloc](../../language-reference/operators/stackalloc.md)
