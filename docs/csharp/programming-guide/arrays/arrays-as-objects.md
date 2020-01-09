---
title: Matrici come oggetti - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: d8b929eccf9be259874d03dd93f49a49798bb349
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715097"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Matrici come oggetti (Guida per programmatori C#)

In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++. <xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice. È possibile utilizzare le proprietà e altri membri della classe che <xref:System.Array> dispone di. Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza di una matrice. Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.

## <a name="example"></a>Esempio

Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Matrici](./index.md)
- [Matrici unidimensionali](./single-dimensional-arrays.md)
- [Matrici multidimensionali](./multidimensional-arrays.md)
- [Matrici irregolari](./jagged-arrays.md)
