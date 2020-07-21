---
title: Matrici unidimensionali - Guida per programmatori C#
description: Creare una matrice unidimensionale in C# usando l'operatore New che specifica il tipo di elemento della matrice e il numero di elementi.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474592"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrici unidimensionali (Guida per programmatori C#)

Si crea una matrice unidimensionale usando l'operatore [New](../../language-reference/operators/new-operator.md) che specifica il tipo di elemento della matrice e il numero di elementi. Nell'esempio seguente viene dichiarata una matrice di cinque Integer:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

Questa matrice contiene gli elementi da `array[0]` a `array[4]`. Gli elementi della matrice vengono inizializzati sul valore predefinito del tipo di elemento, `0` per i numeri interi.

Le matrici possono archiviare qualsiasi tipo di elemento specificato, ad esempio l'esempio seguente che dichiara una matrice di stringhe:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a>Inizializzazione di una matrice

È possibile inizializzare gli elementi di una matrice quando si dichiara la matrice. L'identificatore di lunghezza non è necessario perché è dedotto dal numero di elementi nell'elenco di inizializzazione. Ad esempio:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

Nel codice seguente viene illustrata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato in base al nome di un giorno:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
È possibile evitare l' `new` espressione e il tipo di matrice quando si Inizializza una matrice al momento della dichiarazione, come illustrato nel codice seguente. Si tratta di una [matrice tipizzata in modo implicito](implicitly-typed-arrays.md):

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

È possibile dichiarare una variabile di matrice senza crearla, ma è necessario usare l' `new` operatore quando si assegna una nuova matrice a questa variabile. Ad esempio:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a>Matrici di tipo valore e di tipo riferimento

Considerare la dichiarazione di matrice seguente:  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento. Se è un tipo di valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType` . Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null. In entrambe le istanze gli elementi vengono inizializzati sul valore predefinito per il tipo di elemento. Per ulteriori informazioni sui tipi di valore e sui tipi di riferimento, vedere [tipi di valore](../../language-reference/builtin-types/value-types.md) e [tipi di riferimento](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>
- [Matrici](./index.md)
- [Matrici multidimensionali](./multidimensional-arrays.md)
- [Matrici irregolari](./jagged-arrays.md)
