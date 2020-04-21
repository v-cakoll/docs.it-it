---
title: Come eseguire il cast in modo sicuro utilizzando criteri di ricerca e gli operatori is e as
description: Informazioni su come usare le tecniche dei criteri di ricerca per eseguire il cast sicuro di variabili in un tipo diverso. È possibile usare i criteri di ricerca, nonché gli operatori is e as per convertire in modo sicuro i tipi.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 9f5690e6840098f94360dba89f09fb23b258b782
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739054"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-and-the-is-and-as-operators"></a>Come eseguire il cast in modo sicuro utilizzando criteri di ricerca e gli operatori is e as

Poiché gli oggetti sono polimorfici, è possibile che una variabile di un tipo di classe di base contenga un [tipo](../programming-guide/types/index.md) derivato. Per accedere ai membri dell'istanza del tipo derivato, è necessario eseguire nuovamente il [cast](../programming-guide/types/casting-and-type-conversions.md) del valore al tipo derivato. Tuttavia, un cast crea il rischio di generare un <xref:System.InvalidCastException>. C# offre istruzioni sui [criteri di ricerca](../pattern-matching.md) che eseguono un cast in modo condizionale solo quando ha esito positivo. C# offre anche gli operatori [is](../language-reference/operators/type-testing-and-cast.md#is-operator) e [as](../language-reference/operators/type-testing-and-cast.md#as-operator) per verificare se il valore è di un determinato tipo.

Nell'esempio seguente viene illustrato `is` come utilizzare l'istruzione di criteri di ricerca:The following example shows how to use the pattern matching statement:

[!code-csharp[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

Il campione precedente dimostra alcune funzionalità della sintassi dei criteri di ricerca. L'istruzione `if (a is Mammal m)` combina il test con un'assegnazione di inizializzazione. L'assegnazione si verifica solo quando il test ha esito positivo. La variabile `m` è nell'ambito solo nell'istruzione `if` incorporata a cui è stata assegnata. Non è possibile accedere a `m` successivamente nello stesso metodo. Nell'esempio precedente viene inoltre illustrato come utilizzare [ `as` l'operatore](../language-reference/operators/type-testing-and-cast.md#as-operator) per convertire un oggetto in un tipo specificato.

È inoltre possibile utilizzare la stessa sintassi per il test se un tipo di valore nullable ha un valore, come illustrato nell'esempio seguente:You can also use the same syntax for testing if a [nullable value type](../language-reference/builtin-types/nullable-value-types.md) has a value, as shown in the following example:

[!code-csharp[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

Il campione precedente dimostra alcune funzionalità dei criteri di ricerca per l'uso con le conversioni. È possibile sottoporre a test una variabile per il criterio null controllando in modo specifico il valore `null`. Quando il valore di runtime della variabile è `null`, un'istruzione `is` che controlla il tipo restituisce sempre `false`. L'istruzione `is` dei criteri di ricerca non consente un tipo di valore nullable, quale `int?` o `Nullable<int>`, ma è possibile eseguire il test di qualunque altro tipo di valore. I `is` modelli dell'esempio precedente non sono limitati ai tipi di valore nullable. È inoltre possibile utilizzare tali modelli per verificare se una variabile `null`di un tipo di riferimento ha un valore o è .

Nell'esempio precedente viene inoltre illustrato come `switch` utilizzare il modello di tipo in un'istruzione in cui la variabile può essere uno dei molti tipi diversi.

Se si desidera verificare se una variabile è un determinato tipo, ma `is` non `as` assegnarla a una nuova variabile, è possibile utilizzare gli operatori e per i tipi di riferimento e i tipi di valore nullable. Il codice seguente indica come usare le istruzioni `is` e `as` che facevano parte del linguaggio C# prima che fossero introdotti i criteri di ricerca per verificare se una variabile è di un determinato tipo:

[!code-csharp[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

Come si può vedere dal confronto tra questo codice e il codice dei criteri di ricerca, la sintassi dei criteri di ricerca offre funzionalità più affidabili tramite la combinazione del test e l'assegnazione in un'unica istruzione. Usare la sintassi dei criteri di ricerca qualora possibile.

È possibile provare questi esempi esaminando il codice nel repository [GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/safelycast). Oppure è possibile scaricare gli esempi [come file ZIP](../../../samples/snippets/csharp/how-to/safelycast.zip).
