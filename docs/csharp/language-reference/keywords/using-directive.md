---
title: Direttiva using - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 4f7ddad8c3dc12391ef6bf345a73ebb384400b38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093149"
---
# <a name="using-directive-c-reference"></a>Direttiva using (Riferimenti per C#)

La direttiva `using` ha tre usi:

- Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:

    ```csharp
    using System.Text;
    ```

- Consentire l'accesso ai membri statici e ai tipi nidificati di un tipo senza dover qualificare l'accesso con il nome del tipo.

    ```csharp
    using static System.Math;
    ```

    Per altre informazioni, vedere la [direttiva using static](using-static.md).

- Creare un alias per uno spazio dei nomi o un tipo. Si tratta di una *direttiva alias using*.

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente. Per altre informazioni, vedere [Istruzione using](using-statement.md).

## <a name="using-static-type"></a>Tipo using static

È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a>Osservazioni

L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.

La direttiva `using` può essere visualizzata:

- All'inizio del file del codice sorgente, prima di eventuali definizioni di spazio dei nomi o tipo.
- In qualsiasi spazio dei nomi, ma prima di un spazio dei nomi o di tipi dichiarati nello spazio dei nomi.

In caso contrario, viene generato l'errore del compilatore [CS1529](../../misc/cs1529.md).

Creare una direttiva alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo. In una direttiva `using` è necessario usare lo spazio dei nomi o il tipo completo indipendentemente dalle direttive `using` che la precedono. Non è possibile usare alcun alias `using` nella dichiarazione di una direttiva `using`. Ad esempio, il codice seguente genera un errore del compilatore:

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi. Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.

Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema. Gli spazi dei nomi definiti dall'utente vengono definiti nel codice. Per un elenco di spazi dei nomi definiti dal sistema, vedere [Browser API .NET](../../../../api/index.md).

## <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

Una direttiva alias using non può contenere un tipo generico aperto nella parte destra. Ad esempio, non è possibile creare un alias using per`List<T>`, ma è possibile crearne uno per `List<int>`.

## <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Direttive using](~/_csharplang/spec/namespaces.md#using-directives) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Uso degli spazi dei nomi](../../programming-guide/namespaces/using-namespaces.md)
- [Parole chiave di C#](index.md)
- [Spazi dei nomi](../../programming-guide/namespaces/index.md)
- [Istruzione using](using-statement.md)
