---
title: Parola chiave contestuale value - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 84d0c51ddafb59144f4ba8c6e73412642fa8fa28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712897"
---
# <a name="value-c-reference"></a>value (Riferimenti per C#)

La parola chiave contestuale `value` viene utilizzata nella funzione di accesso `set` nelle dichiarazioni di [Proprietà](../../programming-guide/classes-and-structs/properties.md) e [indicizzatori](../../programming-guide/indexers/index.md) . È simile a un parametro di input di un metodo. La parola `value` fa riferimento al valore che il codice client sta tentando di assegnare alla proprietà o all'indicizzatore. Nell'esempio seguente, `MyDerivedClass` ha una proprietà denominata `Name` che usa il parametro `value` per assegnare una nuova stringa al campo sottostante `name`. Dal punto di vista del codice client, l'operazione viene scritta come assegnazione semplice.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Per altre informazioni, vedere gli articoli [Proprietà](../../programming-guide/classes-and-structs/properties.md) e [Indexeres](../../programming-guide/indexers/index.md) .

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
