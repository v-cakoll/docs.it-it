---
title: Riferimento al comando CLI ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 397f6fda8554024624b3ef630856dc8eca9696b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594543"
---
# <a name="the-mlnet-cli-command-reference"></a>Riferimento ai comandi dell'interfaccia della riga di comando ML.NET

I `classification` `regression` comandi, e `recommendation` sono i comandi principali forniti dallo strumento dell'interfaccia della riga di comando ml.NET. Questi comandi consentono di generare modelli ML.NET di qualità elevata per la classificazione, la regressione e i modelli di raccomandazione usando automazione Machine Learning (AutoML), nonché il codice C# di esempio per eseguire/assegnare un punteggio a tale modello. Inoltre, il codice C# per eseguire il training del modello viene generato per la ricerca dell'algoritmo e delle impostazioni del modello.

> [!NOTE]
> Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.

## <a name="overview"></a>Panoramica

Sintassi di esempio:

```console
mlnet regression --dataset "cars.csv" --label-col price
```

I `mlnet` comandi dell'attività ml ( `classification` , `regression` e `recommendation` ) generano gli asset seguenti:

- Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso.
- Codice C# per eseguire/assegnare un punteggio al modello generato.
- Codice C# con il codice di training utilizzato per generare il modello.

Le prime due risorse possono essere usate direttamente nelle app per gli utenti finali (ASP.NET Core app Web, servizi, app desktop e altro ancora) per eseguire stime con il modello.

Il terzo asset, il codice di training, Mostra il codice API ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo da poter esaminare l'algoritmo e le impostazioni specifiche del modello.

## <a name="examples"></a>Esempi

Il comando CLI più semplice per un problema di classificazione (AutoML deduce la maggior parte della configurazione dai dati forniti):

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

Un altro comando dell'interfaccia della riga semplice per un problema di regressione:

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

Creazione ed addestramento di un modello di classificazione con un set di dati di training, un set di dati di test e altri argomenti espliciti di personalizzazione:

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a>Opzioni del comando

I `mlnet` comandi dell'attività ml ( `classification` , `regression` e) consentono di eseguire il `recommendation` training di più modelli in base al set di dati fornito e alle opzioni CLI ml.NET. Questi comandi selezionano anche il modello migliore, salvano il modello come file con estensione zip serializzato e generano codice C# correlato per il punteggio e il training.

### <a name="classification-options"></a>Opzioni di classificazione

In esecuzione `mlnet classification` viene eseguito il training di un modello di classificazione. Scegliere questo comando se si vuole che un modello ML classifichi i dati in due o più classi, ad esempio l'analisi dei sentimenti.

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a>Opzioni di regressione

`mlnet regression`L'esecuzione di eseguirà il training di un modello di regressione. Scegliere questo comando se si vuole che un modello ML predichi un valore numerico, ad esempio la stima del prezzo.

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a>Opzioni di raccomandazione

In esecuzione `mlnet recommendation` viene eseguito il training di un modello di raccomandazione.  Scegliere questo comando se si vuole che un modello ML consigli gli elementi agli utenti in base alle classificazioni (ad esempio, raccomandazione del prodotto).

```console
mlnet classification

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

Opzioni di input non valide. lo strumento dell'interfaccia della riga di comando crea un elenco di input validi e un messaggio di errore.

## <a name="dataset"></a>Set di dati

`--dataset | -d` (string)

Questo argomento specifica il percorso file di una delle opzioni seguenti:

- *R: l'intero file del set di dati:* Se si usa questa opzione e l'utente non fornisce `--test-dataset` e `--validation-dataset` , la convalida incrociata (k-fold e così via) o gli approcci di suddivisione automatica dei dati verranno usati internamente per la convalida del modello. In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.

- *B: file del set di dati di training:* Se l'utente fornisce anche set di dati per la convalida del modello (usando `--test-dataset` e `--validation-dataset` , facoltativamente), l' `--dataset` argomento significa solo il "set di dati di training". Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.

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

Di conseguenza, la suddivisione dei dati potrebbe essere 80/10/10 o 75/15/10. Ad esempio:

- Il file di `training-dataset` deve avere il 75% dei dati.
- Il file di `validation-dataset` deve avere il 15% dei dati.
- Il file di `test-dataset` deve avere il 10% dei dati.

In ogni caso, queste percentuali verranno decise dall'utente tramite l'interfaccia della riga di comando che fornirà i file già suddivisi.

## <a name="label-column"></a>Colonna di etichetta

`--label-col`(int o String)

Con questo argomento, è possibile specificare una colonna objective/target specifica (la variabile che si desidera stimare) utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).

Questo argomento viene usato per i problemi di *classificazione* e *regressione* .

## <a name="item-column"></a>Colonna elemento

`--item-col`(int o String)

La colonna Item contiene l'elenco degli elementi che vengono valutati dagli utenti (gli elementi sono consigliati per gli utenti). Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).

Questo argomento viene utilizzato solo per l'attività *Recommendation* .

## <a name="rating-column"></a>Colonna valutazione

`--rating-col`(int o String)

Nella colonna rating è presente l'elenco di classificazioni assegnato agli utenti dagli utenti. Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).

Questo argomento viene utilizzato solo per l'attività *Recommendation* .

## <a name="user-column"></a>Colonna utente

`--user-col`(int o String)

Nella colonna User è presente l'elenco di utenti che assegnano le classificazioni agli elementi. Questa colonna può essere specificata utilizzando il nome della colonna impostato nell'intestazione del set di dati o l'indice numerico della colonna nel file del set di dati (i valori dell'indice di colonna iniziano da 0).

Questo argomento viene utilizzato solo per l'attività *Recommendation* .

## <a name="ignore-columns"></a>Ignora colonne

`--ignore-columns` (string)

Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.

Specificare i nomi delle colonne da ignorare. Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna. È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").

Esempio:

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a>Con intestazione

`--has-header` (bool)

Specificare se i file di set di dati includono una riga di intestazione.
I valori possibili sono:

- `true`
- `false`

L'interfaccia della riga di comando di ML.NET tenterà di rilevare questa proprietà se questo argomento non è specificato dall'utente.

## <a name="train-time"></a>Tempo di training

`--train-time` (string)

Per impostazione predefinita, il tempo massimo di esplorazione/Training è di 30 minuti.

Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni. Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione. In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.

Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.

## <a name="cache"></a>Cache

`--cache` (string)

Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.

Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.

Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria. Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.

È possibile specificare i valori seguenti:

`on`: Forza la cache da usare durante il training.
`off`: Forza la cache a non essere utilizzata durante il training.
`auto`: A seconda dell'euristica AutoML, la cache verrà utilizzata o meno. In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.

Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.

## <a name="name"></a>Nome

`--name` (string)

Nome del progetto di output o della soluzione creata. Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.

Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).

## <a name="output-path"></a>Percorso di output

`--output-path | -o` (string)

Percorso o cartella radice in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

## <a name="verbosity"></a>Livello di dettaglio

`--verbosity | -v` (string)

Imposta il livello di dettaglio dell'output standard.

I valori consentiti sono i seguenti:

- `q[uiet]`
- `m[inimal]`  (per impostazione predefinita)
- `diag[nostic]` (livello informazioni di registrazione)

Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando deve visualizzare un feedback minimo ( `minimal` ) quando funziona, ad esempio indicando che è funzionante e se possibile quanto tempo rimane o quale percentuale del tempo è stata completata.

## <a name="help"></a>Guida

`-h |--help`

Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](../how-to-guides/install-ml-net-cli.md)
- [Panoramica dell'interfaccia della riga di comando di ML.NET](../automate-training-with-cli.md)
- [Esercitazione: analizzare i sentimenti usando l'interfaccia della riga di comando di ML.NET](../tutorials/sentiment-analysis-cli.md)
- [Telemetria nell'interfaccia della riga di comando ML.NET](../resources/ml-net-cli-telemetry.md)
