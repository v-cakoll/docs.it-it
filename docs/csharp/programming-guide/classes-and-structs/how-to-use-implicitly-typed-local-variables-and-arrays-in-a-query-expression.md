---
title: "Procedura: utilizzare variabili e matrici locali tipizzate in modo implicito in un'espressione di query (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: dccf40508d4223bdef0b2fbbe5ce97f75ffb5773
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500986"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Procedura: utilizzare variabili e matrici locali tipizzate in modo implicito in un'espressione di query (Guida per programmatori C#)
È possibile usare le variabili locali tipizzate in modo implicito ogni volta che si vuole che il compilatore determini il tipo di una variabile locale. È necessario usare le variabili locali tipizzate in modo implicito per archiviare i tipi anonimi, che vengono spesso usati nelle espressioni di query. Gli esempi seguenti illustrano tipi d'uso facoltativi e obbligatori delle variabili locali tipizzate in modo implicito nelle query.  
  
 Le variabili locali tipizzate in modo implicito vengono dichiarate usando la parola chiave contestuale [var](../../../csharp/language-reference/keywords/var.md). Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) e [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno scenario comune in cui la parola chiave `var` è obbligatoria: un'espressione di query che produce una sequenza di tipi anonimi. In questo scenario sia la variabile di query che la variabile di iterazione nell'istruzione `foreach` devono essere tipizzate in modo implicito usando `var`, perché non si ha accesso a un nome di tipo per il tipo anonimo. Per altre informazioni sui tipi anonimi, vedere [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la parola chiave `var` in una situazione simile, ma in cui l'uso di `var` è facoltativo. Poiché `student.LastName` è una stringa, l'esecuzione della query restituisce una sequenza di stringhe. Il tipo di `queryID` può quindi essere dichiarato come `System.Collections.Generic.IEnumerable<string>` invece di `var`. La parola chiave `var` viene usata per praticità. Nell'esempio la variabile di iterazione nell'istruzione `foreach` è tipizzata in modo esplicito come stringa, ma potrebbe invece essere dichiarata usando `var`. Poiché il tipo della variabile di iterazione non è un tipo anonimo, l'uso di `var` è facoltativo e non obbligatorio. Tenere presente che `var` non è un tipo, ma un'istruzione che indica al compilatore di derivare tramite inferenza e assegnare il tipo.  
  
 [!code-csharp[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Metodi di estensione](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
- [LINQ (Language-Integrated Query)](../../../csharp/linq/index.md)  
- [var](../../../csharp/language-reference/keywords/var.md)  
- [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
