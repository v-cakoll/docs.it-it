---
title: Parola chiave set - Riferimenti per C#
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: 97b0dbf8716edc4cd465eb5ac693efa0ecaa498b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713079"
---
# <a name="set-c-reference"></a>set (Riferimenti per C#)

La parola chiave `set` definisce un metodo *funzione di accesso* in una proprietà o indicizzatore che assegna un valore alla proprietà o all'elemento dell'indicizzatore. Per altre informazioni ed esempi, vedere [Proprietà](../../programming-guide/classes-and-structs/properties.md), [Proprietà implementate automaticamente](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indicizzatori](../../programming-guide/indexers/index.md).

L'esempio seguente definisce le funzioni di accesso `get` e `set` per una proprietà denominata `Seconds`. Usa il campo privato denominato `_seconds` per portare in secondo piano il valore della proprietà.

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

Spesso la funzione di accesso `set` è costituita da una singola istruzione che assegna un valore, come nell'esempio precedente. A partire da C# 7.0, è possibile implementare la funzione di accesso `set` come membro con corpo di espressione. L'esempio seguente implementa entrambe le funzioni di accesso `get` e `set` come membri con corpo di espressione.

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
Per i casi semplici in cui le funzioni di accesso `get` e `set` di una proprietà non eseguono operazioni diverse dall'impostazione o recupero di un valore in un campo sottostante, è possibile sfruttare il supporto del compilatore C# per le proprietà implementate automaticamente. L'esempio seguente implementa `Hours` come una proprietà implementata automaticamente. 

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Proprietà](../../programming-guide/classes-and-structs/properties.md)
