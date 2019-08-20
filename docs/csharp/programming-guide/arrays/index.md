---
title: Matrici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 24c6d54c3fe92ada661e732adec582e87ab62417
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597522"
---
# <a name="arrays-c-programming-guide"></a>Matrici (Guida per programmatori C#)

È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice. Una matrice viene dichiarata specificando il tipo degli elementi.  
  
 `type[] arrayName;`  
  
 L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a>Panoramica delle matrici

 Le matrici hanno le proprietà seguenti:  
  
- Una matrice può essere [unidimensionale](./single-dimensional-arrays.md), [multidimensionale](./multidimensional-arrays.md) o [irregolare](./jagged-arrays.md).  
  
- Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice. Questi valori non possono essere modificati per la durata dell'istanza.  
  
- I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.  
  
- Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.  
  
- Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.  
  
- Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.  
  
- I tipi matrice sono [tipi di riferimento](../../language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>. Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../language-reference/keywords/foreach-in.md) su tutte le matrici in C#.  
  
## <a name="related-sections"></a>Sezioni correlate  
  
- [Matrici come oggetti](./arrays-as-objects.md)  
  
- [Uso di foreach con matrici](./using-foreach-with-arrays.md)  
  
- [Passaggio di matrici come argomenti](./passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Raccolte](../concepts/collections.md)
