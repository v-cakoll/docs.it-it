---
title: Utilizzo di foreach con matrici (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Utilizzo di foreach con matrici (Guida per programmatori C#)
In C# è disponibile anche l'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Questa istruzione offre un metodo semplice e diretto per scorrere gli elementi di una matrice o qualsiasi raccolta enumerabile. L'istruzione `foreach` elabora gli elementi nell'ordine restituito dalla matrice o dall'enumeratore del tipo di raccolta, in genere dall'elemento zero all'ultimo. Il codice che segue, ad esempio, consente la creazione di una matrice denominata `numbers` e di scorrere tale matrice con l'istruzione `foreach`:  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Con le matrici multidimensionali è possibile utilizzare lo stesso metodo per scorrere gli elementi, ad esempio:  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 Con le matrici multidimensionali, tuttavia, l'uso di un ciclo [for](../../../csharp/language-reference/keywords/for.md) annidato fornisce maggiore controllo sugli elementi della matrice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Array](../../../csharp/programming-guide/arrays/index.md)  
 [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
