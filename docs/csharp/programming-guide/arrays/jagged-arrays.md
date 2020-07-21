---
title: Matrici irregolari - Guida per programmatori C#
description: Una matrice di matrici in C# è una matrice i cui elementi sono matrici di dimensioni e dimensioni diverse. Informazioni su come dichiarare, inizializzare e accedere a matrici di matrici.
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 40da9fbda34aef4e69ebf2ae20485e883b79f871
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474683"
---
# <a name="jagged-arrays-c-programming-guide"></a>Matrici irregolari (Guida per programmatori C#)

Una matrice di matrici è una matrice i cui elementi sono costituiti da matrici. Gli elementi di una matrice di matrici possono presentare dimensioni e misure diverse. Una matrice di matrici è chiamata talvolta "matrice irregolare". Gli esempi seguenti mostrano come dichiarare, inizializzare e accedere a matrici di matrici.  
  
 Di seguito è riportata la dichiarazione di una matrice unidimensionale a tre elementi, ognuno dei quali è una matrice unidimensionale di Integer:  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 Prima di poter usare `jaggedArray`, è necessario che siano stati inizializzati i relativi elementi. È possibile inizializzare gli elementi nel modo seguente:  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 Ognuno degli elementi è costituito da una matrice unidimensionale di Integer. Il primo elemento è una matrice di 5 Integer, il secondo una matrice di 4 Integer e il terzo una matrice di 2 Integer.  
  
 È possibile usare gli inizializzatori anche per immettere i valori negli elementi delle matrici. In questo caso, non occorre conoscere le dimensioni delle matrici. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 È inoltre possibile inizializzare la matrice al momento della dichiarazione, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 È possibile usare la forma abbreviata seguente. Non è possibile omettere l'operatore `new` poiché non è prevista alcuna inizializzazione predefinita per gli elementi:  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.  
  
 È possibile accedere ai singoli elementi di una matrice, come negli esempi seguenti:  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 È possibile combinare matrici di matrici e matrici multidimensionali. Di seguito sono riportate la dichiarazione e l'inizializzazione di una matrice di matrici unidimensionale che contiene tre elementi matrice bidimensionali con dimensioni diverse. Per altre informazioni sulle matrici bidimensionali, vedere [Matrici multidimensionali](./multidimensional-arrays.md).  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 È possibile accedere a singoli elementi, come illustrato in questo esempio, in cui viene visualizzato il valore dell'elemento `[1,0]` della prima matrice (valore `5`):  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 Il metodo `Length` restituisce il numero di matrici contenute nella matrice di matrici. Si supponga, ad esempio, che sia stata dichiarata la matrice precedente. In questo caso, la riga  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 restituisce il valore 3.  
  
## <a name="example"></a>Esempio

 In questo esempio viene compilata una matrice i cui elementi sono costituiti da matrici. Ogni elemento della matrice ha una dimensione diversa.  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>
- [Guida per programmatori C#](../index.md)
- [Matrici](./index.md)
- [Matrici unidimensionali](./single-dimensional-arrays.md)
- [Matrici multidimensionali](./multidimensional-arrays.md)
