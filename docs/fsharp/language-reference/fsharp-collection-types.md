---
title: Tipi di raccolta F#
description: 'Informazioni sui tipi di raccolta F # e le differenze rispetto ai tipi di raccolte in .NET Framework.'
ms.date: 05/16/2016
ms.openlocfilehash: a3cfc3f06582c31a79dce43b583eca39f69ddf1e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864761"
---
# <a name="f-collection-types"></a>Tipi di raccolta F#

Esaminando questo argomento, è possibile determinare quale tipo F # raccolta migliore appropriato per una particolare necessità. Questi tipi di raccolta sono diversi dai tipi di raccolta in .NET Framework, ad esempio quelli nel `System.Collections.Generic` dello spazio dei nomi, in quanto i tipi di raccolta F # sono progettati da una prospettiva di programmazione funzionale piuttosto che da una prospettiva orientata agli oggetti. In particolare, solo la raccolta di matrice contiene elementi modificabili. Pertanto, quando si modifica una raccolta, si crea un'istanza della raccolta modificata invece di modifica della raccolta originale.

I tipi di raccolta anche differiscono nel tipo di struttura di data in cui sono archiviati gli oggetti. Strutture di dati, ad esempio tabelle hash, elenchi collegati e le matrici hanno le caratteristiche di prestazioni diverso e un set diverso di operazioni disponibili.

## <a name="f-collection-types"></a>Tipi di raccolta F#

La tabella seguente illustra i tipi di raccolta F #.

|Tipo|Descrizione|Collegamenti correlati|
|----|-----------|-------------|
|[List](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Una serie ordinata e non modificabile di elementi dello stesso tipo. Implementato come un elenco collegato.|[Elenchi](lists.md)<br /><br />[Modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[matrice](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Una raccolta a dimensione fissa, in base zero e modificabile di elementi dati consecutivi dello stesso tipo.|[Array](arrays.md)<br /><br />[Array (modulo)](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Modulo Array2D](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Modulo Array3D](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Una serie logica di elementi che sono dello stesso tipo. Le sequenze sono particolarmente utili quando si hanno grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevediate di usare tutti gli elementi. Sequenza di singoli elementi vengono calcolati solo se necessario, quindi una sequenza può avere prestazioni migliori rispetto a un elenco, se non vengono utilizzati tutti gli elementi. Le sequenze sono rappresentate dal `seq<'T>` tipo, che è un alias per `IEnumerable<T>`. Pertanto, qualsiasi tipo .NET Framework che implementa `System.Collections.Generic.IEnumerable<'T>` può essere usato come una sequenza.|[Sequenze](sequences.md)<br /><br />[Seq (modulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Mappa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Un dizionario non modificabile di elementi. Gli elementi sono accessibili tramite chiave.|[Map (modulo)](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Un set non modificabile basato su alberi binari, in cui il confronto è la funzione di confronto strutturali F #, che usa potenzialmente le implementazioni del `System.IComparable` interfaccia sui valori di chiave.|[Modulo di set](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabella delle funzioni

Questa sezione vengono confrontate le funzioni disponibili in tipi di raccolta F #. La complessità del calcolo della funzione viene specificata, dove N è la dimensione della prima raccolta e M è la dimensione della seconda raccolta, se presente. Un trattino (-) indica che questa funzione non è disponibile nella raccolta. Poiché le sequenze vengono valutate in modo differito, una funzione, ad esempio SEQ. Distinct potrebbe essere o (1) perché restituisce immediatamente, anche se ancora influisce sulle prestazioni della sequenza di enumerazione.

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
|concat|O (N)|O (N)|O (N)|-|-|Combina l'enumerazione di enumerazioni specificata come singola enumerazione concatenata.|
|contiene|-|-|-|-|O (log N)|Restituisce true se il set contiene l'elemento specificato.|
|containsKey|-|-|-|O (log N)|-|Verifica se un elemento si trova nel dominio di una mappa.|
|count|-|-|-|-|O (N)|Restituisce il numero di elementi nel set.|
|countBy|-|-|O (N)|-|-|Applica una funzione di generazione chiavi a ogni elemento di una sequenza e restituisce una sequenza che produce chiavi univoche e relativo numero di occorrenze nella sequenza originale.|
|copy|O (N)|-|O (N)|-|-|Copia la raccolta.|
|creazione|O (N)|-|-|-|-|Crea una matrice di elementi interi che sono inizialmente impostati sul valore specificato.|
|Ritardo|-|-|O(1)|-|-|Restituisce una sequenza che viene compilata dalla specifica ritardata indicata di una sequenza.|
|differenza|-|-|-|-|O (M &#42; log N)|Restituisce un nuovo set con gli elementi del secondo insieme rimossi dal primo set.|
|DISTINCT|||O (1)&AMP;#42;|||Restituisce una sequenza che non contiene voci duplicate in base ai confronti di uguaglianza e di hash generici sulle voci. Se un elemento è presente più volte nella sequenza, occorrenze successive vengono ignorate.|
|distinctBy|||O (1)&AMP;#42;|||Restituisce una sequenza che non contiene voci duplicate in base ai confronti di uguaglianza e hash generici per le chiavi che restituisce la funzione di generazione chiavi specificata. Se un elemento è presente più volte nella sequenza, occorrenze successive vengono ignorate.|
|vuoto|O(1)|O(1)|O(1)|O(1)|O(1)|Crea una raccolta vuota.|
|exists|O (N)|O (N)|O (N)|O (log N)|O (log N)|Verifica se qualsiasi elemento della sequenza soddisfa il predicato specificato.|
|exists2|O(min(N,M))|-|O(min(N,M))|||Verifica se qualsiasi coppia di elementi corrispondenti delle sequenze di input soddisfa il predicato specificato.|
|fill|O (N)|||||Imposta un intervallo di elementi della matrice sul valore specificato.|
|filtro|O (N)|O (N)|O (N)|O (N)|O (N)|Restituisce una nuova raccolta che contiene solo gli elementi della raccolta per il quale il predicato specificato restituisce `true`.|
|find|O (N)|O (N)|O (N)|O (log N)|-|Restituisce il primo elemento per cui la funzione specificata restituisce `true`. Restituisce `System.Collections.Generic.KeyNotFoundException` se tale elemento non esiste.|
|findIndex|O (N)|O (N)|O (N)|-|-|Restituisce l'indice del primo elemento nella matrice che soddisfa il predicato specificato. Genera `System.Collections.Generic.KeyNotFoundException` se nessun elemento soddisfa il predicato.|
|findKey|-|-|-|O (log N)|-|Valuta la funzione su ogni mapping nella raccolta e restituisce la chiave per il primo mapping in cui la funzione restituisce `true`. Se tale elemento non esiste, questa funzione genera `System.Collections.Generic.KeyNotFoundException`.|
|riduzione|O (N)|O (N)|O (N)|O (N)|O (N)|Applica una funzione a ogni elemento della raccolta, threading di un argomento di accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola f (... (f s i0)...) iN.|
|fold2|O (N)|O (N)|-|-|-|Applica una funzione agli elementi corrispondenti di due raccolte, threading di un argomento di accumulatore attraverso il calcolo. Le raccolte devono avere dimensioni identiche. Se la funzione di input è f e gli elementi sono i0 iN e... j0 jN, questa funzione Calcola f (... (s f i0 j0)...) iN jN.|
|foldBack|O (N)|O (N)|-|O (N)|O (N)|Applica una funzione a ogni elemento della raccolta, threading di un argomento di accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola f i0 (... (f iN s)).|
|foldBack2|O (N)|O (N)|-|-|-|Applica una funzione agli elementi corrispondenti di due raccolte, threading di un argomento di accumulatore attraverso il calcolo. Le raccolte devono avere dimensioni identiche. Se la funzione di input è f e gli elementi sono i0 iN e... j0 jN, questa funzione Calcola f i0 j0 (... (f iN jN s)).|
|forall|O (N)|O (N)|O (N)|O (N)|O (N)|Verifica se tutti gli elementi della raccolta soddisfano il predicato specificato.|
|forall2|O (N)|O (N)|O (N)|-|-|Verifica se tutti gli elementi corrispondenti della raccolta soddisfano a coppie il predicato specificato.|
|ottenere / ennesima|O(1)|O (N)|O (N)|-|-|Restituisce un elemento dalla raccolta di base al relativo indice.|
|head|-|O(1)|O(1)|-|-|Restituisce il primo elemento della raccolta.|
|init|O (N)|O (N)|O(1)|-|-|Crea una raccolta di date la dimensione e una funzione generatrice per calcolare gli elementi.|
|initInfinite|-|-|O(1)|-|-|Genera una sequenza che, se iterata, restituisce gli elementi successivi chiamando la funzione specificata.|
|Si intersecano|-|-|-|-|O (log N &#42; log M)|Calcola l'intersezione di due set.|
|intersectMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcola l'intersezione di una sequenza di set. La sequenza non deve essere vuota.|
|IsEmpty|O(1)|O(1)|O(1)|O(1)|-|Restituisce `true` se la raccolta è vuota.|
|isProperSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono nel secondo set e almeno un elemento del secondo set non è presente nel primo set.|
|isProperSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono nel primo set e almeno un elemento del primo set non è presente nel secondo set.|
|isSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono nel secondo set.|
|isSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono nel primo set.|
|Iter|O (N)|O (N)|O (N)|O (N)|O (N)|Applica la funzione specificata a ogni elemento della raccolta.|
|iteri|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata a ogni elemento della raccolta. Il valore integer che viene passato alla funzione indica l'indice dell'elemento.|
|iteri2|O (N)|O (N)|-|-|-|Applica la funzione specificata a una coppia di elementi che derivano dagli indici corrispondenti in due matrici. Il valore integer che viene passato alla funzione indica l'indice degli elementi. Le due matrici devono avere la stessa lunghezza.|
|iter2|O (N)|O (N)|O (N)|-|-|Applica la funzione specificata a una coppia di elementi che derivano dagli indici corrispondenti in due matrici. Le due matrici devono avere la stessa lunghezza.|
|length|O(1)|O (N)|O (N)|-|-|Restituisce il numero di elementi nella raccolta.|
|map|O (N)|O (N)|O(1)|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata a ogni elemento della matrice.|
|map2|O (N)|O (N)|O(1)|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti di due raccolte a coppie. Le due matrici di input devono avere la stessa lunghezza.|
|map3|-|O (N)|-|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti delle tre raccolte contemporaneamente.|
|MAPI|O (N)|O (N)|O (N)|-|-|Compila una matrice i cui elementi sono il risultato ottenuto applicando la funzione specificata a ogni elemento della matrice. L'indice integer passato alla funzione indica l'indice dell'elemento a cui è in corso di trasformazione.|
|mapi2|O (N)|O (N)|-|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti di due raccolte a coppie, passando inoltre l'indice degli elementi. Le due matrici di input devono avere la stessa lunghezza.|
|max|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento massimo nella raccolta, confrontata tramite il [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) operatore.|
|maxBy|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento massimo nella raccolta, confrontata usando [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) nel risultato della funzione.|
|maxElement|-|-|-|-|O (log N)|Restituisce l'elemento maggiore di set in base all'ordinamento utilizzato per il set.|
|min|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento minima nella raccolta, confrontata tramite il [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operatore.|
|minBy|O (N)|O (N)|O (N)|-|-|Restituisce l'elemento minima nella raccolta, confrontata tramite il [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) operatore nel risultato della funzione.|
|minElement|-|-|-|-|O (log N)|Restituisce l'elemento più basso nel set in base all'ordine che viene usato per il set.|
|ofArray|-|O (N)|O(1)|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi della matrice specificata.|
|ofList|O (N)|-|O(1)|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi dell'elenco specificato.|
|ofSeq|O (N)|O (N)|-|O (N)|O (N)|Crea una raccolta che contiene gli stessi elementi della sequenza specificata.|
|a livello pairwise|-|-|O (N)|-|-|Restituisce una sequenza di ogni elemento nella sequenza di input e il suo predecessore, ad eccezione del primo elemento, che viene restituito solo come predecessore del secondo elemento.|
|partition|O (N)|O (N)|-|O (N)|O (N)|Divide la raccolta in due raccolte. La prima raccolta contiene gli elementi per cui il predicato specificato restituisce `true`, e la seconda raccolta contiene gli elementi per cui il predicato specificato restituisce `false`.|
|permute|O (N)|O (N)|-|-|-|Restituisce una matrice con tutti gli elementi permutati secondo la permutazione specificata.|
|selezione|O (N)|O (N)|O (N)|O (log N)|-|Applica la funzione specificata a elementi consecutivi, restituendo il primo risultato in cui la funzione restituisce Some. Se la funzione non restituisce mai alcuni, `System.Collections.Generic.KeyNotFoundException` viene generato.|
|readonly|-|-|O (N)|-|-|Crea un oggetto di sequenza che delega all'oggetto sequenza specificato. Questa operazione garantisce che un cast di tipo non è possibile individuare di nuovo e modificare la sequenza originale. Ad esempio, se specifica una matrice, la sequenza restituita restituirà gli elementi della matrice, ma è Impossibile eseguire il cast dell'oggetto sequenza restituito a una matrice.|
|reduce|O (N)|O (N)|O (N)|-|-|Applica una funzione a ogni elemento della raccolta, threading di un argomento di accumulatore attraverso il calcolo. Questa funzione avvia applicando la funzione per i primi due elementi, passa il risultato alla funzione insieme il terzo elemento e così via. La funzione restituisce il risultato finale.|
|reduceBack|O (N)|O (N)|-|-|-|Applica una funzione a ogni elemento della raccolta, threading di un argomento di accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0..., questa funzione Calcola f i0 (... (f iN-1 iN)).|
|remove|-|-|-|O (log N)|O (log N)|Rimuove un elemento dal dominio della mappa. Se l'elemento non è presente, viene generata alcuna eccezione.|
|eseguire la replica|-|O (N)|-|-|-|Crea un elenco di lunghezza specificata con ogni elemento impostato sul valore specificato.|
|REV|O (N)|O (N)|-|-|-|Restituisce un nuovo elenco con gli elementi in ordine inverso.|
|analisi|O (N)|O (N)|O (N)|-|-|Applica una funzione a ogni elemento della raccolta, threading di un argomento di accumulatore attraverso il calcolo. Questa operazione si applica la funzione per il secondo argomento e il primo elemento dell'elenco. L'operazione viene passa questo risultato alla funzione insieme al secondo elemento e così via. Infine, l'operazione restituisce l'elenco dei risultati intermedi e il risultato finale.|
|scanBack|O (N)|O (N)|-|-|-|L'operazione foldBack è simile ma restituisce sia i risultati intermedi e finali.|
|singleton|-|-|O(1)|-|O(1)|Restituisce una sequenza che produce un solo elemento.|
|set|O(1)|-|-|-|-|Imposta un elemento della matrice sul valore specificato.|
|skip|-|-|O (N)|-|-|Restituisce una sequenza che ignora N elementi della sequenza sottostante e restituisce gli elementi rimanenti della sequenza.|
|SkipWhile|-|-|O (N)|-|-|Restituisce una sequenza che, se iterata, ignora gli elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e restituisce gli elementi rimanenti della sequenza.|
|sort|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|O (N log N)|-|-|Ordina la raccolta dal valore dell'elemento. Gli elementi vengono confrontati tramite [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|O (N log N)|-|-|Ordina l'elenco specificato utilizzando i tasti che fornisce la proiezione specificata. Le chiavi vengono confrontate usando [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi della matrice di mutazione viene posto e usando la funzione di confronto specificata. Gli elementi vengono confrontati usando [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi della matrice di mutazione viene posto e tramite la proiezione specificata per le chiavi. Gli elementi vengono confrontati usando [confrontare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|-|-|-|-|Ordina gli elementi della matrice da mutazione viene posto e tramite la funzione di confronto specificata come ordine.|
|sortWith|Media O (N log N)<br /><br />O(N^2) peggiore dei casi|O (N log N)|-|-|-|Ordina gli elementi di una raccolta, tramite la funzione di confronto specificata come ordine e la restituzione di una nuova raccolta.|
|sub|O (N)|-|-|-|-|Compila una matrice che contiene l'intervallo secondario fornito specificato dall'indice iniziale e dalla lunghezza.|
|sum|O (N)|O (N)|O (N)|-|-|Restituisce la somma degli elementi nella raccolta.|
|sumBy|O (N)|O (N)|O (N)|-|-|Restituisce la somma dei risultati generati applicando la funzione a ogni elemento della raccolta.|
|Della parte finale del|-|O(1)|-|-|-|Restituisce l'elenco senza il primo elemento.|
|Take|-|-|O (N)|-|-|Restituisce gli elementi della sequenza fino a un numero specificato.|
|TakeWhile|-|-|O(1)|-|-|Restituisce una sequenza che, se iterata, produce gli elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e quindi non restituisce Nessun ulteriori elementi.|
|ToArray|-|O (N)|O (N)|O (N)|O (N)|Crea una matrice dalla raccolta specificata.|
|ToList|O (N)|-|O (N)|O (N)|O (N)|Crea un elenco dalla raccolta specificata.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Crea una sequenza dalla raccolta specificata.|
|TRUNCATE|-|-|O(1)|-|-|Restituisce una sequenza che, quando enumerata, restituisce non più di N elementi.|
|tryFind|O (N)|O (N)|O (N)|O (log N)|-|Cerca un elemento che soddisfa un predicato specificato.|
|tryFindIndex|O (N)|O (N)|O (N)|-|-|Cerca il primo elemento che soddisfa un predicato specificato e restituisce l'indice dell'elemento corrispondente, o `None` se tale elemento non esiste.|
|tryFindKey|-|-|-|O (log N)|-|Restituisce la chiave del primo mapping nella raccolta che soddisfa il predicato specificato, o restituisce `None` se tale elemento non esiste.|
|tryPick|O (N)|O (N)|O (N)|O (log N)|-|Applica la funzione specificata a elementi consecutivi, restituendo il primo risultato in cui la funzione restituisce `Some` per alcuni valori. Se tale elemento non esiste, l'operazione restituisce `None`.|
|Espandi|-|-|O (N)|-|-|Restituisce una sequenza che contiene gli elementi che genera il calcolo specificato.|
|union|-|-|-|-|O (M &#42; log N)|Calcola l'unione dei due set.|
|unionMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Calcola l'unione di una sequenza di set.|
|unzip|O (N)|O (N)|O (N)|-|-|Suddivide un elenco di coppie in due elenchi.|
|unzip3|O (N)|O (N)|O (N)|-|-|Suddivide un elenco di tripli in tre elenchi.|
|con finestra|-|-|O (N)|-|-|Restituisce una sequenza che produce finestre scorrevoli di che contengono elementi che vengono disegnati dalla sequenza di input. Ogni finestra viene restituita come matrice aggiornata.|
|file ZIP|O (N)|O (N)|O (N)|-|-|Combina due raccolte in un elenco di coppie. I due elenchi lunghezza devono essere uguale.|
|zip3|O (N)|O (N)|O (N)|-|-|Combina tre raccolte in un elenco di tripli. Gli elenchi di lunghezza devono essere uguale.|

## <a name="see-also"></a>Vedere anche

- [Tipi F#](fsharp-types.md)
- [Riferimenti per il linguaggio F#](index.md)
