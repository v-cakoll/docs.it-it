---
title: Cast e conversioni
description: Informazioni su come F# il linguaggio di programmazione fornisce operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi.
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543586"
---
# <a name="casting-and-conversions-f"></a>Cast e conversioni (F#)

In questo argomento viene descritto il supporto per le conversioni di tipi in F#.

## <a name="arithmetic-types"></a>Tipi aritmetici

F#fornisce operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi, ad esempio tra tipi integer e a virgola mobile. Gli operatori di conversione integrale e char hanno form selezionati e non controllati; gli operatori a virgola mobile e l'operatore di conversione `enum` non lo sono. I moduli deselezionati sono definiti in `Microsoft.FSharp.Core.Operators` e i form selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`. I moduli controllati verificano l'overflow e generano un'eccezione in fase di esecuzione se il valore risultante supera i limiti del tipo di destinazione.

Ognuno di questi operatori ha lo stesso nome del nome del tipo di destinazione. Nel codice seguente, ad esempio, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi. La prima occorrenza è il tipo e il secondo è l'operatore di conversione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

Nella tabella seguente vengono illustrati gli operatori F#di conversione definiti in.

|Operatore|Descrizione|
|--------|-----------|
|`byte`|Converte in byte, un tipo senza segno a 8 bit.|
|`sbyte`|Converte in byte con segno.|
|`int16`|Converte in un intero con segno a 16 bit.|
|`uint16`|Convertire in un Unsigned Integer a 16 bit.|
|`int32, int`|Converte in un intero con segno a 32 bit.|
|`uint32`|Convertire in un Unsigned Integer a 32 bit.|
|`int64`|Converte in un intero con segno a 64 bit.|
|`uint64`|Convertire in un Unsigned Integer a 64 bit.|
|`nativeint`|Convertire in un intero nativo.|
|`unativeint`|Convertire in un intero nativo senza segno.|
|`float, double`|Convertire in un numero a virgola mobile IEEE a precisione doppia a 64 bit.|
|`float32, single`|Convertire in un numero a virgola mobile IEEE a precisione singola a 32 bit.|
|`decimal`|Converte in `System.Decimal`.|
|`char`|Converte in `System.Char`, un carattere Unicode.|
|`enum`|Convertire in un tipo enumerato.|

Oltre ai tipi primitivi incorporati, è possibile usare questi operatori con tipi che implementano `op_Explicit` o `op_Implicit` metodi con le firme appropriate. Ad esempio, l'operatore di conversione `int` funziona con qualsiasi tipo che fornisce un metodo statico `op_Explicit` che accetta il tipo come parametro e restituisce `int`. Come eccezione speciale alla regola generale, non è possibile eseguire l'overload dei metodi per tipo restituito, per `op_Explicit` e `op_Implicit`.

## <a name="enumerated-types"></a>Tipi enumerati

L'operatore `enum` è un operatore generico che accetta un parametro di tipo che rappresenta il tipo di `enum` in cui eseguire la conversione. Quando si esegue la conversione in un tipo enumerato, l'inferenza del tipo tenta di determinare il tipo di `enum` in cui si desidera eseguire la conversione. Nell'esempio seguente, la variabile `col1` non è annotata in modo esplicito, ma il tipo viene dedotto dal test di uguaglianza successivo. Pertanto, il compilatore può dedurre che si sta convertendo in un'enumerazione `Color`. In alternativa, è possibile fornire un'annotazione di tipo, come con `col2` nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

È anche possibile specificare il tipo di enumerazione di destinazione in modo esplicito come parametro di tipo, come nel codice seguente:

```fsharp
let col3 = enum<Color> 3
```

Si noti che i cast dell'enumerazione funzionano solo se il tipo sottostante dell'enumerazione è compatibile con il tipo convertito. Nel codice seguente non è possibile compilare la conversione a causa della mancata corrispondenza tra `int32` e `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Per ulteriori informazioni, vedere [enumerazioni](enumerations.md).

## <a name="casting-object-types"></a>Cast di tipi di oggetto

La conversione tra i tipi in una gerarchia di oggetti è fondamentale per la programmazione orientata a oggetti. Sono disponibili due tipi di conversioni di base: il cast (multicast) e il cast verso il basso (downcast). Il cast di una gerarchia implica il cast da un riferimento a un oggetto derivato a un riferimento a un oggetto di base. Un cast di questo tipo può funzionare purché la classe di base si trovi nella gerarchia di ereditarietà della classe derivata. Il cast di una gerarchia, da un riferimento a un oggetto di base a un riferimento a un oggetto derivato, ha esito positivo solo se l'oggetto è effettivamente un'istanza del tipo di destinazione (derivato) corretto o un tipo derivato dal tipo di destinazione.

F#fornisce operatori per questi tipi di conversione. L'operatore `:>` esegue il cast della gerarchia e l'operatore `:?>` esegue il cast della gerarchia.

### <a name="upcasting"></a>Upcast

In molti linguaggi orientati a oggetti, il cast è implicito; in F#le regole sono leggermente diverse. Il multicast viene applicato automaticamente quando si passano argomenti a metodi su un tipo di oggetto. Tuttavia, per le funzioni con binding Let in un modulo, il cast non è automatico, a meno che il tipo di parametro non venga dichiarato come tipo flessibile. Per ulteriori informazioni, vedere [tipi flessibili](flexible-Types.md).

L'operatore `:>` esegue un cast statico, il che significa che la riuscita del cast è determinata in fase di compilazione. Se un cast che utilizza `:>` viene compilato correttamente, si tratta di un cast valido e non ha alcuna possibilità di errore in fase di esecuzione.

È anche possibile usare l'operatore `upcast` per eseguire tale conversione. L'espressione seguente specifica una conversione della gerarchia:

```fsharp
upcast expression
```

Quando si usa l'operatore di cast, il compilatore tenta di dedurre il tipo da cui si esegue la conversione dal contesto. Se il compilatore non è in grado di determinare il tipo di destinazione, il compilatore segnala un errore. Potrebbe essere necessaria un'annotazione di tipo.

### <a name="downcasting"></a>Downcast

L'operatore `:?>` esegue un cast dinamico, il che significa che la riuscita del cast è determinata in fase di esecuzione. Un cast che usa l'operatore `:?>` non viene controllato in fase di compilazione; Tuttavia, in fase di esecuzione, viene eseguito un tentativo di eseguire il cast al tipo specificato. Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo. Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera un'`InvalidCastException`.

È anche possibile usare l'operatore `downcast` per eseguire una conversione dinamica dei tipi. L'espressione seguente specifica una conversione della gerarchia in un tipo dedotto dal contesto del programma:

```fsharp
downcast expression
```

Come per l'operatore `upcast`, se il compilatore non è in grado di dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore. Potrebbe essere necessaria un'annotazione di tipo.

Il codice seguente illustra l'uso degli operatori `:>` e `:?>`. Nel codice viene illustrato che l'operatore `:?>` viene utilizzato meglio quando si è certi che la conversione avrà esito positivo, perché genera `InvalidCastException` se la conversione non riesce. Se non si è certi che la conversione avrà esito positivo, un test di tipo che usa un'espressione `match` è migliore perché evita l'overhead causato dalla generazione di un'eccezione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Poiché gli operatori generici `downcast` e `upcast` si basano sull'inferenza del tipo per determinare l'argomento e il tipo restituito, nel codice precedente, è possibile sostituire

```fsharp
let base1 = d1 :> Base1
```

con

```fsharp
let base1: Base1 = upcast d1
```

Si noti che è necessaria un'annotazione di tipo, poiché `upcast` da solo non è stato in grado di determinare la classe di base.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
