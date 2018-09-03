---
title: Variabili locali tipizzate in modo implicito (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 91020886e381d8410358cae9511107e28c51452a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464908"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a>Variabili locali tipizzate in modo implicito (Guida per programmatori C#)
Le variabili locali possono essere dichiarate senza specificare un tipo esplicito. La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione. Il tipo dedotto può essere un tipo predefinito, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET Framework. Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
 Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:  
  
 [!code-csharp[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva. Significa semplicemente che il compilatore determina e assegna il tipo più adatto.  
  
 È possibile usare la parola chiave `var` nei contesti seguenti:  
  
-   Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.  
  
-   In un'istruzione di inizializzazione [for](../../../csharp/language-reference/keywords/for.md).  
  
    ```csharp  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   In un'istruzione di inizializzazione [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
    ```csharp  
    foreach(var item in list){...}  
    ```  
  
-   In un'istruzione [using](../../../csharp/language-reference/keywords/using-statement.md).  
  
    ```csharp  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 Per altre informazioni, vedere [Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).  
  
## <a name="var-and-anonymous-types"></a>var e tipi anonimi  
 In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica. Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`. Si tratta di uno scenario comune nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Per altre informazioni, vedere [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 Dal punto di vista del codice sorgente, un tipo anonimo non ha nome. Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.  
  
 [!code-csharp[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a>Note  
 Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:  
  
-   La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.  
  
-   Non è possibile usare `var` nei campi nell'ambito della classe.  
  
-   Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione. In altre parole, questa espressione è valida: `: int i = (i = 20);`. Questa invece genera un errore in fase di compilazione: `var i = (i = 20);`  
  
-   Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.  
  
-   Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.  
  
 `var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query, ad esempio con il raggruppamento e l'ordinamento di operazioni.  
  
 La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice. `var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo. Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`. Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 L'uso di `var`, tuttavia, può quanto meno rendere più difficoltosa la comprensione del codice per gli altri sviluppatori. Nella documentazione di C# `var` viene quindi in genere usata solo quando è necessario.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)  
 [Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)  
 [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [var](../../../csharp/language-reference/keywords/var.md)  
 [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [LINQ (Language-Integrated Query)](../../../csharp/linq/index.md)  
 [for](../../../csharp/language-reference/keywords/for.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md)
