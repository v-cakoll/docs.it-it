---
title: Cast e conversioni (F#)
description: 'Informazioni su come il linguaggio di programmazione F # fornisce gli operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 410c7da2b7ae8a09c58e8c89b24d0093a7f33a5c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="casting-and-conversions-f"></a>Cast e conversioni (F#)

In questo argomento viene descritto il supporto per le conversioni in F #.

## <a name="arithmetic-types"></a>Tipi aritmetici
F # fornisce gli operatori di conversione per le conversioni aritmetiche tra diversi tipi di primitivi, ad esempio integer e tipi a virgola mobile. Gli operatori di conversione integrale e char sono controllati e form non è selezionato. operatori di virgola mobile e `enum` non operatore di conversione. I moduli non controllati vengono definiti in `Microsoft.FSharp.Core.Operators` e i moduli selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`. I moduli selezionati, verificare la presenza di overflow e generano un'eccezione in fase di esecuzione se il valore risultante supera i limiti del tipo di destinazione.

Ognuno di questi operatori ha lo stesso nome come nome del tipo di destinazione. Ad esempio, nel codice seguente, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi. La prima occorrenza è il tipo e il secondo è l'operatore di conversione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

La tabella seguente illustra gli operatori di conversione definiti in F #.

|Operatore|Descrizione|
|--------|-----------|
|`byte`|Conversione in byte, un tipo senza segno a 8 bit.|
|`sbyte`|Convertire i byte con segno.|
|`int16`|Convertire in un intero con segno a 16 bit.|
|`uint16`|Convertire in un intero senza segno a 16 bit.|
|`int32, int`|Convertire in un intero con segno a 32 bit.|
|`uint32`|Convertire in un intero senza segno a 32 bit.|
|`int64`|Convertire in un intero con segno a 64 bit.|
|`uint64`|Convertire in un intero senza segno a 64 bit.|
|`nativeint`|Convertire un valore intero nativa.|
|`unativeint`|Convertire in un intero senza segno nativo.|
|`float, double`|Convertire un IEEE a precisione doppia a 64 bit numero a virgola mobile.|
|`float32, single`|Convertire un IEEE a 32 bit a precisione singola numero a virgola mobile.|
|`decimal`|Convertire `System.Decimal`.|
|`char`|Converti in `System.Char`, un carattere Unicode.|
|`enum`|Convertire un tipo enumerato.|
Oltre ai tipi primitivi incorporati, è possibile utilizzare questi operatori con tipi che implementano `op_Explicit` o `op_Implicit` metodi con firme appropriate. Ad esempio, il `int` operatore di conversione funziona con qualsiasi tipo che fornisce un metodo statico `op_Explicit` che accetta il tipo come parametro e restituisce `int`. Come un'eccezione speciale per la regola generale, che non è possibile eseguirne l'overload per il tipo restituito, è possibile eseguire questa operazione per `op_Explicit` e `op_Implicit`.

## <a name="enumerated-types"></a>Tipi enumerati
Il `enum` è un operatore generico che accetta un parametro di tipo che rappresenta il tipo del `enum` da convertire. Durante la conversione nel tipo enumerato, digitare l'inferenza del tipo di tentativi per determinare il tipo del `enum` che si desidera convertire. Nell'esempio seguente, la variabile `col1` non è annotato in modo esplicito, ma il relativo tipo è derivato dal test di uguaglianza successivo. Pertanto, il compilatore può dedurre che si desidera convertire in un `Color` enumerazione. In alternativa, è possibile fornire un'annotazione di tipo, come con `col2` nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
È inoltre possibile specificare il tipo di enumerazione di destinazione in modo esplicito come un parametro di tipo, come illustrato nel codice seguente:

```fsharp
let col3 = enum<Color> 3
```

Si noti che l'enumerazione esegue il cast di lavoro solo se il tipo sottostante dell'enumerazione è compatibile con il tipo da convertire. Nel codice seguente, la conversione non riesce a compilare a causa della mancata corrispondenza tra `int32` e `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Per ulteriori informazioni, vedere [enumerazioni](enumerations.md).

## <a name="casting-object-types"></a>Il cast dei tipi di oggetto
Conversione tra tipi di una gerarchia di oggetti è fondamentale per la programmazione orientata agli oggetti. Esistono due tipi di conversioni: cast di backup (upcast) e cast verso il basso (downcast). Eseguire il cast di una gerarchia indica il cast da un riferimento di oggetto derivato da un riferimento all'oggetto di base. Questo cast è garantito per funzionare, purché sia la classe di base nella gerarchia di ereditarietà della classe derivata. In una gerarchia, da un riferimento di oggetto di base a un oggetto derivata, esegue il cast ha esito positivo solo se l'oggetto è in realtà di un'istanza del tipo di destinazione corretto (derivato) o un tipo derivato dal tipo di destinazione.

F # fornisce gli operatori per questi tipi di conversioni. Il `:>` superiore nella gerarchia, esegue il cast di operatore e `:?>` esegue il cast operatore inferiori della gerarchia.

### <a name="upcasting"></a>Upcast
In molti linguaggi orientata agli oggetti, è implicita; upcast in F #, le regole sono leggermente diverse. Upcast viene eseguito automaticamente quando si passano argomenti ai metodi del tipo di oggetto. Tuttavia, per le funzioni consentono di associazione in un modulo, l'upcast non è automatica, a meno che il tipo di parametro è dichiarato come tipo flessibile. Per ulteriori informazioni, vedere [tipi flessibili](flexible-Types.md).

Il `:>` operatore esegue un cast statico, il che significa che la riuscita del cast viene determinata in fase di compilazione. Se un cast che utilizza `:>` viene compilato correttamente, un cast valido ed non è alcuna possibilità di errore in fase di esecuzione.

È inoltre possibile utilizzare il `upcast` operatore per eseguire la conversione. L'espressione seguente specifica una conversione nella gerarchia:

```fsharp
upcast expression
```

Quando si utilizza l'upcast (operatore), il compilatore prova a dedurre il tipo che si sta convertendo dal contesto. Se il compilatore è in grado di determinare il tipo di destinazione, il compilatore segnala un errore.

### <a name="downcasting"></a>Downcast
Il `:?>` operatore esegue un cast dinamico, il che significa che la riuscita del cast viene determinata in fase di esecuzione. Un cast che utilizza il `:?>` operatore non viene controllato in fase di compilazione; ma in fase di esecuzione, viene effettuato un tentativo di eseguire il cast al tipo specificato. Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo. Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera un `InvalidCastException`.

È inoltre possibile utilizzare il `downcast` operatore per eseguire una conversione di tipo dinamico. L'espressione seguente specifica una conversione verso il basso della gerarchia a un tipo viene dedotto dal contesto di programma:

```fsharp
downcast expression
```

Come per il `upcast` (operatore), se il compilatore non è possibile dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore.

Il codice seguente viene illustrato l'utilizzo del `:>` e `:?>` operatori. Il codice viene illustrato che il `:?>` operatore viene utilizzato meglio quando si è certi che la conversione avrà esito positivo, perché genera `InvalidCastException` se la conversione non riesce. Se non si conosce che una conversione avrà esito positivo, un test del tipo che utilizza un `match` espressione è migliore in quanto evita l'overhead della generazione di un'eccezione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Poiché gli operatori generici `downcast` e `upcast` basarsi sull'inferenza del tipo per determinare il tipo di argomenti e valori restituiti nel codice precedente, è possibile sostituire

```fsharp
let base1 = d1 :> Base1
```

con

```fsharp
let base1 = upcast d1
```

Nel codice precedente, il tipo di argomento e tipi restituiti sono `Derived1` e `Base1`, rispettivamente.

Per ulteriori informazioni sui test del tipo, vedere [espressioni Match](match-Expressions.md).

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
