---
title: Cast e conversioni (F#)
description: 'Informazioni su come il linguaggio di programmazione F # offre operatori di conversione per le conversioni aritmetiche tra vari tipi primitivi.'
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508391"
---
# <a name="casting-and-conversions-f"></a>Cast e conversioni (F#)

In questo argomento viene descritto il supporto per le conversioni di tipo in F #.

## <a name="arithmetic-types"></a>Tipi aritmetici

F # fornisce gli operatori di conversione per le conversioni aritmetiche tra vari tipi di primitivi, ad esempio tra valori interi e tipi a virgola mobile. Gli operatori di conversione integrale e char sono stati verificati e form unchecked; gli operatori della virgola mobile e `enum` operatore di conversione non lo sono. I moduli deselezionati vengono definiti in `Microsoft.FSharp.Core.Operators` e i moduli selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`. I moduli selezionati verificare la presenza di overflow e generano un'eccezione di runtime se il valore risultante supera i limiti del tipo di destinazione.

Ognuno di questi operatori ha lo stesso nome come nome del tipo di destinazione. Ad esempio, nel codice seguente, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi. La prima occorrenza è il tipo e il secondo è l'operatore di conversione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

La tabella seguente illustra gli operatori di conversione definiti in F #.

|Operatore|Descrizione|
|--------|-----------|
|`byte`|Converte in byte, un tipo senza segno a 8 bit.|
|`sbyte`|Converte in byte con segno.|
|`int16`|Convertire in un intero con segno a 16 bit.|
|`uint16`|Convertire in un intero senza segno a 16 bit.|
|`int32, int`|Convertire in un intero con segno a 32 bit.|
|`uint32`|Convertire in un intero senza segno a 32 bit.|
|`int64`|Convertire in un intero con segno a 64 bit.|
|`uint64`|Convertire in un intero senza segno a 64 bit.|
|`nativeint`|Converte in un integer nativo.|
|`unativeint`|Convertire in un unsigned integer nativo.|
|`float, double`|Convertire un IEEE a precisione doppia a 64 bit numero a virgola mobile.|
|`float32, single`|Convertire un IEEE a 32 bit con precisione singola numero a virgola mobile.|
|`decimal`|Converti in `System.Decimal`.|
|`char`|Converti in `System.Char`, un carattere Unicode.|
|`enum`|Convertire in un tipo enumerato.|
Oltre ai tipi primitivi incorporati, è possibile usare questi operatori con i tipi che implementano `op_Explicit` o `op_Implicit` metodi con firme appropriate. Ad esempio, il `int` operatore di conversione funziona con qualsiasi tipo che fornisce un metodo statico `op_Explicit` che accetta il tipo come parametro e restituisce `int`. Come eccezione speciale per la regola generale che non possono essere sottoposti a overload di metodi per il tipo restituito, è possibile farlo `op_Explicit` e `op_Implicit`.

## <a name="enumerated-types"></a>Tipi enumerati

Il `enum` è un operatore di tipo generico che accetta un parametro di tipo che rappresenta il tipo del `enum` da convertire in. Quando converte un tipo enumerato, digitare l'inferenza tenta di determinare il tipo del `enum` che si desidera convertire. Nell'esempio seguente, la variabile `col1` non è annotato in modo esplicito, ma il relativo tipo viene dedotto dal test di uguaglianza più avanti. Pertanto, il compilatore può dedurre che si desidera convertire in un `Color` enumerazione. In alternativa, è possibile fornire un'annotazione di tipo, come con `col2` nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

È anche possibile specificare il tipo di enumerazione di destinazione in modo esplicito come un parametro di tipo, come nel codice seguente:

```fsharp
let col3 = enum<Color> 3
```

Si noti che l'enumerazione esegue il cast di lavoro solo se il tipo sottostante dell'enumerazione è compatibile con il tipo da convertire. Nel codice seguente, la conversione ha esito negativo per la compilazione a causa della mancata corrispondenza tra `int32` e `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Per altre informazioni, vedere [enumerazioni](enumerations.md).

## <a name="casting-object-types"></a>Il cast dei tipi di oggetto

Conversione tra tipi in una gerarchia di oggetti è fondamentale per la programmazione orientata agli oggetti. Esistono due tipi di base delle conversioni: cast backup (l'upcast) e cast verso il basso (downcast). Eseguire il cast di una gerarchia indica che il cast da un riferimento all'oggetto derivato da un riferimento di oggetto di base. Un cast di questo tipo sarà sicuramente funzionante, purché sia la classe di base nella gerarchia di ereditarietà della classe derivata. Il downcast in una gerarchia, da un riferimento di oggetto di base a un riferimento all'oggetto derivato, ha esito positivo solo se l'oggetto è effettivamente un'istanza del tipo corretto di destinazione (derivato) o un tipo derivato dal tipo di destinazione.

F # fornisce operatori per questi tipi di conversioni. Il `:>` viene eseguito il cast operatore nella gerarchia e `:?>` operatore viene eseguito il cast verso il basso della gerarchia.

### <a name="upcasting"></a>Upcast

In molti linguaggi orientate a oggetti, è implicita; l'upcast in F #, le regole sono leggermente diverse. Upcast viene applicata automaticamente quando si passano argomenti ai metodi in un tipo di oggetto. Tuttavia, per le funzioni consentono di associazione in un modulo, l'upcast non è automatica, a meno che il tipo di parametro è dichiarato come tipo flessibile. Per altre informazioni, vedere [tipi flessibili](flexible-Types.md).

Il `:>` operatore esegue un cast statico, che significa che il successo del cast è determinato in fase di compilazione. Se un cast che usa `:>` viene compilato correttamente, è un cast valido e non dispone di alcuna possibilità di errore in fase di esecuzione.

È anche possibile usare il `upcast` operatore per eseguire la conversione. L'espressione seguente specifica una conversione nella gerarchia:

```fsharp
upcast expression
```

Quando si usa l'upcast (operatore), il compilatore prova a dedurre il tipo che si sta convertendo dal contesto. Se il compilatore non riesce a determinare il tipo di destinazione, il compilatore segnala un errore.

### <a name="downcasting"></a>Downcast

Il `:?>` operatore esegue un cast dinamico, il che significa che il successo del cast è determinato in fase di esecuzione. Un cast che utilizza il `:?>` operatore non è selezionato in fase di compilazione; ma in fase di esecuzione, viene effettuato un tentativo di eseguire il cast nel tipo specificato. Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo. Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera un `InvalidCastException`.

È anche possibile usare il `downcast` operatore per eseguire una conversione di tipo dinamico. L'espressione seguente specifica una conversione verso il basso della gerarchia a un tipo viene dedotto dal contesto del programma:

```fsharp
downcast expression
```

Come per il `upcast` (operatore), se il compilatore non è possibile dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore.

Il codice seguente viene illustrato l'utilizzo dei `:>` e `:?>` operatori. Il codice viene illustrato che il `:?>` operatore è più adatta quando si è certi che la conversione avrà esito positivo, perché genera `InvalidCastException` se la conversione non riesce. Se non si conosce che una conversione avrà esito positivo, un tipo test che usa un `match` espressione è preferibile perché evita l'overhead della generazione di un'eccezione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Poiché gli operatori generici `downcast` e `upcast` basarsi sull'inferenza del tipo per determinare il tipo di argomenti e valori restituiti, nel codice precedente, è possibile sostituire

```fsharp
let base1 = d1 :> Base1
```

con

```fsharp
let base1 = upcast d1
```

Nel codice precedente, il tipo di argomento e tipi restituiti sono `Derived1` e `Base1`, rispettivamente.

Per altre informazioni sui test di tipo, vedere [espressioni di ricerca](match-Expressions.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
