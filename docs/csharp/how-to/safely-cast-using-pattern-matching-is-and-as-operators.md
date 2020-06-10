---
title: Come eseguire il cast in modo sicuro usando i criteri di ricerca e gli operatori is e As
description: Informazioni su come usare le tecniche dei criteri di ricerca per eseguire il cast sicuro di variabili in un tipo diverso. È possibile usare i criteri di ricerca, nonché gli operatori is e as per convertire in modo sicuro i tipi.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: f10ce837057cc61b84130f237a13af708849dfc5
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662966"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-and-the-is-and-as-operators"></a>Come eseguire il cast in modo sicuro usando i criteri di ricerca e gli operatori is e As

Poiché gli oggetti sono polimorfici, è possibile che una variabile di un tipo di classe di base contenga un [tipo](../programming-guide/types/index.md) derivato. Per accedere ai membri dell'istanza del tipo derivato, è necessario eseguire nuovamente il [cast](../programming-guide/types/casting-and-type-conversions.md) del valore al tipo derivato. Tuttavia, un cast crea il rischio di generare un <xref:System.InvalidCastException>. C# offre istruzioni sui [criteri di ricerca](../pattern-matching.md) che eseguono un cast in modo condizionale solo quando ha esito positivo. C# offre anche gli operatori [is](../language-reference/operators/type-testing-and-cast.md#is-operator) e [as](../language-reference/operators/type-testing-and-cast.md#as-operator) per verificare se il valore è di un determinato tipo.

Nell'esempio seguente viene illustrato come utilizzare l'istruzione dei criteri di ricerca `is` :

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs" id="PatternMatchingIs":::

Il campione precedente dimostra alcune funzionalità della sintassi dei criteri di ricerca. L' `if (a is Mammal m)` istruzione combina il test con un'assegnazione di inizializzazione. L'assegnazione si verifica solo quando il test ha esito positivo. La variabile `m` è nell'ambito solo nell'istruzione `if` incorporata a cui è stata assegnata. Non è possibile accedere a `m` successivamente nello stesso metodo. Nell'esempio precedente viene inoltre illustrato come utilizzare l' [ `as` operatore](../language-reference/operators/type-testing-and-cast.md#as-operator) per convertire un oggetto in un tipo specificato.

È anche possibile usare la stessa sintassi per verificare se un [tipo di valore Nullable](../language-reference/builtin-types/nullable-value-types.md) ha un valore, come illustrato nell'esempio seguente:

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs" id="PatternMatchingNullable":::

Il campione precedente dimostra alcune funzionalità dei criteri di ricerca per l'uso con le conversioni. È possibile sottoporre a test una variabile per il criterio null controllando in modo specifico il valore `null`. Quando il valore di runtime della variabile è `null`, un'istruzione `is` che controlla il tipo restituisce sempre `false`. L'istruzione `is` dei criteri di ricerca non consente un tipo di valore nullable, quale `int?` o `Nullable<int>`, ma è possibile eseguire il test di qualunque altro tipo di valore. I `is` modelli dell'esempio precedente non sono limitati ai tipi di valore Nullable. È anche possibile usare questi modelli per verificare se una variabile di un tipo di riferimento ha un valore o `null` .

Nell'esempio precedente viene inoltre illustrato come utilizzare il modello di tipo in un' `switch` istruzione in cui la variabile può essere di uno di molti tipi diversi.

Se si desidera verificare se una variabile è un tipo specificato, ma non assegnarla a una nuova variabile, è possibile utilizzare gli `is` operatori e `as` per i tipi di riferimento e i tipi di valore Nullable. Il codice seguente indica come usare le istruzioni `is` e `as` che facevano parte del linguaggio C# prima che fossero introdotti i criteri di ricerca per verificare se una variabile è di un determinato tipo:

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs" id="IsAndAs":::

Come si può vedere dal confronto tra questo codice e il codice dei criteri di ricerca, la sintassi dei criteri di ricerca offre funzionalità più affidabili tramite la combinazione del test e l'assegnazione in un'unica istruzione. Usare la sintassi dei criteri di ricerca qualora possibile.
