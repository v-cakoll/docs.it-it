---
title: Passaggio di matrici come argomenti - Guida per programmatori C#
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705691"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Passaggio di matrici come argomenti (Guida per programmatori C#)

Le matrici possono essere passate come argomenti ai parametri di metodo. Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.

## <a name="passing-single-dimensional-arrays-as-arguments"></a>Passaggio di matrici unidimensionali come argomenti

È possibile passare una matrice unidimensionale inizializzata a un metodo. L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a>Esempio

Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `DisplayArray` per le stringhe. Nel metodo vengono visualizzati gli elementi della matrice. Successivamente, il metodo `ChangeArray` inverte gli elementi della matrice e quindi il metodo `ChangeArrayElements` consente di modificare i primi tre elementi della matrice. Al termine delle restituzioni di ogni metodo, il metodo `DisplayArray` mostra che il passaggio di una matrice per valore non impedisce le modifiche agli elementi della matrice.

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a>Passaggio di matrici multidimensionali come argomenti

Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente:

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a>Esempio

Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`. Nel metodo vengono visualizzati gli elementi della matrice.

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Matrici](index.md)
- [Matrici unidimensionali](single-dimensional-arrays.md)
- [Matrici multidimensionali](multidimensional-arrays.md)
- [Matrici irregolari](jagged-arrays.md)
