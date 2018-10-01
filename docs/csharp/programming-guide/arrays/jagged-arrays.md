---
title: Matrici irregolari (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 2e4988439000712f4d1bd9b5abe412e7fd5d43eb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396877"
---
# <a name="jagged-arrays-c-programming-guide"></a>Matrici irregolari (Guida per programmatori C#)

Una matrice di matrici è una matrice i cui elementi sono costituiti da matrici. Gli elementi di una matrice di matrici possono presentare dimensioni e misure diverse. Una matrice di matrici è chiamata talvolta "matrice irregolare". Gli esempi seguenti mostrano come dichiarare, inizializzare e accedere a matrici di matrici.  
  
 Di seguito è riportata la dichiarazione di una matrice unidimensionale a tre elementi, ognuno dei quali è una matrice unidimensionale di Integer:  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Prima di poter usare `jaggedArray`, è necessario che siano stati inizializzati i relativi elementi. È possibile inizializzare gli elementi nel modo seguente:  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Ognuno degli elementi è costituito da una matrice unidimensionale di Integer. Il primo elemento è una matrice di 5 Integer, il secondo una matrice di 4 Integer e il terzo una matrice di 2 Integer.  
  
 È possibile usare gli inizializzatori anche per immettere i valori negli elementi delle matrici. In questo caso, non occorre conoscere le dimensioni delle matrici. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 È inoltre possibile inizializzare la matrice al momento della dichiarazione, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 È possibile usare la forma abbreviata seguente. Non è possibile omettere l'operatore `new` poiché non è prevista alcuna inizializzazione predefinita per gli elementi:  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.  
  
 È possibile accedere ai singoli elementi di una matrice, come negli esempi seguenti:  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 È possibile combinare matrici di matrici e matrici multidimensionali. Di seguito sono riportate la dichiarazione e l'inizializzazione di una matrice di matrici unidimensionale che contiene tre elementi matrice bidimensionali con dimensioni diverse. Per altre informazioni sulle matrici bidimensionali, vedere [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 È possibile accedere a singoli elementi, come illustrato in questo esempio, in cui viene visualizzato il valore dell'elemento `[1,0]` della prima matrice (valore `5`):  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 Il metodo `Length` restituisce il numero di matrici contenute nella matrice di matrici. Si supponga, ad esempio, che sia stata dichiarata la matrice precedente. In questo caso, la riga  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 restituisce il valore 3.  
  
## <a name="example"></a>Esempio

 In questo esempio viene compilata una matrice i cui elementi sono costituiti da matrici. Ogni elemento della matrice ha una dimensione diversa.  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Array](../../../csharp/programming-guide/arrays/index.md)  
- [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
