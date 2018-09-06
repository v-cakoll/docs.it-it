---
title: Funzioni inline (F#)
description: 'Informazioni su come utilizzare F # le funzioni inline che sono integrate direttamente nel codice chiamante.'
ms.date: 05/16/2016
ms.openlocfilehash: 47fca0fe34630792aeb0908b0cee02a927e2567d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875057"
---
# <a name="inline-functions"></a>Funzioni inline

*Funzioni inline* sono funzioni che sono integrate direttamente nel codice chiamante.

## <a name="using-inline-functions"></a>Utilizzo delle funzioni Inline

Quando si usano parametri di tipo statico, qualsiasi funzione che vengono parametrizzate dai parametri di tipo devono essere inline. In questo modo si garantisce che il compilatore può risolvere questi parametri di tipo. Quando si usano parametri di tipo generico normali, non è non implica tale restrizione.

Oltre che per consentire l'utilizzo di vincoli relativi ai membri, funzioni inline possono essere utili nell'ottimizzazione del codice. Utilizzo eccessivo di funzioni inline, tuttavia, può causare il codice può essere meno resistente alle modifiche apportate alle ottimizzazioni del compilatore e l'implementazione delle funzioni della libreria. Per questo motivo, è consigliabile evitare l'utilizzo delle funzioni inline per l'ottimizzazione a meno che non si sono provato a tutte le altre tecniche di ottimizzazione. Rendere inline una funzione o un metodo talvolta possono migliorare le prestazioni, ma non che è sempre così. Pertanto, si devono inoltre utilizzare le misurazioni delle prestazioni per verificare che effettua una funzione inline in realtà hanno un effetto positivo.

Il `inline` modificatore può essere applicato alle funzioni di primo livello, a livello di modulo o a livello di metodo in una classe.

L'esempio di codice seguente illustra una funzione inline a livello superiore, un metodo di istanza inline e un metodo statico inline.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>Le funzioni inline e l'inferenza del tipo

La presenza di `inline` interessa l'inferenza del tipo. Questo avviene perché le funzioni inline possono avere risolti staticamente parametri di tipo, operazione Impossibile con le funzioni non inline. Esempio di codice seguente viene illustrato un caso in cui `inline` è utile perché si sta usando una funzione che ha un parametro di tipo risolti staticamente, la `float` operatore di conversione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Senza il `inline` modificatore, l'inferenza del tipo impone la funzione accetti un tipo specifico, in questo caso `int`. Ma con la `inline` modificatore, la funzione viene anche dedotto per avere un parametro di tipo risolti staticamente. Con la `inline` modificatore, il tipo viene dedotto come quanto segue:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Ciò significa che la funzione accetta qualsiasi tipo che supporta una conversione **float**.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Vincoli](../generics/constraints.md)
- [Parametri di tipo risolti staticamente](../generics/statically-resolved-type-parameters.md)
