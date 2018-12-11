---
title: Direttive per il compilatore (F#)
description: Informazioni su F# le direttive del preprocessore del linguaggio, le direttive di compilazione condizionale, le direttive di riga e direttive del compilatore.
ms.date: 12/10/2018
ms.openlocfilehash: 7344785e37454d367aa4dfcfa1bacd01b68363d5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239696"
---
# <a name="compiler-directives"></a>Direttive per il compilatore

In questo argomento vengono descritte le direttive per il preprocessore e le direttive del compilatore.

## <a name="preprocessor-directives"></a>Direttive per il preprocessore

Una direttiva per il preprocessore è preceduta dal simbolo # e viene visualizzata in una riga da sola. Viene interpretata dal preprocessore, che viene eseguito prima del compilatore stesso.

Nella tabella riportata di seguito sono elencate le direttive per il preprocessore disponibili in F#.

|Direttiva|Descrizione|
|---------|-----------|
|`#if` *Simbolo*|Supporta la compilazione condizionale. Codice nella sezione dopo il `#if` è incluso se il *simbolo* è definito. Il simbolo può essere negato anche con `!`.|
|`#else`|Supporta la compilazione condizionale. Contrassegna una sezione di codice da includere se il simbolo usato nella precedente direttiva `#if` non è definito.|
|`#endif`|Supporta la compilazione condizionale. Contrassegna la fine di una sezione condizionale di codice.|
|`#`[riga] *int*,<br/>`#`[riga] *int* *stringa*,<br/>`#`[riga] *int* *stringa verbatim*|Indica la riga e il nome di file del codice sorgente originale per il debug. Questa funzionalità viene fornita per gli strumenti che generano codice sorgente F#.|
|`#nowarn` *warningcode*|Disabilita un avviso o più avvisi del compilatore. Per disabilitare un avviso, individuare il numero dall'output del compilatore e includerlo tra virgolette. Omettere il prefisso "FS". Per disabilitare più numeri di avviso sulla stessa riga, racchiudere ogni numero tra virgolette e separare ogni stringa con uno spazio. Ad esempio:

`#nowarn "9" "40"`

L'effetto della disabilitazione di un avviso si applica all'intero file, incluse le parti del file che precedono la direttiva. |

## <a name="conditional-compilation-directives"></a>Direttive di compilazione condizionale

Il codice disattivato da una di queste direttive viene visualizzato in grigio nell'Editor di codice di Visual Studio.

> [!NOTE]
> Il comportamento delle direttive di compilazione condizionale non è lo stesso come in altri linguaggi. Ad esempio, è possibile usare espressioni booleane che includono simboli e `true` e `false` non hanno alcun significato speciale. I simboli usati nella direttiva `if` devono essere definiti dalla riga di comando o nelle impostazioni del progetto e non esiste alcuna direttiva per il preprocessore `define`.

Nel codice di esempio che segue viene illustrato l'uso delle direttive `#if`, `#else` e `#endif`. In questo esempio, il codice contiene due versioni della definizione di `function1`. Quando `VERSION1` viene definito tramite il [-define (opzione del compilatore)](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04), il codice tra il `#if` direttiva e il `#else` direttiva è attivata. In caso contrario, viene attivato il codice tra `#else` e `#endif`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

Non esiste alcuna direttiva per il preprocessore `#define` in F#. È necessario usare l'opzione del compilatore o le impostazioni di progetto per definire i simboli usati per la direttiva `#if`.

Le direttive di compilazione condizionale possono essere annidate. Il rientro non è significativo per le direttive per il preprocessore.

È inoltre possibile escludere un simbolo con `!`. In questo esempio, un valore di stringa è un valore solo quando _non_ debug:

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a>Direttive di riga

Durante la compilazione, il compilatore segnala errori nel codice F# facendo riferimento ai numeri di riga in cui si verifica ogni errore. Questi numeri di riga iniziano da 1 per la prima riga in un file. Tuttavia, se si genera codice sorgente F# da un altro strumento, i numeri di riga nel codice generato non sono generalmente di interesse, perché nel codice F# generato probabilmente gli errori sono causati da un'altra origine. La direttiva `#line` consente agli autori di strumenti che generano codice sorgente F# di passare le informazioni relative ai numeri di riga e ai file di origine originali al codice F# generato.

Quando si usa la direttiva `#line`, i nomi di file devono essere racchiusi tra virgolette. A meno che il token verbatim (`@`) venga visualizzato all'inizio della stringa, è necessario eseguire l'escape dei caratteri barra rovesciata usando due barre rovesciate anziché una per poterli usare nel percorso. Di seguito sono riportati dei token di riga validi. In questi esempi si presuppone che il file originale `Script1` risulti in un file di codice F# generato automaticamente quando viene eseguito tramite uno strumento e che il codice nella posizione di tali direttive venga generato dagli stessi token alla riga 25 nel file `Script1`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

Questi token indicano che il codice F# generato in questa posizione è derivato da alcuni costrutti alla riga o vicino alla riga `25` in `Script1`.

## <a name="compiler-directives"></a>Direttive per il compilatore

Le direttive del compilatore sono simili alle direttive per il preprocessore perché sono precedute da un simbolo #, ma anziché essere interpretate dal preprocessore, vengono interpretate dal compilatore.

Nella tabella seguente viene elencata la direttiva del compilatore disponibile in F#.

|Direttiva|Descrizione|
|---------|-----------|
|`#light` ["on"&#124;"off"]|Abilita o disabilita la sintassi leggera per la compatibilità con altre versioni di ML. Per impostazione predefinita, la sintassi leggera è abilitata. La sintassi dettagliata è sempre abilitata. Pertanto, è possibile usare sia sintassi leggera che sintassi dettagliata. La direttiva `#light` da sola equivale a `#light "on"`. Se si specifica `#light "off"`, è necessario usare la sintassi dettagliata per tutti i costrutti del linguaggio. La sintassi nella documentazione per F# viene presentata partendo dal presupposto che venga usata la sintassi leggera. Per altre informazioni, vedere [sintassi dettagliata](verbose-syntax.md).|

Per le direttive dell'interprete (fsi.exe), vedere [programmazione interattiva con F# ](../tutorials/fsharp-interactive/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Opzioni del compilatore](compiler-options.md)
