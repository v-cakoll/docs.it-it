---
title: Matrici - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715061"
---
# <a name="arrays-c-programming-guide"></a>Matrici (Guida per programmatori C#)

È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice. Una matrice viene dichiarata specificando il tipo degli elementi. Se si desidera che la matrice memorizzi elementi di qualsiasi tipo, è possibile specificare `object` come tipo. Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.

```csharp
type[] arrayName;
```

## <a name="example"></a>Esempio

L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a>Panoramica dell'array

Le matrici hanno le proprietà seguenti:

- Una matrice può essere [unidimensionale](single-dimensional-arrays.md), [multidimensionale](multidimensional-arrays.md) o [irregolare](jagged-arrays.md).
- Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice. Questi valori non possono essere modificati per la durata dell'istanza.
- I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.
- Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.
- Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.
- Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.
- I tipi matrice sono [tipi di riferimento](../../language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>. Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../language-reference/keywords/foreach-in.md) su tutte le matrici in C#.

## <a name="related-sections"></a>Sezioni correlate

- [Matrici come oggetti](arrays-as-objects.md)
- [Uso di foreach con matrici](using-foreach-with-arrays.md)
- [Passaggio di matrici come argomenti](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [raccolte](../concepts/collections.md)
