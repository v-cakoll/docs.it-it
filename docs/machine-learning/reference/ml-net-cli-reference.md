---
title: Riferimento al comando CLI ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 12/18/2019
ms.openlocfilehash: 537f8d361c170378f5fe8cf454320831d7c8cbf2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449699"
---
# <a name="the-mlnet-cli-command-reference"></a>Riferimento ai comandi dell'interfaccia della riga di comando ML.NET

Il comando `auto-train` è il comando principale dello strumento dell'interfaccia della riga di comando di ML.NET. Il comando consente di generare un modello ML.NET di qualità elevata usando automazione Machine Learning (AutoML), nonché il codice di C# esempio per eseguire/assegnare un punteggio a tale modello. Inoltre, il C# codice per eseguire il training del modello viene generato per la ricerca dell'algoritmo e delle impostazioni del modello.

> [!NOTE]
> Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="overview"></a>Panoramica

Sintassi di esempio:

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

Il comando `mlnet auto-train` genera gli asset seguenti:

- Un file di modello serializzato con estensione zip ("miglior modello") pronto per l'uso.
- C#codice per l'esecuzione o il punteggio del modello generato.
- C#codice con il codice di training utilizzato per generare il modello.

Le prime due risorse possono essere usate direttamente nelle app per gli utenti finali (ASP.NET Core app Web, servizi, app desktop e altro ancora) per eseguire stime con il modello.

Il terzo asset, il codice di training, Mostra il codice API ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo da poter esaminare l'algoritmo e le impostazioni specifiche del modello.

## <a name="examples"></a>Esempi

Il comando CLI più semplice per un problema di classificazione binaria (AutoML deduce la maggior parte della configurazione dai dati forniti):

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

Un altro comando dell'interfaccia della riga semplice per un problema di regressione:

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

Creare ed eseguire il training di un modello di classificazione binaria con un set di dati con training, un set di dati di test e ulteriori argomenti espliciti di personalizzazione:

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a>Opzioni del comando

`mlnet auto-train` esegue il training di più modelli in base al set di dati fornito e infine seleziona il modello migliore, lo salva come file con estensione zip C# serializzato più genera il codice correlato per il punteggio e il training.

```console
mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

Opzioni di input non valide. lo strumento dell'interfaccia della riga di comando crea un elenco di input validi e un messaggio di errore.

## <a name="task"></a>Attività

`--task | --mltask | -T` (string)

Stringa singola che specifica il problema di Machine Learning da risolvere. Ad esempio, una delle attività seguenti (l'interfaccia della riga di comando supporterà tutte le attività supportate nella funzionalità di Machine Learning automatico):

- `regression` - Scegliere se verrà usato il modello di Machine Learning per effettuare la previsione di un valore numerico
- `binary-classification` - Scegliere se il risultato del modello di Machine Learning ha due valori booleani categorici possibili (0 o 1).
- `multiclass-classification` - Scegliere se il risultato del modello di Machine Learning ha più valori categorici possibili.

In questo argomento è necessario specificare una sola attività di Machine Learning.

## <a name="dataset"></a>Set di dati

`--dataset | -d` (string)

Questo argomento specifica il percorso file di una delle opzioni seguenti:

- *R: l'intero file del set di dati:* Se si usa questa opzione e l'utente non fornisce `--test-dataset` e `--validation-dataset`, la convalida incrociata (k-fold e così via) o gli approcci di suddivisione automatica dei dati verranno usati internamente per la convalida del modello. In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.

- *B: file del set di dati di training:* Se l'utente fornisce anche set di dati per la convalida del modello (usando `--test-dataset` e, facoltativamente, `--validation-dataset`), l'argomento `--dataset` significa solo il "set di dati di training". Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.

## <a name="test-dataset"></a>Set di dati di test

`--test-dataset | -t` (string)

Percorso del file del set di dati di test, ad esempio quando viene usato un approccio 80% - 20% durante le convalide regolari per ottenere le metriche di accuratezza.

Se viene usato `--test-dataset`, è necessario specificare anche `--dataset`.

L'argomento `--test-dataset` è facoltativo, a meno che non venga usato --validation-dataset. In questo caso, l'utente deve usare i tre argomenti.

## <a name="validation-dataset"></a>Set di dati di convalida

`--validation-dataset | -v` (string)

Percorso del file del set di dati di convalida. In tutti i casi il set di dati di convalida è facoltativo.

Se si usa `validation dataset`, il comportamento deve essere il seguente:

- Anche gli argomenti `test-dataset` e `--dataset` sono obbligatori.

- Il set di dati `validation-dataset` viene usato per stimare l'errore di previsione per la selezione del modello.

- Il set di dati `test-dataset` viene usato per la valutazione dell'errore di generalizzazione del modello selezionato finale. In teoria, il set di test deve essere conservato in un "vault" e usato solo alla fine dell'analisi dei dati.

In pratica, quando vengono usati `validation dataset` e `test dataset`, la fase di convalida è suddivisa in due parti:

1. Si esaminano innanzitutto i modelli e si seleziona l'approccio migliore usando i dati di convalida (=validation)
2. Quindi si valuta l'accuratezza dell'approccio selezionato (=test).

Di conseguenza, la suddivisione dei dati potrebbe essere 80/10/10 o 75/15/10. Ad esempio,

- Il file di `training-dataset` deve avere il 75% dei dati.
- Il file di `validation-dataset` deve avere il 15% dei dati.
- Il file di `test-dataset` deve avere il 10% dei dati.

In ogni caso, queste percentuali verranno decise dall'utente tramite l'interfaccia della riga di comando che fornirà i file già suddivisi.

## <a name="label-column-name"></a>Nome colonna etichetta

`--label-column-name | -n` (string)

Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando il nome della colonna impostato nell'intestazione del set di dati.

Questo argomento viene usato solo per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*. Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.

## <a name="label-column-index"></a>Indice colonna etichetta

`--label-column-index | -i` (int)

Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando l'indice numerico della colonna nel file del set di dati (i valori di indice della colonna iniziano da 1).

*Nota:* Se l'utente usa anche il `--label-column-name`, il `--label-column-name` è quello usato.

Questo argomento viene usato per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*. Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.

## <a name="ignore-columns"></a>Ignora colonne

`--ignore-columns | -I` (string)

Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.

Specificare i nomi delle colonne da ignorare. Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna. È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").

Esempio:

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a>Con intestazione

`--has-header | -h` (bool)

Specificare se i file di set di dati includono una riga di intestazione.
I valori possibili sono:

- `true`
- `false`

Il valore predefinito è `true` se questo argomento non viene specificato dall'utente.

Per usare l'argomento `--label-column-name` è necessario che il file del set di dati includa un'intestazione e che `--has-header` sia impostato su `true` (impostazione predefinita).

## <a name="max-exploration-time"></a>Tempo massimo di esplorazione

`--max-exploration-time | -x` (string)

Per impostazione predefinita, il tempo massimo di esplorazione è 30 minuti.

Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni. Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione. In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.

Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.

## <a name="cache"></a>Cache

`--cache | -c` (string)

Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.

Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.

Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria. Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.

È possibile specificare i valori seguenti:

`on`: forza la cache da usare durante il training.
`off`: forza la cache a non essere utilizzata durante il training.
`auto`: a seconda dell'euristica AutoML, la cache verrà utilizzata o meno. In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.

Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.

## <a name="name"></a>Name

`--name | -N` (string)

Nome del progetto di output o della soluzione creata. Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.

Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).

## <a name="output-path"></a>Percorso output

`--output-path | -o` (string)

Percorso o cartella radice in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

## <a name="verbosity"></a>Livello di dettaglio

`--verbosity | -V` (string)

Imposta il livello di dettaglio dell'output standard.

I valori consentiti sono:

- `q[uiet]`
- `m[inimal]`  (per impostazione predefinita)
- `diag[nostic]` (livello informazioni di registrazione)

Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando dovrebbe visualizzare un feedback minimo, ad esempio indicare che è attivo e se possibile il tempo rimanente o la percentuale di tempo trascorso.

## <a name="help"></a>?

`-h|--help`

Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](../how-to-guides/install-ml-net-cli.md)
- [Panoramica dell'interfaccia della riga di comando di ML.NET](../automate-training-with-cli.md)
- [Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET](../tutorials/sentiment-analysis-cli.md)
- [Telemetria nell'interfaccia della riga di comando di ML.NET](../resources/ml-net-cli-telemetry.md)
