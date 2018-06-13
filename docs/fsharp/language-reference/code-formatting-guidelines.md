---
title: Linee guida per la formattazione del codice (F#)
description: 'Ulteriori linee guida di formattazione rientro di codice per il linguaggio di programmazione per migliorare la leggibilità, estetica, standardizzazione e compilazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 5bb1f9958a21beb795f9174e44f24c7194453fc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564830"
---
# <a name="code-formatting-guidelines"></a>Linee guida per la formattazione del codice

In questo argomento vengono riepilogate le linee guida rientro di codice per F #. Poiché il linguaggio F # è sensibile alle interruzioni di riga e il rientro, non è semplicemente un problema di migliorare la leggibilità, estetica o problema relativo alla codifica standardizzazione per formattare correttamente il codice. È necessario formattare il codice in modo corretto per la compilazione corretta.


## <a name="general-rules-for-indentation"></a>Regole generali per il rientro
Quando è necessario il rientro, è necessario utilizzare spazi e non tabulazioni. È necessario almeno uno spazio. L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro. tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro è tipico. È possibile configurare Visual Studio in base agli standard di rientro dell'organizzazione, modificando le opzioni nel `Options` nella finestra di dialogo è disponibile il `Tools` menu. Nel `Text Editor` nodo espandere `F#` e quindi fare clic su `Tabs`. Per una descrizione delle opzioni disponibili, vedere [opzioni, Editor di testo, tutti i linguaggi, schede](https://msdn.microsoft.com/library/7sffa753.aspx).

In generale, quando il compilatore analizza il codice, gestisce uno stack interno che indica il livello di nidificazione corrente. Quando il codice viene rientrato, un nuovo livello di nidificazione viene creato o inserito nello stack interno. Al termine di un costrutto viene estratto il livello. Rientro è un modo per segnalare la fine di un livello e pop stack interno, ma anche determinati token comportano il livello da estrarre, ad esempio il `end` (parola chiave), o una parentesi graffa di chiusura o parentesi.

Codice in un costrutto su più righe, ad esempio una definizione di tipo, definizione di funzione, `try...with` costrutto, costrutti di ciclo e, devono essere rientrate rispetto alla riga di apertura del costrutto. La prima riga rientrata definisce una posizione di colonna per il codice successivo nello stesso costrutto. Il livello di rientro viene chiamato un *contesto*. Posizione della colonna imposta una minima della colonna, detta un *riga di offside*, per le successive righe di codice che sono nello stesso contesto. Quando viene rilevata una riga di codice rientro minore rispetto a questa posizione colonna stabilita, il compilatore presuppone che il contesto è stata completata e che il codice si trovi al livello successivo verso l'alto, nel contesto precedente. Il termine *offside* viene utilizzato per descrivere la condizione in cui una riga di codice attiva la fine di un costrutto in quanto il rientro non è sufficiente. In altre parole, codice a sinistra di una riga di offside è offside. Nel codice rientrato correttamente, si sfruttare la regola di offside per definire la fine dei costrutti. Se si utilizza il rientro in modo non corretto, una condizione di offside può causare al compilatore di generare un avviso o può comportare l'errata interpretazione del codice.

Righe di offside vengono determinate come segue.


- Un `=` token associato a un `let` introduce una riga di offside in corrispondenza della colonna del primo token dopo il `=` sign.


- In un `if...then...else` espressione, la posizione colonna del primo token dopo il `then` parola chiave o `else` parola chiave introduce una riga di offside.


- In un `try...with` espressione, il primo token dopo `try` introduce una riga di offside.


- In un `match` espressione, il primo token dopo `with` e il primo token dopo ogni `->` introducono righe di offside.


- Il primo token dopo `with` in un tipo di estensione introduce una riga di offside.


- Il primo token dopo una parentesi o parentesi graffa di apertura o dopo il `begin` (parola chiave), introduce una riga di offside.


- Il primo carattere nelle parole chiave `let`, `if`, e `module` introducono righe di offside.


Gli esempi di codice seguenti illustrano le regole di rientro. In questo caso, le istruzioni print si basano su rientro per la loro associazione con il contesto appropriato. Ogni volta che viene spostato il rientro, il contesto viene estratto e restituisce il contesto precedente. Pertanto, in cui viene stampato uno spazio alla fine di ogni iterazione. "Completata". Poiché il rientro di offside stabilisce che non è parte del ciclo, viene stampato solo una volta. La stampa della stringa "Il contesto di primo livello" non fa parte della funzione. Pertanto, verrà stampato prima, durante l'inizializzazione statica, prima di chiamare la funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

L'output è indicato di seguito.

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

Quando si interrompono le righe lunghe, la continuazione di riga deve essere rientrata un costrutto che lo contiene. Ad esempio, gli argomenti della funzione devono essere impostato un rientro il primo carattere del nome della funzione, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

Esistono eccezioni a queste regole, come descritto nella sezione successiva.


## <a name="indentation-in-modules"></a>Rientro nei moduli
Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma codice in un modulo di livello superiore non deve essere rientrato. Elementi Namespace non è necessario impostare un rientro.

Gli esempi di codice seguenti illustrano questo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

Per ulteriori informazioni, vedere [moduli](modules.md).


## <a name="exceptions-to-the-basic-indentation-rules"></a>Eccezioni alle regole di base di rientro
La regola generale, come descritto nella sezione precedente, è che il codice nei costrutti su più righe deve essere rientrato relativo il rientro della prima riga del costrutto, e che la fine del costrutto è determinata da quando si verifica la prima riga di offside. Un'eccezione alla regola relativa alla fine di contesti fatto che alcuni costrutti, ad esempio il `try...with` espressione, il `if...then...else` espressione e l'utilizzo di `and` sintassi per la dichiarazione di funzioni ricorsive o tipi, che più parti. Ad esempio si impostano i rientri, le parti `then` e `else` in un `if...then...else` espressione, allo stesso livello del token di inizio dell'espressione, ma invece di indicare la fine del contesto, che rappresenta la parte successiva dello stesso contesto. Pertanto, un `if...then...else` espressione può essere scritta come nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

L'eccezione alla regola di offside si applica solo al `then` e `else` parole chiave. Pertanto, sebbene non sia un errore per il rientro di `then` e `else` , inoltre, non riusciti per il rientro alle righe di codice in un `then` blocco genera un avviso. Come illustrato nelle seguenti righe di codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

Per il codice in un `else` blocco, una regola speciale aggiuntiva viene applicato. Nell'esempio precedente l'avviso si verifica solo nel codice nel `then` blocco, non sul codice di `else` blocco. Ciò consente di scrivere codice che verifica la presenza di diverse condizioni all'inizio di una funzione senza forzare il resto del codice per la funzione, che potrebbe essere in un `else` blocco, il rientro. Di conseguenza, è possibile scrivere quanto segue senza generare un avviso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

Un'altra eccezione alla regola che fine dei contesti quando una riga non viene rientrata come una riga precedente viene ad esempio, gli operatori infissi `+` e `|>`. Le righe che iniziano con gli operatori infissi possono iniziare `(1 + oplength)` colonne prima della posizione normale senza attivare la fine del contesto, in cui `oplength` è il numero di caratteri che costituiscono l'operatore. In questo modo il primo token dopo l'operatore per la compatibilità con la riga precedente.

Ad esempio, nel codice seguente, il `+` simbolo può essere rientrate due colonne minore rispetto alla riga precedente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

Sebbene rientro aumenta in genere quando il livello di nidificazione diventa maggiore, vi sono alcuni costrutti in cui il compilatore consente di reimpostare il rientro in una posizione inferiore di colonna.

I costrutti che permettono la reimpostazione della posizione di colonna sono i seguenti:


- Corpi delle funzioni anonime. Nel codice seguente, l'espressione di stampa inizia in una posizione di colonna più a sinistra rispetto di `fun` (parola chiave). Tuttavia, la riga non deve iniziare in una colonna a sinistra dell'inizio del livello di rientro precedente (ovvero, a sinistra del `L` in `List`).
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- Costrutti racchiusi tra parentesi o dalla `begin` e `end` in un `then` o `else` blocco di un `if...then...else` espressione, purché il rientro non minore di posizione della colonna di `if` (parola chiave). Questa eccezione consente di uno stile di codifica in cui una parentesi di apertura o `begin` viene utilizzato alla fine di una riga dopo `then` o `else`.


- Corpi di moduli, classi, interfacce e strutture delimitati da `begin...end`, `{...}`, `class...end`, o `interface...end`. In questo modo per uno stile in cui la parola chiave di apertura di una definizione di tipo può essere sulla stessa riga come nome del tipo senza forzare il corpo intero far rientrare un la parola chiave di apertura.
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
