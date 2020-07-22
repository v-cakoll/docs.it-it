---
title: Variabili locali tipizzate in modo implicito - Guida per programmatori C#
description: La parola chiave var in C# indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 6badb8588dedda80227ab38bee027cf2890c8672
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864215"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a>Variabili locali tipizzate in modo implicito - Guida per programmatori C#

Le variabili locali possono essere dichiarate senza specificare un tipo esplicito. La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione. Il tipo derivato può essere un tipo incorporato, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET. Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md).

Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva. Significa semplicemente che il compilatore determina e assegna il tipo più adatto.

È possibile usare la parola chiave `var` nei contesti seguenti:

- Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.

- In un'istruzione di inizializzazione [for](../../language-reference/keywords/for.md).

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- In un'istruzione di inizializzazione [foreach](../../language-reference/keywords/foreach-in.md).

    ```csharp
    foreach (var item in list) {...}
    ```

- In un'istruzione [using](../../language-reference/keywords/using-statement.md).

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

Per ulteriori informazioni, vedere [come utilizzare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).

## <a name="var-and-anonymous-types"></a>var e tipi anonimi

In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica. Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`. Si tratta di uno scenario comune nelle espressioni di query LINQ. Per ulteriori informazioni, vedere [tipi anonimi](anonymous-types.md).

Dal punto di vista del codice sorgente, un tipo anonimo non ha nome. Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a>Commenti

Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:

- La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.

- Non è possibile usare `var` nei campi nell'ambito della classe.

- Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione. In altre parole, questa espressione è valida: `int i = (i = 20);` ma questa espressione genera un errore in fase di compilazione:`var i = (i = 20);`

- Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.

- Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.

La tipizzazione implicita con la parola chiave `var` può essere applicata solo alle variabili nell'ambito del metodo locale. La tipizzazione implicita non è disponibile per i campi di classe perché il compilatore C# riscontrerebbe un paradosso logico durante l'elaborazione del codice: il compilatore deve conoscere il tipo del campo, ma è in grado di determinare il tipo solo dopo che l'espressione di assegnazione è stata analizzata e l'espressione non può essere valutata senza conoscere il tipo. Osservare il codice seguente:

```csharp
private var bookTitles;
```

`bookTitles` è un campo di classe a cui è stato assegnato il tipo `var`. Poiché il campo non ha alcuna espressione da valutare, è impossibile per il compilatore dedurre quale tipo dovrebbe essere `bookTitles`. Inoltre, anche l'aggiunta di un'espressione al campo, come si farebbe per una variabile locale, risulta insufficiente:

```csharp
private var bookTitles = new List<string>();
```

Quando il compilatore rileva i campi durante la compilazione del codice, registra il tipo di ogni campo prima di elaborare le espressioni a esso associate. Durante il tentativo di analisi di `bookTitles`, il compilatore rileva lo stesso paradosso: ha necessità di conoscere il tipo del campo, ma il compilatore normalmente determina il tipo di `var` tramite l'analisi dell'espressione, operazione che non è possibile eseguire senza conoscere prima il tipo.

`var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query, ad esempio con il raggruppamento e l'ordinamento di operazioni.

La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice. `var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo. Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`. Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

L'uso di `var` consente di semplificare il codice, ma il suo uso dovrebbe essere limitato ai casi in cui è necessario o quando rende il codice più facile da leggere. Per altre informazioni su quando usare `var` correttamente, vedere la sezione [variabili locali tipizzate in modo implicito](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) nell'articolo linee guida per il codice C#.

## <a name="see-also"></a>Vedi anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md)
- [Come usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [Tipi anonimi](anonymous-types.md)
- [Inizializzatori di oggetto e di raccolta](object-and-collection-initializers.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ in C#](../../linq/index.md)
- [LINQ (Language-Integrated Query)](../../linq/index.md)
- [for](../../language-reference/keywords/for.md)
- [foreach, in](../../language-reference/keywords/foreach-in.md)
- [Istruzione using](../../language-reference/keywords/using-statement.md)
