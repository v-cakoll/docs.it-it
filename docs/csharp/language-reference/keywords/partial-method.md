---
title: Metodo parziale - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 14bcd3329b6ca8e46f6c180c97174a561108d143
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633362"
---
# <a name="partial-method-c-reference"></a>Metodo parziale (Riferimenti per C#)

Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo. I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno. Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione. Ai metodi parziali si applicano le condizioni seguenti:

- Le firme nelle due parti del tipo parziale devono corrispondere.

- Il metodo deve restituire void.

- Non è consentito alcun modificatore di accesso. I metodi parziali sono implicitamente privati.

Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

Per altre informazioni, vedere [Classi e metodi parziali](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Tipo parziale](partial-type.md)
