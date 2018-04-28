---
title: Tipi di raccolta F#
description: 'Informazioni sui tipi di raccolta F # e le differenze rispetto ai tipi di raccolte in .NET Framework.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0baad5bdf88e8f381240b822a3f6132898dc9ff9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="f-collection-types"></a>Tipi di raccolta F#

Esaminando questo argomento, è possibile determinare quale F # raccolta tipo più adatto a una particolare esigenza. Questi tipi di raccolta sono diversi dai tipi di raccolte in .NET Framework, ad esempio quelli di `System.Collections.Generic` dello spazio dei nomi, in quanto i tipi di raccolta F # sono progettati da una prospettiva di programmazione funzionale piuttosto che da una prospettiva orientata agli oggetti. In particolare, solo la raccolta di matrice contiene elementi modificabili. Pertanto, quando si modifica una raccolta, creare un'istanza della raccolta modificata anziché la modifica della raccolta originale.

Il tipo di struttura di data in cui sono archiviati gli oggetti risultano diverse anche i tipi di raccolta. Strutture di dati, ad esempio tabelle hash, elenchi collegati e le matrici hanno diverse caratteristiche di prestazione e un set diverso di operazioni disponibili.


## <a name="f-collection-types"></a>Tipi di raccolta F#
La tabella seguente illustra i tipi di raccolta F #.



|Tipo|Descrizione|Collegamenti correlati|
|----|-----------|-------------|
|[List](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Una serie ordinata e non modificabile di elementi dello stesso tipo. Implementato come un elenco collegato.|[Elenchi](lists.md)<br /><br />[Modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Matrice](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Una raccolta di elementi di dati consecutivi che sono tutti dello stesso tipo a dimensione fissa, in base zero e modificabile.|[Array](arrays.md)<br /><br />[Modulo Array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Modulo Array2D](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Modulo Array3D](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Una serie logica di elementi che sono dello stesso tipo. Le sequenze sono particolarmente utili quando si dispone di grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevede di utilizzare tutti gli elementi. Sequenza di singoli elementi vengono calcolati solo se necessario, pertanto una sequenza può risultare più efficace rispetto a un elenco se non vengono utilizzati tutti gli elementi. Le sequenze vengono rappresentate dal `seq<'T>` tipo, ovvero un alias per `IEnumerable<T>`. Pertanto, qualsiasi tipo di .NET Framework che implementa `System.Collections.Generic.IEnumerable<'T>` può essere utilizzato come una sequenza.|[Sequenze](sequences.md)<br /><br />[Modulo Seq](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[mappa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Un dizionario non modificabile di elementi. Gli elementi sono accessibili per chiave.|[Eseguire il mapping di modulo](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Un set non modificabile basato su strutture ad albero binario, in cui il confronto è la funzione di confronto strutturale F #, che potenzialmente utilizza le implementazioni del `System.IComparable` interfaccia sui valori di chiave.|[Impostare il modulo](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabella di funzioni
Questa sezione vengono confrontate le funzioni che sono disponibili per i tipi di raccolta F #. La complessità del calcolo della funzione viene fornita, dove N è la dimensione della prima raccolta e M è la dimensione della seconda raccolta, se presente. Un trattino (-) indica che questa funzione non è disponibile nell'insieme. Poiché le sequenze vengono valutate in modo differito, una funzione, ad esempio SEQ potrebbe essere o (1) poiché viene restituito immediatamente, anche se ancora le prestazioni di sequenza quando enumerata.



|Funzione|Matrice|List|Sequence|Mappa|Imposta|Descrizione|
|--------|-----|----|--------|---|---|-----------|
|append|O(M)|O (N)|O (N)|-|-|Restituisce una nuova raccolta che contiene gli elementi della prima raccolta seguiti dagli elementi della seconda raccolta.|
|aggiunta|-|-|-|O (log N)|O (log N)|Restituisce una nuova raccolta con l'elemento aggiunto.|
|Media|O (N)|O (N)|O (N)|-|-|Restituisce la media degli elementi nella raccolta.|
|averageBy|O (N)|O (N)|O (N)|-|-|Restituisce la media dei risultati della funzione specificato applicato a ogni elemento.|
|blit|O (N)|-|-|-|-|Copia una sezione di una matrice.|
|cache|-|-|O (N)|-|-|Calcola e archivia gli elementi di una sequenza.|
|cast|-|-|O (N)|-|-|Converte gli elementi nel tipo specificato.|
|Scegliere|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata `f` a ogni elemento `x` dell'elenco. Restituisce l'elenco che contiene i risultati per ogni elemento in cui la funzione restituisce `Some(f(x))`.|
|raccogliere|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata a ogni elemento della raccolta, concatena tutti i risultati e restituisce l'elenco combinato.|
|compareWith|-|-|O (N)|-|-|Confronta due sequenze tramite la funzione di confronto specificata, elemento per elemento.|
|concat|O (N)|O (N)|O (N)|-|-|Combina l'enumerazione di enumerazioni specificata come un'unica enumerazione concatenata.|
|contiene|-|-|-|-|O (log N)|Restituisce true se il set contiene l'elemento specificato.|
|containsKey|-|-|-|O (log N)|-|Verifica se un elemento si trova nel dominio di una mappa.|
|count|-|-|-|-|O (N)|Restituisce il numero di elementi nel set.|
|countBy|-|-|O (N)|-|-|Applica una funzione di generazione chiavi a ogni elemento di una sequenza e restituisce una sequenza che produce chiavi univoche e il relativo numero di occorrenze nella sequenza originale.|
|copy|O (N)|-|O (N)|-|-|Copia la raccolta.|
|creazione|O (N)|-|-|-|-|Crea una matrice di interi elementi che sono inizialmente il valore specificato.|
|ritardo|-|-|O(1)|-|-|Restituisce una sequenza che viene compilata dalla specifica ritardata specificata di una sequenza.|
|differenza|-|-|-|-|O (M &#42; log N)|Restituisce un nuovo set con gli elementi del secondo insieme rimossi dal primo set.|
|DISTINCT|||O (1)&AMP;#42;|||Restituisce una sequenza che non contiene voci duplicate in base ai confronti di uguaglianza e di hash generici sulle voci. Se un elemento è presente più volte nella sequenza, occorrenze successive vengono ignorate.|
|distinctBy|||O (1)&AMP;#42;|||Restituisce una sequenza che non contiene voci duplicate in base ai confronti di uguaglianza e hash generici alle chiavi che restituisce la funzione di generazione di chiavi specificata. Se un elemento è presente più volte nella sequenza, occorrenze successive vengono ignorate.|
|vuoto|O(1)|O(1)|O(1)|O(1)|O(1)|Crea una raccolta vuota.|
|exists|O (N)|O (N)|O (N)|O (log N)|O (log N)|Controlla se qualsiasi elemento della sequenza soddisfa il predicato specificato.|
|exists2|O(min(N,M))|-|O(min(N,M))|||Controlla se qualsiasi coppia di elementi corrispondenti di sequenze di input soddisfa il predicato specificato.|
|fill|O (N)|||||Imposta un intervallo di elementi della matrice sul valore specificato.|
|filtro|O (N)|O (N)|O (N)|O (N)|O (N)|Restituisce una nuova raccolta che contiene solo gli elementi della raccolta per cui il predicato specificato restituisce `true`.|
|find|O (N)|O (N)|O (N)|O (log N)|-|Restituisce il primo elemento per cui la funzione specificata restituisce `true`. Restituisce `System.Collections.Generic.KeyNotFoundException` se tale elemento non esiste.|
|findIndex|O (N)|O (N)|O (N)|-|-|Restituisce l'indice del primo elemento nella matrice che soddisfa il predicato specificato. Genera `System.Collections.Generic.KeyNotFoundException` se nessun elemento soddisfa il predicato.|
|findKey|-|-|-|O (log N)|-|Valuta la funzione su ogni mapping nella raccolta e restituisce la chiave per il primo mapping in cui la funzione restituisce `true`. Se tale elemento non esiste, questa funzione genera `System.Collections.Generic.KeyNotFoundException`.|
|riduzione|O (N)|O (N)|O (N)|O (N)|O (N)|Applica una funzione a ogni elemento della raccolta di threading di un argomento dell'accumulatore nel calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola f (... (f s i0)...) iN.|
|fold2|O (N)|O (N)|-|-|-|Applica una funzione per gli elementi corrispondenti di due raccolte, threading di un argomento dell'accumulatore nel calcolo. Le raccolte devono essere identiche dimensioni. Se la funzione di input è f e gli elementi sono i0... e j0... jN, questa funzione Calcola f (... (f s i0 j0)...) iN jN.|
|foldBack|O (N)|O (N)|-|O (N)|O (N)|Applica una funzione a ogni elemento della raccolta di threading di un argomento dell'accumulatore nel calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola i0 f (... (f iN s)).|
|foldBack2|O (N)|O (N)|-|-|-|Applica una funzione per gli elementi corrispondenti di due raccolte, threading di un argomento dell'accumulatore nel calcolo. Le raccolte devono essere identiche dimensioni. Se la funzione di input è f e gli elementi sono i0... e j0... jN, questa funzione Calcola f i0 j0 (... (f jN s)).|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|Verifica se tutti gli elementi della raccolta soddisfano il predicato specificato.|
|forall2|O (N)|O (N)|O (N)|-|-|Verifica se tutti gli elementi corrispondenti della raccolta soddisfano il predicato specificato pairwise.|
|ottenere / ennesimo|O(1)|O (N)|O (N)|-|-|Restituisce un elemento dalla raccolta di base al relativo indice.|
|head|-|O(1)|O(1)|-|-|Restituisce il primo elemento della raccolta.|
|init|O (N)|O (N)|O(1)|-|-|Crea una raccolta di dati della dimensione e una funzione generatore per calcolare gli elementi.|
|initInfinite|-|-|O(1)|-|-|Genera una sequenza che, se iterata, restituisce gli elementi successivi chiamando la funzione specificata.|
|Si intersecano|-|-|-|-|O (log N &#42; log M)|Calcola l'intersezione di due set.|
|intersectMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcola l'intersezione di una sequenza di set. La sequenza non deve essere vuota.|
|IsEmpty|O(1)|O(1)|O(1)|O(1)|-|Restituisce `true` se la raccolta è vuota.|
|isProperSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono nel secondo set e non è presente almeno un elemento del secondo set nel primo set.|
|isProperSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono nel primo set e non è presente almeno un elemento del primo set nel secondo set.|
|isSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono nel secondo set.|
|isSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono nel primo set.|
|iter|O (N)|O (N)|O (N)|O (N)|O (N)|Applica la funzione specificata a ogni elemento della raccolta.|
|iteri|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata a ogni elemento della raccolta. Il valore integer che viene passato alla funzione indica l'indice dell'elemento.|
|iteri2|O (N)|O (N)|-|-|-|Applica la funzione specificata a una coppia di elementi da cui vengono prelevati indici corrispondenti in due matrici. Il valore integer che viene passato alla funzione indica l'indice degli elementi. Le due matrici devono avere la stessa lunghezza.|
|iter2|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata a una coppia di elementi da cui vengono prelevati indici corrispondenti in due matrici. Le due matrici devono avere la stessa lunghezza.|
|length|O(1)|O (N)|O (N)|-|-|Restituisce il numero di elementi nella raccolta.|
|map|O (N)|O (N)|O(1)|-|-|Crea una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata a ogni elemento della matrice.|
|map2|O (N)|O (N)|O(1)|-|-|Crea una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata per gli elementi corrispondenti di due raccolte pairwise. Le due matrici di input devono avere la stessa lunghezza.|
|map3|-|O (N)|-|-|-|Crea una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata per gli elementi corrispondenti di tre raccolte contemporaneamente.|
|MAPI|O (N)|O (N)|O (N)|-|-|Crea una matrice i cui elementi sono il risultato ottenuto applicando la funzione specificata a ogni elemento della matrice. Indice di tipo integer che viene passato alla funzione indica l'indice dell'elemento che viene trasformato.|
|mapi2|O (N)|O (N)|-|-|-|Crea una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata per gli elementi corrispondenti di due raccolte pairwise, passando l'indice degli elementi. Le due matrici di input devono avere la stessa lunghezza.|
|max|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento massimo nella raccolta, confrontata utilizzando il [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) operatore.|
|maxBy|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento massimo nella raccolta, confrontata utilizzando [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) nel risultato della funzione.|
|maxElement|-|-|-|-|O (log N)|Restituisce l'elemento massimo nel set in base all'ordine che viene utilizzato per il set.|
|min|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento almeno in una raccolta, confrontata utilizzando il [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operatore.|
|minBy|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento almeno in una raccolta, confrontata utilizzando il [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operatore nel risultato della funzione.|
|minElement|-|-|-|-|O (log N)|Restituisce l'elemento più basso nel set in base all'ordine che viene utilizzato per il set.|
|ofArray|-|O (N)|O(1)|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi della matrice specificata.|
|ofList|O (N)|-|O(1)|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi dell'elenco specificato.|
|ofSeq|O (N)|O (N)|-|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi della sequenza specificata.|
|pairwise|-|-|O (N)|-|-|Restituisce una sequenza di ogni elemento nella sequenza di input e il suo predecessore, ad eccezione del primo elemento, che viene restituito solo come predecessore del secondo elemento.|
|partition|O (N)|O (N)|-|O (N)|O (N)|Divide l'insieme in due raccolte. La prima raccolta contiene gli elementi per cui il predicato specificato restituisce `true`, e la seconda raccolta contiene gli elementi per cui il predicato specificato restituisce `false`.|
|permute)|O (N)|O (N)|-|-|-|Restituisce una matrice con tutti gli elementi permutati secondo la permutazione specificata.|
|selezione|O (N)|O (N)|O (N)|O (log N)|-|Applica la funzione specificata a elementi consecutivi, restituendo il primo risultato in cui la funzione restituisce alcuni. Se la funzione non restituisce mai alcuni, `System.Collections.Generic.KeyNotFoundException` viene generato.|
|readonly|-|-|O (N)|-|-|Crea un oggetto di sequenza che delega per l'oggetto sequenza specificata. Questa operazione garantisce che un cast di tipo non è possibile rilevare e modificare la sequenza originale. Ad esempio, se una matrice, la sequenza restituita restituirà gli elementi della matrice, ma non è possibile convertire l'oggetto sequenza restituita in una matrice.|
|reduce|O (N)|O (N)|O (N)|-|-|Applica una funzione a ogni elemento della raccolta di threading di un argomento dell'accumulatore nel calcolo. Questa funzione viene avviato applicando la funzione per i primi due elementi, passa il risultato nella funzione con il terzo elemento e così via. La funzione restituisce il risultato finale.|
|reduceBack|O (N)|O (N)|-|-|-|Applica una funzione a ogni elemento della raccolta di threading di un argomento dell'accumulatore nel calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola i0 f (... (f iN-1 iN)).|
|remove|-|-|-|O (log N)|O (log N)|Rimuove un elemento dal dominio della mappa. Se l'elemento non è presente, viene generata alcuna eccezione.|
|La replica|-|O (N)|-|-|-|Crea un elenco di lunghezza specificata con ogni elemento impostata sul valore specificato.|
|REV|O (N)|O (N)|-|-|-|Restituisce un nuovo elenco con gli elementi in ordine inverso.|
|analisi|O (N)|O (N)|O (N)|-|-|Applica una funzione a ogni elemento della raccolta di threading di un argomento dell'accumulatore nel calcolo. Questa operazione si applica la funzione per il secondo argomento e il primo elemento dell'elenco. L'operazione quindi passa il risultato nella funzione con il secondo elemento e così via. Infine, l'operazione restituisce l'elenco dei risultati intermedi e il risultato finale.|
|scanBack|O (N)|O (N)|-|-|-|L'operazione foldBack è simile ma restituisce i risultati intermedi e finali.|
|Singleton|-|-|O(1)|-|O(1)|Restituisce una sequenza che produce un solo elemento.|
|set|O(1)|-|-|-|-|Imposta un elemento di una matrice sul valore specificato.|
|skip|-|-|O (N)|-|-|Restituisce una sequenza che ignora N elementi della sequenza sottostante e quindi restituisce gli elementi rimanenti della sequenza.|
|skipWhile|-|-|O (N)|-|-|Restituisce una sequenza che, se iterata, ignora gli elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e quindi restituisce gli elementi rimanenti della sequenza.|
|sort|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|O (N log N)|-|-|Ordina la raccolta dal valore dell'elemento. Gli elementi vengono confrontati tramite [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|O (N log N)|-|-|Ordina l'elenco specificato utilizzando i tasti che fornisce la proiezione specificata. Le chiavi vengono confrontate mediante [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi di una matrice, di modifica sul posto e utilizzando la funzione di confronto specificato. Gli elementi vengono confrontati tramite [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi di una matrice, di modifica sul posto e utilizzando la proiezione specificata per le chiavi. Gli elementi vengono confrontati tramite [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi di una matrice, di modifica sul posto e utilizzando la funzione di confronto specificato come l'ordine.|
|sortWith|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|-|-|-|Ordina gli elementi di una raccolta, utilizzare la funzione di confronto specificato come l'ordine e restituire una nuova raccolta.|
|sub|O (N)|-|-|-|-|Crea una matrice che contiene l'intervallo secondario fornito specificato dall'indice iniziale e lunghezza.|
|sum|O (N)|O (N)|O (N)|-|-|Restituisce la somma degli elementi nella raccolta.|
|sumBy|O (N)|O (N)|O (N)|-|-|Restituisce la somma dei risultati generati applicando la funzione a ogni elemento della raccolta.|
|Coda|-|O(1)|-|-|-|Restituisce l'elenco senza il primo elemento.|
|Take|-|-|O (N)|-|-|Restituisce gli elementi della sequenza fino a un numero specificato.|
|takeWhile|-|-|O(1)|-|-|Restituisce una sequenza che, se iterata, produce gli elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e quindi non restituisce più elementi.|
|ToArray|-|O (N)|O (N)|O (N)|O (N)|Crea una matrice dalla raccolta specificata.|
|ToList|O (N)|-|O (N)|O (N)|O (N)|Crea un elenco dalla raccolta specificata.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Crea una sequenza dalla raccolta specificata.|
|troncare|-|-|O(1)|-|-|Restituisce una sequenza che, quando enumerata, restituisce non più di N elementi.|
|tryFind|O (N)|O (N)|O (N)|O (log N)|-|Cerca un elemento che soddisfa un predicato specificato.|
|tryFindIndex|O (N)|O (N)|O (N)|-|-|Cerca il primo elemento che soddisfa un predicato specificato e restituisce l'indice dell'elemento corrispondente, o `None` se tale elemento non esiste.|
|tryFindKey|-|-|-|O (log N)|-|Restituisce la chiave del primo mapping della raccolta che soddisfa il predicato specificato o restituisce `None` se tale elemento non esiste.|
|tryPick|O (N)|O (N)|O (N)|O (log N)|-|Applica la funzione specificata a elementi consecutivi, restituendo il primo risultato in cui la funzione restituisce `Some` per alcuni valori. Se tale elemento non esiste, l'operazione restituisce `None`.|
|Espandi|-|-|O (N)|-|-|Restituisce una sequenza che contiene gli elementi generati dal calcolo specificato.|
|union|-|-|-|-|O (M &#42; log N)|Calcola l'unione di due set.|
|unionMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcola l'unione di una sequenza di set.|
|unzip|O (N)|O (N)|O (N)|-|-|Divide un elenco di coppie in due elenchi.|
|unzip3|O (N)|O (N)|O (N)|-|-|Divide un elenco di Triple in tre elenchi.|
|finestre|-|-|O (N)|-|-|Restituisce una sequenza che produce finestre temporali scorrevoli del contenente gli elementi che vengono disegnati dalla sequenza di input. Ogni finestra viene restituita come nuova matrice.|
|Codice postale|O (N)|O (N)|O (N)|-|-|Combina due raccolte in un elenco di coppie. I due elenchi lunghezza devono essere uguale.|
|zip3|O (N)|O (N)|O (N)|-|-|Combina tre raccolte in un elenco di Triple. Gli elenchi di lunghezza devono essere uguale.|

## <a name="see-also"></a>Vedere anche
[Tipi F#](fsharp-types.md)

[Riferimenti per il linguaggio F#](index.md)

