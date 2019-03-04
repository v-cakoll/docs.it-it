---
title: Uso di foreach con matrici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: a22cb939370b38780881eca0d9585a14002c8250
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966411"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Utilizzo di foreach con matrici (Guida per programmatori C#)

L'istruzione [foreach](../../language-reference/keywords/foreach-in.md) offre un metodo semplice e diretto per scorrere gli elementi di una matrice.

Per le matrici unidimensionali, l'istruzione `foreach` elabora gli elementi in ordine di indice crescente, a partire dall'indice 0 e terminando con l'indice `Length - 1`:

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

Per le matrici multidimensionali, l'attraversamento degli elementi avviene in modo da incrementare per primi gli indici della dimensione all'estrema destra, per poi proseguire con la dimensione successiva a sinistra e così via verso sinistra:

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

Con le matrici multidimensionali, tuttavia, l'uso di un ciclo [for](../../language-reference/keywords/for.md) annidato fornisce maggiore controllo sull'ordine di elaborazione degli elementi della matrice.

## <a name="see-also"></a>Vedere anche

- <xref:System.Array>
- [Guida per programmatori C#](../index.md)
- [Matrici](index.md)
- [Matrici unidimensionali](single-dimensional-arrays.md)
- [Matrici multidimensionali](multidimensional-arrays.md)
- [Matrici irregolari](jagged-arrays.md)
