---
title: Tipi di raccolta
description: Informazioni sui F# tipi di raccolta e su come si differenziano dai tipi di raccolta nel .NET Framework.
ms.date: 05/16/2016
ms.openlocfilehash: df34a18e7762c52e169aa8a69709ae16064c134d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628865"
---
# <a name="f-collection-types"></a>Tipi di raccolta F#

Esaminando questo argomento, è possibile determinare il tipo di F# raccolta più adatto a una particolare esigenza. Questi tipi di raccolta si differenziano dai tipi di raccolta nel .NET Framework, ad esempio quelli nello spazio dei nomi `System.Collections.Generic`, F# in quanto i tipi di raccolta sono progettati da una prospettiva di programmazione funzionale piuttosto che da una prospettiva orientata agli oggetti. In particolare, solo la raccolta di matrici ha elementi modificabili. Pertanto, quando si modifica una raccolta, si crea un'istanza della raccolta modificata invece di modificare la raccolta originale.

I tipi di raccolta differiscono anche per il tipo di struttura dei dati in cui sono archiviati gli oggetti. Le strutture di dati quali tabelle hash, elenchi collegati e matrici hanno caratteristiche di prestazioni diverse e un set di operazioni disponibili diverso.

## <a name="f-collection-types"></a>Tipi di raccolta F#

La tabella seguente illustra F# i tipi di raccolta.

|Type|Descrizione|Collegamenti correlati|
|----|-----------|-------------|
|[Elenco](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Serie ordinata e non modificabile di elementi dello stesso tipo. Implementato come elenco collegato.|[Elenchi](lists.md)<br /><br />[Elenca modulo](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Raccolta modificabile a dimensione fissa, in base zero, di elementi di dati consecutivi che sono tutti dello stesso tipo.|[Array](arrays.md)<br /><br />[Modulo array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Modulo Array2D](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Modulo Array3D](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Una serie logica di elementi che sono tutti di un tipo. Le sequenze sono particolarmente utili quando si dispone di una raccolta di dati grande e ordinata, ma non si prevede necessariamente di usare tutti gli elementi. I singoli elementi di sequenza vengono calcolati solo se necessario, pertanto una sequenza può essere eseguita meglio di un elenco se non vengono utilizzati tutti gli elementi. Le sequenze sono rappresentate dal tipo di `seq<'T>`, che è un alias per `IEnumerable<T>`. Pertanto, qualsiasi tipo di .NET Framework che implementi `System.Collections.Generic.IEnumerable<'T>` può essere utilizzato come sequenza.|[Sequenze](sequences.md)<br /><br />[Modulo Seq](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Mappa](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Dizionario non modificabile di elementi. È possibile accedere agli elementi in base alla chiave.|[Modulo Map](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Set non modificabile basato su alberi binari, in cui il confronto è la F# funzione di confronto strutturale, che potenzialmente usa le implementazioni dell'interfaccia `System.IComparable` sui valori di chiave.|[Imposta modulo](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabella delle funzioni

In questa sezione vengono confrontate le funzioni disponibili F# sui tipi di raccolta. Viene fornita la complessità computazionale della funzione, dove N è la dimensione della prima raccolta e M è la dimensione della seconda raccolta, se disponibile. Un trattino (-) indica che questa funzione non è disponibile nella raccolta. Poiché le sequenze vengono valutate in modo differito, una funzione come Seq. Distinct può essere O (1) perché restituisce immediatamente un risultato, sebbene influisca sulle prestazioni della sequenza durante l'enumerazione.

|Funzione|Array|Elenco|Sequenza|Mappa|Configurazione|Descrizione|
|--------|-----|----|--------|---|---|-----------|
|append|O(N)|O(N)|O(N)|-|-|Restituisce una nuova raccolta che contiene gli elementi della prima raccolta seguita dagli elementi della seconda raccolta.|
|add|-|-|-|O (log N)|O (log N)|Restituisce una nuova raccolta con l'elemento aggiunto.|
|average|O(N)|O(N)|O(N)|-|-|Restituisce la media degli elementi nella raccolta.|
|averageBy|O(N)|O(N)|O(N)|-|-|Restituisce la media dei risultati della funzione fornita applicata a ogni elemento.|
|Blit|O(N)|-|-|-|-|Copia una sezione di una matrice.|
|cache|-|-|O(N)|-|-|Calcola e archivia gli elementi di una sequenza.|
|Cast|-|-|O(N)|-|-|Converte gli elementi nel tipo specificato.|
|choose|O(N)|O(N)|O(N)|-|-|Applica la funzione specificata `f` a ogni elemento `x` dell'elenco. Restituisce l'elenco che contiene i risultati per ogni elemento in cui la funzione restituisce `Some(f(x))`.|
|collect|O(N)|O(N)|O(N)|-|-|Applica la funzione specificata a ogni elemento della raccolta, concatena tutti i risultati e restituisce l'elenco combinato.|
|compareWith|-|-|O(N)|-|-|Confronta due sequenze tramite la funzione di confronto specificata, elemento per elemento.|
|concat|O(N)|O(N)|O(N)|-|-|Combina l'enumerazione di enumerazioni specificata come singola enumerazione concatenata.|
|contains|-|-|-|-|O (log N)|Restituisce true se il set contiene l'elemento specificato.|
|containsKey|-|-|-|O (log N)|-|Verifica se un elemento si trova nel dominio di una mappa.|
|count|-|-|-|-|O(N)|Restituisce il numero di elementi nel set.|
|countBy|-|-|O(N)|-|-|Applica una funzione di generazione chiavi a ogni elemento di una sequenza e restituisce una sequenza che restituisce chiavi univoche e il relativo numero di occorrenze nella sequenza originale.|
|copiare|O(N)|-|O(N)|-|-|Copia la raccolta.|
|create|O(N)|-|-|-|-|Crea una matrice di elementi interi che sono tutti inizialmente il valore specificato.|
|delay|-|-|O(1)|-|-|Restituisce una sequenza compilata dalla specifica ritardata specificata di una sequenza.|
|differenza|-|-|-|-|O (M &#42; log N)|Restituisce un nuovo set con gli elementi del secondo set rimossi dal primo set.|
|distinct|||O(1)&#42;|||Restituisce una sequenza che non contiene voci duplicate in base all'hash generico e ai confronti di uguaglianza sulle voci. Se un elemento si verifica più volte nella sequenza, le occorrenze successive vengono scartate.|
|distinctBy|||O(1)&#42;|||Restituisce una sequenza che non contiene voci duplicate in base all'hash generico e ai confronti di uguaglianza sulle chiavi restituite dalla funzione di generazione della chiave specificata. Se un elemento si verifica più volte nella sequenza, le occorrenze successive vengono scartate.|
|empty|O(1)|O(1)|O(1)|O(1)|O(1)|Crea una raccolta vuota.|
|esiste|O(N)|O(N)|O(N)|O (log N)|O (log N)|Verifica se un elemento della sequenza soddisfa il predicato specificato.|
|exists2|O (min (N, M))|-|O (min (N, M))|||Verifica se una coppia di elementi corrispondenti delle sequenze di input soddisfa il predicato specificato.|
|fill|O(N)|||||Imposta un intervallo di elementi della matrice sul valore specificato.|
|Filtro|O(N)|O(N)|O(N)|O(N)|O(N)|Restituisce una nuova raccolta che contiene solo gli elementi della raccolta per cui il predicato specificato restituisce `true`.|
|trovare|O(N)|O(N)|O(N)|O (log N)|-|Restituisce il primo elemento per il quale la funzione specificata restituisce `true`. Restituisce `System.Collections.Generic.KeyNotFoundException` se tale elemento non esiste.|
|findIndex|O(N)|O(N)|O(N)|-|-|Restituisce l'indice del primo elemento nella matrice che soddisfa il predicato specificato. Genera `System.Collections.Generic.KeyNotFoundException` se nessun elemento soddisfa il predicato.|
|findKey|-|-|-|O (log N)|-|Valuta la funzione su ogni mapping nella raccolta e restituisce la chiave per il primo mapping in cui la funzione restituisce `true`. Se tale elemento non esiste, questa funzione genera `System.Collections.Generic.KeyNotFoundException`.|
|riduzione|O(N)|O(N)|O(N)|O(N)|O(N)|Applica una funzione a ogni elemento della raccolta, Threading di un argomento dell'accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0... iN questa funzione calcola f (... (f s I0)...) iN.|
|fold2|O(N)|O(N)|-|-|-|Applica una funzione agli elementi corrispondenti di due raccolte, Threading di un argomento dell'accumulatore attraverso il calcolo. Le dimensioni delle raccolte devono essere identiche. Se la funzione di input è f e gli elementi sono i0... iN e j0... jN, questa funzione calcola f (... (f s i0 j0)...) iN jN.|
|foldBack|O(N)|O(N)|-|O(N)|O(N)|Applica una funzione a ogni elemento della raccolta, Threading di un argomento dell'accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0... iN questa funzione calcola f i0 (... (f iN s)).|
|foldBack2|O(N)|O(N)|-|-|-|Applica una funzione agli elementi corrispondenti di due raccolte, Threading di un argomento dell'accumulatore attraverso il calcolo. Le dimensioni delle raccolte devono essere identiche. Se la funzione di input è f e gli elementi sono i0... iN e j0... jN, questa funzione calcola f i0 j0 (... (f iN jN s)).|
|ForAll|O(N)|O(N)|O(N)|O(N)|O(N)|Verifica se tutti gli elementi della raccolta soddisfano il predicato specificato.|
|forall2|O(N)|O(N)|O(N)|-|-|Verifica se tutti gli elementi corrispondenti della raccolta soddisfano a coppie il predicato specificato.|
|Get/nth|O(1)|O(N)|O(N)|-|-|Restituisce un elemento dalla raccolta in base al relativo indice.|
|head|-|O(1)|O(1)|-|-|Restituisce il primo elemento della raccolta.|
|init|O(N)|O(N)|O(1)|-|-|Crea una raccolta in base alla dimensione e a una funzione del generatore per calcolare gli elementi.|
|initInfinite|-|-|O(1)|-|-|Genera una sequenza che, se iterata, restituisce elementi successivi chiamando la funzione specificata.|
|Intersect|-|-|-|-|O (log N &#42; log M)|Calcola l'intersezione di due set.|
|intersectMany (|-|-|-|-|O (N1 &#42; N2...)|Calcola l'intersezione di una sequenza di set. La sequenza non deve essere vuota.|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|Restituisce `true` se la raccolta è vuota.|
|isProperSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono presenti nel secondo set e almeno un elemento del secondo set non è presente nel primo set.|
|isProperSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono presenti nel primo set e almeno un elemento del primo set non è incluso nel secondo set.|
|isSubset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del primo set sono presenti nel secondo set.|
|isSuperset|-|-|-|-|O (M &#42; log N)|Restituisce `true` se tutti gli elementi del secondo set sono presenti nel primo set.|
|iter|O(N)|O(N)|O(N)|O(N)|O(N)|Applica la funzione specificata a ogni elemento della raccolta.|
|iteri|O(N)|O(N)|O(N)|-|-|Applica la funzione specificata a ogni elemento della raccolta. Il valore integer passato alla funzione indica l'indice dell'elemento.|
|iteri2|O(N)|O(N)|-|-|-|Applica la funzione specificata a una coppia di elementi che vengono disegnati da indici corrispondenti in due matrici. Il valore integer passato alla funzione indica l'indice degli elementi. Le due matrici devono avere la stessa lunghezza.|
|iter2|O(N)|O(N)|O(N)|-|-|Applica la funzione specificata a una coppia di elementi che vengono disegnati da indici corrispondenti in due matrici. Le due matrici devono avere la stessa lunghezza.|
|last|O(1)|O(N)|O(N)|-|-|Restituisce l'ultimo elemento della raccolta applicabile.|
|length|O(1)|O(N)|O(N)|-|-|Restituisce il numero di elementi nella raccolta.|
|map|O(N)|O(N)|O(1)|-|-|Compila una raccolta i cui elementi sono il risultato dell'applicazione della funzione specificata a ogni elemento della matrice.|
|MAP2|O(N)|O(N)|O(1)|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti delle due raccolte pairwise. Le due matrici di input devono avere la stessa lunghezza.|
|map3|-|O(N)|-|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti delle tre raccolte simultaneamente.|
|MAPI|O(N)|O(N)|O(N)|-|-|Compila una matrice i cui elementi sono il risultato dell'applicazione della funzione specificata a ogni elemento della matrice. L'indice Integer passato alla funzione indica l'indice dell'elemento che si sta trasformando.|
|mapi2|O(N)|O(N)|-|-|-|Compila una raccolta i cui elementi sono il risultato ottenuto applicando la funzione specificata agli elementi corrispondenti delle due raccolte pairwise, passando anche l'indice degli elementi. Le due matrici di input devono avere la stessa lunghezza.|
|max|O(N)|O(N)|O(N)|-|-|Restituisce l'elemento maggiore della raccolta, confrontato utilizzando l'operatore [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) .|
|maxBy|O(N)|O(N)|O(N)|-|-|Restituisce l'elemento maggiore della raccolta, confrontato con il valore [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) nel risultato della funzione.|
|maxElement|-|-|-|-|O (log N)|Restituisce l'elemento più grande del set in base all'ordine utilizzato per il set.|
|Min|O(N)|O(N)|O(N)|-|-|Restituisce il minor elemento della raccolta, confrontato con l'operatore [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) .|
|minBy|O(N)|O(N)|O(N)|-|-|Restituisce il minor elemento della raccolta, confrontato utilizzando l'operatore [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) nel risultato della funzione.|
|minElement|-|-|-|-|O (log N)|Restituisce l'elemento più basso del set in base all'ordine utilizzato per il set.|
|ofArray|-|O(N)|O(1)|O(N)|O(N)|Crea una raccolta che contiene gli stessi elementi della matrice specificata.|
|ofList|O(N)|-|O(1)|O(N)|O(N)|Crea una raccolta che contiene gli stessi elementi dell'elenco specificato.|
|ofSeq|O(N)|O(N)|-|O(N)|O(N)|Crea una raccolta che contiene gli stessi elementi della sequenza specificata.|
|pairwise|-|-|O(N)|-|-|Restituisce una sequenza di ogni elemento nella sequenza di input e il relativo predecessore, ad eccezione del primo elemento, che viene restituito solo come predecessore del secondo elemento.|
|partizione|O(N)|O(N)|-|O(N)|O(N)|Suddivide la raccolta in due raccolte. La prima raccolta contiene gli elementi per i quali il predicato specificato restituisce `true`e la seconda raccolta contiene gli elementi per i quali il predicato specificato restituisce `false`.|
|permute|O(N)|O(N)|-|-|-|Restituisce una matrice con tutti gli elementi permutati in base alla permutazione specificata.|
|Selezionare|O(N)|O(N)|O(N)|O (log N)|-|Applica la funzione specificata agli elementi successivi, restituendo il primo risultato in cui la funzione restituisce Some. Se la funzione non restituisce mai Some, viene generato `System.Collections.Generic.KeyNotFoundException`.|
|readonly|-|-|O(N)|-|-|Crea un oggetto sequenza che delega all'oggetto sequenza specificato. Questa operazione garantisce che un cast di tipo non possa riindividuare e mutare la sequenza originale. Se, ad esempio, si specifica una matrice, la sequenza restituita restituirà gli elementi della matrice, ma non sarà possibile eseguire il cast dell'oggetto sequenza restituito a una matrice.|
|reduce|O(N)|O(N)|O(N)|-|-|Applica una funzione a ogni elemento della raccolta, Threading di un argomento dell'accumulatore attraverso il calcolo. Questa funzione inizia applicando la funzione ai primi due elementi, passa questo risultato alla funzione insieme al terzo elemento e così via. La funzione restituisce il risultato finale.|
|reduceBack|O(N)|O(N)|-|-|-|Applica una funzione a ogni elemento della raccolta, Threading di un argomento dell'accumulatore attraverso il calcolo. Se la funzione di input è f e gli elementi sono i0... iN questa funzione calcola f i0 (... (f iN-1 iN)).|
|rimozione|-|-|-|O (log N)|O (log N)|Rimuove un elemento dal dominio della mappa. Se l'elemento non è presente, non viene generata alcuna eccezione.|
|replicare|-|O(N)|-|-|-|Crea un elenco di lunghezza specificata con ogni elemento impostato sul valore specificato.|
|Rev|O(N)|O(N)|-|-|-|Restituisce un nuovo elenco con gli elementi in ordine inverso.|
|scansione|O(N)|O(N)|O(N)|-|-|Applica una funzione a ogni elemento della raccolta, Threading di un argomento dell'accumulatore attraverso il calcolo. Questa operazione applica la funzione al secondo argomento e al primo elemento dell'elenco. L'operazione passa quindi questo risultato nella funzione insieme al secondo elemento e così via. Infine, l'operazione restituisce l'elenco dei risultati intermedi e il risultato finale.|
|scanBack|O(N)|O(N)|-|-|-|È simile all'operazione foldBack, ma restituisce sia i risultati intermedi che quelli finali.|
|singleton|-|-|O(1)|-|O(1)|Restituisce una sequenza che produce un solo elemento.|
|set|O(1)|-|-|-|-|Imposta un elemento di una matrice sul valore specificato.|
|skip|-|-|O(N)|-|-|Restituisce una sequenza che ignora N elementi della sequenza sottostante e quindi produce gli elementi rimanenti della sequenza.|
|skipWhile|-|-|O(N)|-|-|Restituisce una sequenza che, se iterata, ignora gli elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e quindi produce gli elementi rimanenti della sequenza.|
|sort|O (N log N) media<br /><br />O (N ^ 2) worst case|O (N log N)|O (N log N)|-|-|Ordina la raccolta in base al valore dell'elemento. Gli elementi vengono confrontati con [compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|O (N log N) media<br /><br />O (N ^ 2) worst case|O (N log N)|O (N log N)|-|-|Ordina l'elenco specificato usando le chiavi fornite dalla proiezione specificata. Le chiavi vengono confrontate usando [compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace|O (N log N) media<br /><br />O (N ^ 2) worst case|-|-|-|-|Ordina gli elementi di una matrice mutando il valore sul posto e usando la funzione di confronto specificata. Gli elementi vengono confrontati tramite [compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|O (N log N) media<br /><br />O (N ^ 2) worst case|-|-|-|-|Ordina gli elementi di una matrice tramite la mutazione sul posto e usando la proiezione specificata per le chiavi. Gli elementi vengono confrontati tramite [compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|O (N log N) media<br /><br />O (N ^ 2) worst case|-|-|-|-|Ordina gli elementi di una matrice tramite la mutazione sul posto e usando la funzione di confronto specificata come ordine.|
|sortWith|O (N log N) media<br /><br />O (N ^ 2) worst case|O (N log N)|-|-|-|Ordina gli elementi di una raccolta, usando la funzione di confronto specificata come ordine e restituendo una nuova raccolta.|
|sub|O(N)|-|-|-|-|Compila una matrice che contiene l'intervallo secondario specificato dall'indice iniziale e dalla lunghezza.|
|sum|O(N)|O(N)|O(N)|-|-|Restituisce la somma degli elementi nella raccolta.|
|sumBy|O(N)|O(N)|O(N)|-|-|Restituisce la somma dei risultati generati applicando la funzione a ogni elemento della raccolta.|
|coda|-|O(1)|-|-|-|Restituisce l'elenco senza il primo elemento.|
|take|-|-|O(N)|-|-|Restituisce gli elementi della sequenza fino al conteggio specificato.|
|takeWhile|-|-|O(1)|-|-|Restituisce una sequenza che, se iterata, produce elementi della sequenza sottostante mentre il predicato specificato restituisce `true` e quindi non restituisce più elementi.|
|toArray|-|O(N)|O(N)|O(N)|O(N)|Crea una matrice dalla raccolta specificata.|
|toList|O(N)|-|O(N)|O(N)|O(N)|Crea un elenco dalla raccolta specificata.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Crea una sequenza dalla raccolta specificata.|
|truncate|-|-|O(1)|-|-|Restituisce una sequenza che, se enumerata, non restituisce più di N elementi.|
|tryFind|O(N)|O(N)|O(N)|O (log N)|-|Cerca un elemento che soddisfi un predicato specificato.|
|tryFindIndex|O(N)|O(N)|O(N)|-|-|Cerca il primo elemento che soddisfa un predicato specificato e restituisce l'indice dell'elemento corrispondente o `None` se tale elemento non esiste.|
|tryFindKey|-|-|-|O (log N)|-|Restituisce la chiave del primo mapping della raccolta che soddisfa il predicato specificato oppure restituisce `None` se tale elemento non esiste.|
|tryPick|O(N)|O(N)|O(N)|O (log N)|-|Applica la funzione specificata agli elementi successivi, restituendo il primo risultato in cui la funzione restituisce `Some` per un determinato valore. Se tale elemento non esiste, l'operazione restituisce `None`.|
|svolgersi|-|-|O(N)|-|-|Restituisce una sequenza che contiene gli elementi generati dal calcolo specificato.|
|unione|-|-|-|-|O (M &#42; log N)|Calcola l'Unione dei due set.|
|unionMany|-|-|-|-|O (N1 &#42; N2...)|Calcola l'Unione di una sequenza di set.|
|unzip|O(N)|O(N)|O(N)|-|-|Suddivide un elenco di coppie in due elenchi.|
|unzip3|O(N)|O(N)|O(N)|-|-|Suddivide un elenco di tripli in tre elenchi.|
|finestra|-|-|O(N)|-|-|Restituisce una sequenza che produce finestre scorrevoli di elementi contenenti che vengono disegnati dalla sequenza di input. Ogni finestra viene restituita come matrice aggiornata.|
|zip|O(N)|O(N)|O(N)|-|-|Combina le due raccolte in un elenco di coppie. I due elenchi devono avere le stesse lunghezze.|
|zip3|O(N)|O(N)|O(N)|-|-|Combina le tre raccolte in un elenco di tripli. Gli elenchi devono avere le stesse lunghezze.|

## <a name="see-also"></a>Vedere anche

- [Tipi F#](fsharp-types.md)
- [Riferimenti per il linguaggio F#](index.md)
