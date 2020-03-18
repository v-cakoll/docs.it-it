---
title: Come eseguire il cast in modo sicuro utilizzando criteri di ricerca e gli operatori is e as
description: Informazioni su come usare le tecniche dei criteri di ricerca per eseguire il cast sicuro di variabili in un tipo diverso. È possibile usare i criteri di ricerca, nonché gli operatori is e as per convertire in modo sicuro i tipi.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 762f8135063f7256ce7a167c65013703d9249039
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973084"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-and-the-is-and-as-operators"></a>Come eseguire il cast in modo sicuro utilizzando criteri di ricerca e gli operatori is e as

Poiché gli oggetti sono polimorfici, è possibile che una variabile di un tipo di classe di base contenga un [tipo](../programming-guide/types/index.md) derivato. Per accedere ai membri dell'istanza del tipo derivato, è necessario eseguire nuovamente il [cast](../programming-guide/types/casting-and-type-conversions.md) del valore al tipo derivato. Tuttavia, un cast crea il rischio di generare un <xref:System.InvalidCastException>. C# offre istruzioni sui [criteri di ricerca](../pattern-matching.md) che eseguono un cast in modo condizionale solo quando ha esito positivo. C# offre anche gli operatori [is](../language-reference/operators/type-testing-and-cast.md#is-operator) e [as](../language-reference/operators/type-testing-and-cast.md#as-operator) per verificare se il valore è di un determinato tipo.

Il codice seguente dimostra l'istruzione `is` dei criteri di ricerca. Contiene metodi che verificano un argomento del metodo per determinare se si tratta di uno dei possibili set di tipi derivati:

[!code-csharp[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

Il campione precedente dimostra alcune funzionalità della sintassi dei criteri di ricerca. Le istruzioni `if (a is Mammal m)` e `if (o is Mammal m)` combinano il test con un'assegnazione di inizializzazione. L'assegnazione si verifica solo quando il test ha esito positivo. La variabile `m` è nell'ambito solo nell'istruzione `if` incorporata a cui è stata assegnata. Non è possibile accedere a `m` successivamente nello stesso metodo. Provare nella finestra interattiva.

È anche possibile usare la stessa sintassi per il test se un tipo di valore nullable ha un valore, come illustrato nel codice di esempio seguente:You can also use the same syntax for testing if a [nullable value type](../language-reference/builtin-types/nullable-value-types.md) has a value, as shown in the following sample code:

[!code-csharp[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

Il campione precedente dimostra alcune funzionalità dei criteri di ricerca per l'uso con le conversioni. È possibile sottoporre a test una variabile per il criterio null controllando in modo specifico il valore `null`. Quando il valore di runtime della variabile è `null`, un'istruzione `is` che controlla il tipo restituisce sempre `false`. L'istruzione `is` dei criteri di ricerca non consente un tipo di valore nullable, quale `int?` o `Nullable<int>`, ma è possibile eseguire il test di qualunque altro tipo di valore. I `is` modelli dell'esempio precedente non sono limitati ai tipi di valore nullable. È inoltre possibile utilizzare tali modelli per verificare se una variabile `null`di un tipo di riferimento ha un valore o è .

L'esempio precedente illustra anche come utilizzare l'espressione `is` dei criteri di ricerca in un'istruzione `switch` in cui la variabile può essere di molti tipi diversi.

Se si desidera verificare se una variabile è di un tipo specificato, ma non assegnarlo a una nuova variabile, è possibile usare gli operatori `is` e `as` per i tipi di riferimento e per i tipi nullable. Il codice seguente indica come usare le istruzioni `is` e `as` che facevano parte del linguaggio C# prima che fossero introdotti i criteri di ricerca per verificare se una variabile è di un determinato tipo:

[!code-csharp[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

Come si può vedere dal confronto tra questo codice e il codice dei criteri di ricerca, la sintassi dei criteri di ricerca offre funzionalità più affidabili tramite la combinazione del test e l'assegnazione in un'unica istruzione. Usare la sintassi dei criteri di ricerca qualora possibile.

È possibile provare questi esempi esaminando il codice nel repository [GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/safelycast). Oppure è possibile scaricare gli esempi [come file ZIP](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/safelycast.zip).
