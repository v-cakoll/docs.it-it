---
title: Comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET
description: Panoramica, esempi e riferimento per il comando auto-train nello strumento dell'interfaccia della riga di comando di ML.NET.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 28eb56eb018e3d1cc76f300ee78c298af77c9b91
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557929"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a>Comando 'auto-train' nell'interfaccia della riga di comando di ML.NET

> [!NOTE]
> Questo argomento fa riferimento all'interfaccia della riga di comando di ML.NET e al Machine Learning automatico, attualmente in anteprima, e il materiale può essere soggetto a modifiche.

Il comando `auto-train` è il comando principale dello strumento dell'interfaccia della riga di comando di ML.NET. Il comando consente di generare un modello di ML.NET di buona qualità (file di modello serializzato con estensione zip) e il codice C# di esempio per eseguire/assegnare un punteggio al modello. Viene anche generato automaticamente il codice C# per creare/eseguire il training del modello per ricercare l'algoritmo e le impostazioni usate per il "miglior modello" generato.

Poiché è possibile generare questi asset dal proprio set di dati senza scrivere alcun codice, è possibile migliorare la produttività anche se si conosce già ML.NET.

Attualmente, le attività di Machine Learning supportate dall'interfaccia della riga di comando di ML.NET sono:

- `binary-classification`
- `multiclass-classification`
- `regression`

- In futuro saranno supportate altre attività di Machine Learning, ad esempio
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

Esempio di utilizzo nel prompt dei comandi:

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

Il comando `mlnet auto-train` genera gli asset seguenti:

- Un file di modello serializzato con estensione zip ("miglior modello") pronto per l'uso.
- Il codice C# per eseguire/assegnare un punteggio al modello generato (per effettuare previsioni nelle app degli utenti finali con il modello).
- Il codice C# con il codice di training usato per generare il modello (a scopo di apprendimento).

I primi due asset possono essere usati direttamente nelle app degli utenti finali (app Web ASP.NET Core, servizi, app desktop, ecc.) per effettuare previsioni con il modello di Machine Learning generato.

Poiché il terzo asset, il codice di training, mostra il codice API di ML.NET usato dall'interfaccia della riga di comando per eseguire il training del modello generato, è possibile individuare il trainer/algoritmo specifico e gli iperparametri selezionati dall'interfaccia della riga di comando e dal motore di Machine Learning automatico di ML.NET.

## <a name="the-auto-train-command-uses-the-automl-engine"></a>Il comando 'auto-train' usa il motore di Machine Learning automatico

L'interfaccia della riga di comando usa il motore di Machine Learning automatico di ML.NET (pacchetto NuGet) per cercare in modo intelligente i modelli di migliore qualità, come illustrato nel diagramma seguente:

![immagine](./media/ml-net-automl-working-diagram.png "Motore di Machine Learning automatico usato all'interno dell'interfaccia della riga di comando di ML.NET")

Quando si esegue lo strumento dell'interfaccia della riga comando ML.NET con il comando 'auto-train', è possibile osservare che lo strumento prova a eseguire numerose iterazioni con diversi algoritmi e combinazioni di configurazione.

## <a name="reference-for-auto-train-command"></a>Riferimento per il comando 'auto-train'

## <a name="examples"></a>Esempi

Comando dell'interfaccia della riga di comando più semplice per un problema di classificazione binaria (la funzionalità di Machine Learning automatico dovrà dedurre la maggior parte della configurazione dai dati forniti):

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

Un altro comando dell'interfaccia della riga semplice per un problema di regressione:

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

Creare ed eseguire il training di un modello di classificazione binaria con un set di dati con training, un set di dati di test e ulteriori argomenti espliciti di personalizzazione:

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a>nome

`mlnet auto-train` - Esegue il training di più modelli ('n' iterazioni) in base al set di dati fornito e seleziona il modello migliore, lo salva come file serializzato con estensione zip e genera il codice C# correlato per l'assegnazione del punteggio e il training.

## <a name="synopsis"></a>Riepilogo

```console
> mlnet auto-train

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

Le opzioni di input non valide devono causare la generazione da parte dello strumento dell'interfaccia della riga di comando di un elenco di valori di input validi e un messaggio di errore che indica l'argomento mancante, se applicabile.

## <a name="options"></a>Opzioni

 ----------------------------------------------------------

`--task | --mltask | -T` (string)

Stringa singola che specifica il problema di Machine Learning da risolvere. Ad esempio, una delle attività seguenti (l'interfaccia della riga di comando supporterà tutte le attività supportate nella funzionalità di Machine Learning automatico):

- `regression` - Scegliere se verrà usato il modello di Machine Learning per effettuare la previsione di un valore numerico
- `binary-classification` - Scegliere se il risultato del modello di Machine Learning ha due valori booleani categorici possibili (0 o 1).
- `multiclass-classification` - Scegliere se il risultato del modello di Machine Learning ha più valori categorici possibili.

Nelle versioni successive saranno supportati ulteriori scenari e attività di Machine Learning, ad esempio `recommendations`, `clustering` e `ranking`.

 In questo argomento è necessario specificare una sola attività di Machine Learning.

 ----------------------------------------------------------

`--dataset | -d` (string)

Questo argomento specifica il percorso file di una delle opzioni seguenti:

- *A: File del set di dati completo:* se si usa questa opzione e l'utente non specifica `--test-dataset` e `--validation-dataset`, verranno usati internamente gli approcci di convalida incrociata (k-fold e così via) o di suddivisione dati automatizzata per la convalida del modello. In questo caso l'utente dovrà specificare soltanto il percorso file del set di dati.

- *B: File del training set:* se l'utente specifica anche set di dati per la convalida del modello (usando `--test-dataset` e facoltativamente `--validation-dataset`), l'argomento `--dataset` indica solo la presenza del "training set". Ad esempio, quando viene usato un approccio 80% - 20% per convalidare la qualità del modello e ottenere le metriche di accuratezza, il "training set" avrà l'80% dei dati, mentre il "set di dati di test" avrà il 20% dei dati.

----------------------------------------------------------

`--test-dataset | -t` (string)

Percorso del file del set di dati di test, ad esempio quando viene usato un approccio 80% - 20% durante le convalide regolari per ottenere le metriche di accuratezza.

Se viene usato `--test-dataset`, è necessario specificare anche `--dataset`.

L'argomento `--test-dataset` è facoltativo, a meno che non venga usato --validation-dataset. In questo caso, l'utente deve usare i tre argomenti.

----------------------------------------------------------

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

----------------------------------------------------------

`--label-column-name | -n` (string)

Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando il nome della colonna impostato nell'intestazione del set di dati.

Questo argomento viene usato solo per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*. Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.

----------------------------------------------------------

`--label-column-index | -i` (int)

Con questo argomento è possibile specificare una colonna obiettivo/destinazione (la variabile di cui effettuare la previsione) usando l'indice numerico della colonna nel file del set di dati (i valori di indice della colonna iniziano da 1).

*Nota:* se l'utente usa anche `--label-column-name`, viene usato `--label-column-name`.

Questo argomento viene usato per le attività di Machine Learning con supervisione, ad esempio un *problema di classificazione*. Non può essere usato per le attività di Machine Learning senza supervisione, ad esempio il *clustering*.

----------------------------------------------------------

`--ignore-columns | -I` (string)

Con questo argomento è possibile ignorare le colonne esistenti nel file del set di dati in modo che non vengano caricate e usate dai processi di training.

Specificare i nomi delle colonne da ignorare. Usare ', ' (virgola seguita da uno spazio) oppure ' ' (spazio) per separare più nomi di colonna. È possibile usare le virgolette per nomi di colonna che contengono uno spazio vuoto (ad esempio, "accesso eseguito").

Esempio:

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

`--has-header | -h` (bool)

Specificare se i file di set di dati includono una riga di intestazione.
I possibili valori sono:
- `true`
- `false`

Il valore predefinito è `true` se questo argomento non viene specificato dall'utente.

Per usare l'argomento `--label-column-name` è necessario che il file del set di dati includa un'intestazione e che `--has-header` sia impostato su `true` (impostazione predefinita).

----------------------------------------------------------

`--max-exploration-time | -x` (string)

Per impostazione predefinita, il tempo massimo di esplorazione è 10 secondi.

Questo argomento imposta il tempo massimo (in secondi) per il processo per l'esplorazione di più trainer e configurazioni. Il tempo configurato può essere superato se il tempo specificato è troppo breve (ad esempio, 2 secondi) per una singola iterazione. In questo caso, il tempo effettivo corrisponde al tempo necessario per produrre una configurazione di modello in una singola iterazione.

Il tempo necessario per le iterazioni può variare a seconda delle dimensioni del set di dati.

----------------------------------------------------------

`--cache | -c` (string)

Se si usa la memorizzazione nella cache, verrà caricato in memoria l'intero training set.

Per set di dati di piccole e medie dimensioni, l'uso della cache può migliorare nettamente le prestazioni di training riducendo il tempo di training rispetto a quando non si usa la cache.

Tuttavia, per i set di dati di grandi dimensioni, il caricamento di tutti i dati in memoria può influire negativamente ed esaurire la memoria. Quando viene eseguito il training con file di set di dati di grandi dimensioni senza usare la cache, ML.NET esegue lo streaming di blocchi di dati dell'unità quando è necessario caricare più dati durante il training.

È possibile specificare i valori seguenti:

`on`: impone l'uso della cache durante il training.
`off`: impedisce l'uso della cache durante il training.
`auto`: l'uso della cache è determinato dalle regole euristiche della funzionalità di Machine Learning automatico. In genere i set di dati di piccole e medie dimensioni usano la cache, mentre i set di dati di grandi dimensioni non usano la cache se viene usata l'opzione `auto`.

Se non si specifica il parametro `--cache`, viene usata la configurazione `auto` della cache per impostazione predefinita.

----------------------------------------------------------

`--name | -N` (string)

Nome del progetto di output o della soluzione creata. Se viene specificato alcun nome, viene usato il nome `sample-{mltask}`.

Verrà assegnato lo stesso nome anche al file di modello di ML.NET (file con estensione zip).

----------------------------------------------------------

`--output-path | -o` (string)

Percorso o cartella radice in cui posizionare l'output generato. Il valore predefinito è la directory corrente.

----------------------------------------------------------

`--verbosity | -V` (string)

Imposta il livello di dettaglio dell'output standard.

I valori consentiti sono:

- `q[uiet]`
- `m[inimal]`  (per impostazione predefinita)
- `diag[nostic]` (livello informazioni di registrazione)

Per impostazione predefinita, lo strumento dell'interfaccia della riga di comando dovrebbe visualizzare un feedback minimo, ad esempio indicare che è attivo e se possibile il tempo rimanente o la percentuale di tempo trascorso.

----------------------------------------------------------

`-h|--help`

Visualizza le informazioni della Guida per il comando con una descrizione per ogni parametro.

----------------------------------------------------------

## <a name="see-also"></a>Vedere anche

- [Come installare lo strumento dell'interfaccia della riga comando ML.NET](../how-to-guides/install-ml-net-cli.md)
- [Automatizzare il training del modello con l'interfaccia della riga di comando di ML.NET](../automate-training-with-cli.md)
- [Esercitazione: Generare automaticamente un classificatore binario con l'interfaccia della riga di comando di ML.NET](../tutorials/mlnet-cli.md)
- [Telemetria nell'interfaccia della riga di comando di ML.NET](../resources/ml-net-cli-telemetry.md)
