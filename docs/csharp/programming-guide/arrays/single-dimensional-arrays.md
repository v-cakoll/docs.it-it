---
title: Matrici unidimensionali (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: c2f26fd74a596ada21eef578e58c9cd8e0305d6c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47399385"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrici unidimensionali (Guida per programmatori C#)

È possibile dichiarare una matrice unidimensionale di cinque valori integer, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Questa matrice contiene gli elementi da `array[0]` a `array[4]`. L'operatore [new](../../../csharp/language-reference/keywords/new.md) viene usato per creare la matrice e inizializzare gli elementi della matrice ai valori predefiniti. In questo esempio, tutti gli elementi della matrice vengono inizializzati su zero.  
  
 È possibile dichiarare una matrice che archivia elementi stringa nello stesso modo. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Inizializzazione di una matrice

 È possibile inizializzare una matrice al momento della dichiarazione. In tal caso, l'identificatore del numero di dimensioni non è necessario perché è già fornito dal numero di elementi nell'elenco di inizializzazione. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Una matrice di stringhe può essere inizializzata nello stesso modo. Di seguito è riportata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato da un nome di un giorno:  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Durante l'inizializzazione di una matrice al momento della dichiarazione, è possibile usare i collegamenti seguenti:  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 È possibile dichiarare una variabile di matrice senza inizializzazione, ma è necessario usare l'operatore `new` quando si assegna una matrice a questa variabile. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 In C# 3.0 sono state introdotte le matrici tipizzate in modo implicito. Per altre informazioni, vedere [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Matrici di tipo valore e di tipo riferimento

 Considerare la dichiarazione di matrice seguente:  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento. Se è un tipo valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType`. Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.  
  
 Per altre informazioni su tipi valore e tipi riferimento, vedere [Tipi](../../../csharp/language-reference/keywords/types.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Array](../../../csharp/programming-guide/arrays/index.md)  
- [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
