---
title: Tipi di enumerazione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969770"
---
# <a name="enumeration-types-c-programming-guide"></a>Tipi di enumerazione (Guida per programmatori C#)

Un tipo di enumerazione (detto anche enumerazione o enum) rappresenta un modo efficiente per definire un set di costanti integrali denominate che possono essere assegnate a una variabile. Si supponga ad esempio di dover definire una variabile il cui valore rappresenterà un giorno della settimana. Ci sono solo sette valori significativi che la variabile potrà mai archiviare. Per definire tali valori, è possibile usare un tipo di enumerazione, dichiarato tramite la parola chiave [enum](../language-reference/keywords/enum.md).

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

Per impostazione predefinita, il tipo sottostante di ogni elemento dell'enumerazione è [int](../language-reference/builtin-types/integral-numeric-types.md). È possibile specificare un altro tipo numerico integrale usando i due punti, come illustrato nell'esempio precedente. Per un elenco completo dei tipi possibili, vedere [enum (Riferimenti per C#)](../language-reference/keywords/enum.md).

È possibile verificare i valori numerici sottostanti eseguendo il cast al tipo sottostante, come illustrato nell'esempio seguente.

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

I vantaggi dell'uso di enum anziché di un tipo numerico sono i seguenti:

- Si specifica in modo chiaro per il codice client quali sono i valori validi per la variabile.

- In Visual Studio IntelliSense elenca i valori definiti.

Quando non si specificano valori per gli elementi nell'elenco di enumeratori, i valori vengono incrementati automaticamente di 1. Nell'esempio precedente, `Day.Sunday` ha valore 0, `Day.Monday` ha valore 1 e così via. Quando si crea un nuovo oggetto `Day`, se a questo non si assegna un valore in modo esplicito, l'oggetto avrà il valore predefinito `Day.Sunday` (0). Quando si crea un enum, selezionare il valore predefinito più logico e assegnare a questo un valore pari a zero. In tal modo tutti gli enum avranno quel valore predefinito, se non è stato loro assegnato un valore in modo esplicito al momento della creazione.

Se la variabile `meetingDay` è di tipo `Day`, è possibile assegnare (senza un cast esplicito) solo uno dei valori definiti da `Day`. E se il giorno della riunione cambia, è possibile assegnare un nuovo valore da `Day` a `meetingDay`:

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> È possibile assegnare a `meetingDay` qualsiasi valore intero arbitrario. Ad esempio, questa riga di codice non genera un errore: `meetingDay = (Day) 42`. Questa impostazione, tuttavia, non è consigliabile perché l'aspettativa implicita è che una variabile enum contenga solo uno dei valori definiti dal tipo enum. L'assegnazione di un valore arbitrario a una variabile di tipo enum comporta un rischio elevato di errore.

È possibile assegnare qualsiasi valore agli elementi nell'elenco di enumeratori di un tipo di enumerazione ed è anche possibile usare valori calcolati:

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a>Tipi di enumerazione come flag di bit

È possibile usare un tipo di enumerazione per definire flag di bit, che consentono a un'istanza del tipo di enumerazione di archiviare qualsiasi combinazione dei valori definiti nell'elenco di enumeratori. Naturalmente alcune combinazioni potrebbero non essere significative o consentite nel codice del programma.

Un enum di flag di bit viene creato applicando l'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType> e definendo in modo appropriato i valori in modo che sia possibile eseguirvi operazioni bit per bit `AND`, `OR`, `NOT` e `XOR`. In un enum di flag di bit, includere una costante denominata con valore zero, che indica che non sono impostati flag. Assegnare a un flag un valore pari a zero solo per indicare che non sono impostati flag.

Nell'esempio seguente viene definita un'altra versione dell'enum `Day` denominata `Days`. `Days` dispone dell'attributo `Flags`. A ogni valore viene assegnata la successiva potenza di 2. In questo modo è possibile creare una variabile `Days` il cui valore è `Days.Tuesday | Days.Thursday`.

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

Per impostare un flag su un enum, usare l'operatore `OR` bit per bit come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

Per determinare se un flag specifico è impostato, usare l'operatore `AND` bit per bit come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

Per altre informazioni sugli aspetti da considerare quando si definiscono tipi di enumerazione con l'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType>, vedere <xref:System.Enum?displayProperty=nameWithType>.

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Uso dei metodi System.Enum per individuare e modificare valori enum

Tutti gli enum sono istanze del tipo <xref:System.Enum?displayProperty=nameWithType>. Non è possibile derivare nuove classi da <xref:System.Enum?displayProperty=nameWithType>, ma è possibile usarne i metodi per individuare informazioni e modificare valori in un'istanza dell'enum.

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

Per ulteriori informazioni, vedere <xref:System.Enum?displayProperty=nameWithType>.

È anche possibile creare un nuovo metodo per un enum tramite un metodo di estensione. Per ulteriori informazioni, vedere [come creare un nuovo metodo per un'enumerazione](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Enum?displayProperty=nameWithType>
- [Guida per programmatori C#](./index.md)
- [enum](../language-reference/keywords/enum.md)
