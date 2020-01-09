---
title: Matrici unidimensionali - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 07c6061bfc66b1640d0eacca217302feff1a390a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715024"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrici unidimensionali (Guida per programmatori C#)

È possibile dichiarare una matrice unidimensionale di cinque valori integer, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 Questa matrice contiene gli elementi da `array[0]` a `array[4]`. L'operatore [new](../../language-reference/operators/new-operator.md) viene usato per creare la matrice e inizializzare gli elementi della matrice ai valori predefiniti. In questo esempio, tutti gli elementi della matrice vengono inizializzati su zero.  
  
 È possibile dichiarare una matrice che archivia elementi stringa nello stesso modo. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a>Inizializzazione di una matrice

 È possibile inizializzare una matrice al momento della dichiarazione. In tal caso, l'identificatore della lunghezza non è necessario perché è già fornito dal numero di elementi nell'elenco di inizializzazione. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 Una matrice di stringhe può essere inizializzata nello stesso modo. Di seguito è riportata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato da un nome di un giorno:  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 Durante l'inizializzazione di una matrice al momento della dichiarazione, è possibile usare i collegamenti seguenti:  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 È possibile dichiarare una variabile di matrice senza inizializzazione, ma è necessario usare l'operatore `new` quando si assegna una matrice a questa variabile. Ad esempio:  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 In C# 3.0 sono state introdotte le matrici tipizzate in modo implicito. Per altre informazioni, vedere [Matrici tipizzate in modo implicito](./implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Matrici di tipo valore e di tipo riferimento

 Considerare la dichiarazione di matrice seguente:  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento. Se è un tipo valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType`. Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.  
  
Per ulteriori informazioni sui tipi di valore e sui tipi di riferimento, vedere [tipi di valore](../../language-reference/keywords/value-types.md) e [tipi di riferimento](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>
- [Guida per programmatori C#](../index.md)
- [Matrici](./index.md)
- [Matrici multidimensionali](./multidimensional-arrays.md)
- [Matrici irregolari](./jagged-arrays.md)
