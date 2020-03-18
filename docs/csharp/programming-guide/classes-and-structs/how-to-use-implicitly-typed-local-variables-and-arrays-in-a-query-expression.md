---
title: Come utilizzare le matrici e le variabili locali tipizzate in modo implicito in un'espressione di query - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: f4ff71fc4dc1a0b2affa1f032ab1d3d6bb04d297
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705561"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Come utilizzare le matrici e le variabili locali tipizzate in modo implicito in un'espressione di query (Guida per programmatori C
È possibile usare le variabili locali tipizzate in modo implicito ogni volta che si vuole che il compilatore determini il tipo di una variabile locale. È necessario usare le variabili locali tipizzate in modo implicito per archiviare i tipi anonimi, che vengono spesso usati nelle espressioni di query. Gli esempi seguenti illustrano tipi d'uso facoltativi e obbligatori delle variabili locali tipizzate in modo implicito nelle query.  
  
 Le variabili locali tipizzate in modo implicito vengono dichiarate usando la parola chiave contestuale [var](../../language-reference/keywords/var.md). Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](./implicitly-typed-local-variables.md) e [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno scenario comune in cui la parola chiave `var` è obbligatoria: un'espressione di query che produce una sequenza di tipi anonimi. In questo scenario sia la variabile di query che la variabile di iterazione nell'istruzione `foreach` devono essere tipizzate in modo implicito usando `var`, perché non si ha accesso a un nome di tipo per il tipo anonimo. Per altre informazioni sui tipi anonimi, vedere [Tipi anonimi](./anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la parola chiave `var` in una situazione simile, ma in cui l'uso di `var` è facoltativo. Poiché `student.LastName` è una stringa, l'esecuzione della query restituisce una sequenza di stringhe. Il tipo di `queryID` può quindi essere dichiarato come `System.Collections.Generic.IEnumerable<string>` invece di `var`. La parola chiave `var` viene usata per praticità. Nell'esempio la variabile di iterazione nell'istruzione `foreach` è tipizzata in modo esplicito come stringa, ma potrebbe invece essere dichiarata usando `var`. Poiché il tipo della variabile di iterazione non è un tipo anonimo, l'uso di `var` è facoltativo e non obbligatorio. Tenere presente che `var` non è un tipo, ma un'istruzione che indica al compilatore di derivare tramite inferenza e assegnare il tipo.  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Metodi di estensione](./extension-methods.md)
- [LINQ (Language-Integrated Query)](../../linq/index.md)
- [Var](../../language-reference/keywords/var.md)
- [LINQ in C#](../../linq/index.md)
