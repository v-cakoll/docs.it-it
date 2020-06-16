---
title: Analizzare il sentiment usando l'interfaccia della riga di comando di ML.NET
description: Generare automaticamente un modello di ML e il codice C# correlato per un set di dati di esempio
author: cesardl
ms.author: cesardl
ms.date: 06/03/2020
ms.custom: mvc,mlnet-tooling
ms.topic: tutorial
ms.openlocfilehash: aab59463daad30748277602b9ab1d8ca2f3fa1f5
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767676"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a>Analizzare il sentiment usando l'interfaccia della riga di comando di ML.NET

Di seguito sono riportate informazioni su come usare l'interfaccia della riga di comando ML.NET per generare automaticamente un modello ML.NET e il codice C# sottostante. Fornire il set di dati e l'attività di machine learning da implementare e l'interfaccia della riga di comando usa il motore AutoML per creare il codice sorgente di generazione e distribuzione del modello, nonché il modello di classificazione.

In questa esercitazione verranno eseguite le operazioni seguenti:
> [!div class="checklist"]
>
> - Preparare i dati per l'attività di Machine Learning selezionata
> - Eseguire il comando ' mlnet Classification ' dall'interfaccia della riga di comando
> - Rivedere i risultati delle metriche di qualità
> - Comprendere il codice C# generato per usare il modello nell'applicazione
> - Esplorare il codice C# generato usato per il training del modello

> [!NOTE]
> Questo argomento si riferisce all'interfaccia della riga di comando ML.NET, attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per ulteriori informazioni, visitare la pagina [ml.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) .

L'interfaccia della riga di comando ML.NET fa parte di ML.NET e l'obiettivo principale è "democratizzare" ML.NET per gli sviluppatori di .NET in modo che non sia necessario scrivere codice da zero quando iniziano a usarlo.

È possibile eseguire l'interfaccia della riga di comando ML.NET in qualsiasi prompt dei comandi (Windows, Mac o Linux) per generare modelli e codice sorgente ML.NET di buona qualità in base ai set di dati di training specificati.

## <a name="pre-requisites"></a>Prerequisiti

- [.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) o versione successiva
- Opzionale [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
- [Interfaccia della riga di comando ML.NET](../how-to-guides/install-ml-net-cli.md)

È possibile eseguire i progetti in codice C# generati in Visual Studio o con `dotnet run` (interfaccia della riga di comando di .NET Core).

## <a name="prepare-your-data"></a>Preparare i dati

Verrà usato un set di dati esistente per uno scenario di 'analisi del sentiment', che è un'attività di Machine Learning con classificazione binaria. È possibile usare in modo simile un set di dati personalizzato, con il modello e il codice che verranno generati automaticamente.

1. Scaricare il [file ZIP del set di dati Sentiment Labeled Sentences UCI (vedere le citazioni nella nota seguente)](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) e decomprimerlo in una cartella a scelta.

    > [!NOTE]
    > I set di dati usati in questa esercitazione provengono da 'From Group to Individual Labels using Deep Features', Kotzias et al, KDD 2015 e ospitato nel repository di Machine Learning UCI-Dua, D. e Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

2. Copiare il file `yelp_labelled.txt` in qualsiasi cartella creata in precedenza, ad esempio `/cli-test`.

3. Aprire un prompt dei comandi e passare alla cartella in cui è stato copiato il file del set di dati. Ad esempio:

    ```console
    cd /cli-test
    ```

    Usando qualsiasi editor di testo, ad esempio Visual Studio Code, è possibile aprire ed esplorare il file del set di dati `yelp_labelled.txt`. La struttura è la seguente:

    - Il file non ha intestazione. Verrà usato l'indice della colonna.

    - Sono presenti solo due colonne:

        | Testo (indice di colonna 0) | Etichetta (indice di colonna 1)|
        |--------------------------|-------|
        | Wow... Questo posto è stato apprezzato. | 1 |
        | Crust is not good. | 0 |
        | Not tasty and the texture was just nasty. | 0 |
        | ...MOLTE ALTRE RIGHE DI TESTO... | ...(1 o 0)... |

    Assicurarsi di chiudere il file del set di dati nell'editor.

    Ora è possibile iniziare a usare l'interfaccia della riga di comando per questo scenario di 'analisi del sentiment'.

    > [!NOTE]
    > Al termine di questa esercitazione, è anche possibile provare con i propri set di impostazioni purché siano pronti per essere usati per le attività ML attualmente supportate dall'anteprima dell'interfaccia della riga di comando di ML.NET, ovvero *"classificazione binaria", "classificazione", "regressione"* e *"raccomandazione"*.

## <a name="run-the-mlnet-classification-command"></a>Eseguire il comando ' mlnet Classification '

1. Eseguire il comando seguente dell'interfaccia della riga di comando ML.NET:

    ```console
    mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
    ```

    Questo comando esegue il ** `mlnet classification` comando**:
    - per l' **attività** di *classificazione* ml
    - Usa il **file del set di dati `yelp_labelled.txt`** come set di dati di training e di test (internamente l'interfaccia della riga di comando usa la convalida incrociata oppure lo divide in due set di dati, uno per il training e l'altro per il test)
    - Dove la **colonna obiettivo/destinazione** da stimare (solitamente definita **'etichetta'**) è la **colonna con indice 1**, ossia la seconda colonna, perché l'indice è a base zero
    - Non **usa un'intestazione di file** con i nomi di colonna perché questo specifico set di dati non ha un'intestazione
    - il **tempo di esplorazione/training di destinazione** per l'esperimento è **10 secondi**

    L'output dell'interfaccia della riga di comando sarà simile a:

    ![Classificazione dell'interfaccia della riga di comando ML.NET in PowerShell](./media/mlnet-cli/mlnet-classification-powershell.gif)

    In questo caso specifico, in appena 10 secondi e con il piccolo set di dati fornito, l'interfaccia della riga di comando è in grado di eseguire poche iterazioni, il che significa che il training viene ripetuto più volte in base a diverse combinazioni di algoritmi/configurazione con trasformazioni interne dei dati e iperparametri dell'algoritmo differenti.

    Infine, il modello di "qualità migliore" trovato in 10 secondi usa uno specifico trainer/algoritmo con qualsiasi specifica configurazione. A seconda del tempo di esplorazione, il comando può produrre un risultato diverso. La selezione si basa sulle diverse metriche illustrate, ad esempio `Accuracy`.

    **Informazioni sulle metriche di qualità del modello**

    La prima metrica, e anche la più facile, per valutare un modello di classificazione binaria è l'accuratezza, semplice da comprendere. L'accuratezza corrisponde alla percentuale di stime corrette con un set di dati di test, che dovrebbe essere quanto più vicino possibile al 100% (1,00).

    Tuttavia, in alcuni casi la misurazione con la semplice metrica dell'accuratezza non è sufficiente, in particolare quando l'etichetta (0 e 1 in questo esempio) non è bilanciata nel set di dati di test.

    Per altre metriche e informazioni più **dettagliate sulle metriche** , ad esempio l'accuratezza, l'AUC, il AUCPR e il Punteggio F1 usati per valutare i diversi modelli, vedere informazioni sulle [metriche di ml.NET](../resources/metrics.md).

    > [!NOTE]
    > È possibile provare questo stesso set di dati e specificare alcuni minuti per `--max-exploration-time` (ad esempio, tre minuti in modo da specificare 180 secondi) in modo da trovare un "modello ottimale" migliore con una configurazione della pipeline di training diversa per questo set di dati, che con 1000 righe è piuttosto piccolo.

    Per trovare un modello di "qualità migliore/buona" pronto per la produzione e destinato a set di dati più grandi, è consigliabile sperimentare con l'interfaccia della riga di comando specificando in genere una quantità molto maggiore di tempo di esplorazione a seconda delle dimensioni del set di dati. Infatti, in molti casi potrebbero essere necessarie diverse ore di tempo di esplorazione, soprattutto se il set di dati contiene molte righe e colonne.

1. L'esecuzione del comando precedente ha generato gli asset seguenti:

    - Un file ZIP di modello serializzato ("modello ottimale") pronto per l'uso.
    - Il codice C# per eseguire e assegnare punteggi al modello generato (per eseguire stime nelle app per utenti finali con il modello).
    - Il codice di training C# usato per generare il modello (a scopo di apprendimento).
    - Un file di log con tutte le iterazioni esplorate che include specifiche informazioni dettagliate su ogni algoritmo provato con la relativa combinazione di iperparametri e trasformazioni di dati.

    I primi due asset (il modello del file ZIP e il codice C# per eseguirlo) possono essere usati direttamente nelle app per utenti finali (app Web ASP.NET Core, servizi, app desktop e così via) per eseguire stime con il modello di ML generato.

    Il terzo asset, ossia il codice di training, mostra quale codice API ML.NET è stato usato dall'interfaccia della riga di comando per eseguire il training del modello generato, in modo che sia possibile esaminare il trainer/algoritmo e gli iperparametri specifici selezionati dall'interfaccia della riga di comando.

Questi asset enumerati vengono descritti nei passaggi successivi dell'esercitazione.

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a>Esplorare il codice C# generato da usare per eseguire le stime con il modello

1. In Visual Studio (2017 o 2019) aprire la soluzione generata nella cartella denominata `SampleClassification` all'interno della cartella di destinazione originale, che per questa esercitazione è `/cli-test`. Dovrebbe essere visualizzata una soluzione simile a:

    > [!NOTE]
    > Nell'esercitazione suggeriamo di usare Visual Studio, ma è anche possibile esplorare il codice C# generato (due progetti) con qualsiasi editor di testo ed eseguire l'app console generata con `dotnet CLI` in un computer macOS, Linux o Windows.

    ![Soluzione VS generata dall'interfaccia della riga di comando](./media/mlnet-cli/mlnet-cli-solution-explorer.png)

    - La **libreria di classi** generata, contenente il modello di ML serializzato (file ZIP) e le classi di dati (modelli di dati), si può usare direttamente nell'applicazione per utenti finali, anche facendovi riferimento direttamente o, se si preferisce, spostando il codice.
    - L'**app console** generata contiene codice di esecuzione che è necessario rivedere. Quindi in genere si riutilizza il 'codice di assegnazione punteggi' (che esegue il modello di ML per le stime), spostando questo semplice codice, composto da poche righe, nell'applicazione per utenti finali in cui si vogliono eseguire le stime.

1. Aprire i file delle classi **ModelInput.cs** e **ModelOutput.cs** all'interno del progetto di libreria di classi. Si noterà che queste classi sono 'classi di dati' o POCO usate per memorizzare i dati. Si tratta di 'codice boilerplate', ma è utile generarlo se il set di dati contiene decine o anche centinaia di colonne.
    - La classe `ModelInput` viene usata durante la lettura di dati dal set di dati.
    - La classe `ModelOutput` viene usata per ottenere il risultato di stima (dati di stima).

1. Aprire il file Program.cs ed esplorare il codice. Con poche righe è possibile eseguire il modello ed eseguire una stima del campione.

    ```csharp
    static void Main(string[] args)
    {
        // Create single instance of sample data from first line of dataset for model input
        ModelInput sampleData = new ModelInput()
        {
            Col0 = @"Wow... Loved this place.",
        };

        // Make a single prediction on the sample data and print results
        var predictionResult = ConsumeModel.Predict(sampleData);

        Console.WriteLine("Using model to make single prediction -- Comparing actual Col1 with predicted Col1 from sample data...\n\n");
        Console.WriteLine($"Col0: {sampleData.Col0}");
        Console.WriteLine($"\n\nPredicted Col1 value {predictionResult.Prediction} \nPredicted Col1 scores: [{String.Join(",", predictionResult.Score)}]\n\n");
        Console.WriteLine("=============== End of process, hit any key to finish ===============");
        Console.ReadKey();
    }
    ```

    - Le prime righe di codice creano un *solo dato di esempio*, in questo caso basato sulla prima riga del set di dati da utilizzare per la stima. È anche possibile creare i propri dati hardcoded aggiornando il codice:

        ```csharp
        ModelInput sampleData = new ModelInput()
        {
            Col0 = "The ML.NET CLI is great for getting started. Very cool!"
        };
        ```

    - La riga di codice successiva usa il `ConsumeModel.Predict()` metodo sui dati di input specificati per eseguire una stima e restituire i risultati in base allo schema ModelOutput.cs.
    - Le ultime righe del codice stampano il proprietà dei dati di esempio (in questo caso il commento), nonché la stima del sentimento e i punteggi corrispondenti per i sentimenti positivi (1) e il sentimento negativo (2).

1. Eseguire il progetto, usando i dati di esempio originali caricati dalla prima riga del set di dati oppure i dati hardcoded personalizzati. Si dovrebbe ottenere una stima simile a:

![INTERFACCIA della riga di comando di ML.NET eseguire l'app da Visual Studio](./media/mlnet-cli/mlnet-cli-console-app.png))

1. Provare a sostituire i dati di esempio hardcoded con altre frasi con sentiment diverso e vedere come viene stimato un sentiment positivo o negativo dal modello.

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a>Inserire le stime del modello di ML nelle applicazioni per utenti finali

È possibile usare un codice di assegnazione punteggi simile a quello del modello di ML per eseguirlo nell'applicazione per utenti finali ed eseguire stime.

È ad esempio possibile spostare direttamente il codice in qualsiasi applicazione desktop Windows, come **WPF** e **WinForms**, ed eseguire il modello come è stato fatto nell'app console.

È tuttavia necessario ottimizzare il modo in cui vengono implementate queste righe di codice per eseguire un modello di ML, ossia memorizzare nella cache il file ZIP e caricarlo una sola volta, e avere oggetti singleton invece di crearli per ogni richiesta, soprattutto se l'applicazione deve essere scalabile, ad esempio un'applicazione Web o un servizio distribuito, come descritto nella sezione seguente.

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a>Esecuzione di modelli ML.NET in app Web e servizi ASP.NET Core scalabili (app multithread)

La creazione dell'oggetto del modello (`ITransformer` caricato da un file ZIP del modello) e dell'oggetto `PredictionEngine` deve essere ottimizzata in particolare per l'esecuzione in app Web scalabili e servizi distribuiti. Per il primo caso, l'oggetto del modello `ITransformer`, l'ottimizzazione è semplice e diretta. Poiché l'oggetto `ITransformer` è thread-safe, è possibile memorizzarlo nella cache come oggetto singleton o statico in modo da caricare il modello una sola volta.

Per il secondo oggetto, `PredictionEngine`, non è così facile perché l'oggetto `PredictionEngine` non è thread-safe, quindi non è possibile crearne un'istanza come oggetto singleton o statico in un'app ASP.NET Core. Questo problema relativo a scalabilità e thread-safe viene descritto in dettaglio in questo [post di blog](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).

Tuttavia, la situazione è più semplice rispetto a quanto spiegato in questo post. Abbiamo adottato un approccio più semplice e abbiamo creato un utile **'pacchetto di integrazione .NET Core'** che è possibile usare con facilità nelle app e nei servizi ASP.NET Core registrandolo nei servizi DI (Dependency Injection) per poi usarlo direttamente dal codice. Per informazioni, vedere l'esercitazione e l'esempio seguenti:

- [Esercitazione: esecuzione di modelli ML.NET su app Web scalabili ASP.NET Core e WebAPI](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Esempio: modello di ML.NET scalabile in ASP.NET Core WebAPI](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a>Esplorare il codice C# generato usato per il training del modello di "qualità ottimale"

Per un livello di formazione più avanzato, è anche possibile esplorare il codice C# generato usato dall'interfaccia della riga di comando per il training del modello generato.

Questo 'codice di training del modello' viene attualmente generato nella classe personalizzata generata, denominata `ModelBuilder`, quindi è possibile esaminarlo.

Soprattutto, per questo specifico scenario (modello di analisi del sentiment) è anche possibile confrontare il codice di training generato con il codice descritto nell'esercitazione seguente:

- Confrontare: [esercitazione: usare ml.NET in uno scenario di classificazione binaria di analisi dei sentimenti](sentiment-analysis.md).

È interessante confrontare l'algoritmo scelto e la configurazione della pipeline dell'esercitazione con il codice generato dall'interfaccia della riga di comando. A seconda del tempo dedicato all'iterazione e alla ricerca di modelli migliori, l'algoritmo scelto può essere diverso, così come gli specifici iperparametri e la configurazione della pipeline.

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Preparare i dati per l'attività di ML selezionata (problema da risolvere)
> - Eseguire il comando "mlnet Classification" nello strumento dell'interfaccia della riga di comando
> - Rivedere i risultati delle metriche di qualità
> - Comprendere il codice C# generato per l'esecuzione del modello (codice da usare nell'app per utenti finali)
> - Esplorare il codice C# generato usato per eseguire il training del modello "qualità migliore" (a scopo di guadagno)

## <a name="see-also"></a>Vedere anche

- [Automatizzare il training del modello con l'interfaccia della riga di comando di ML.NET](../automate-training-with-cli.md)
- [Esercitazione: esecuzione di modelli ML.NET su app Web scalabili ASP.NET Core e WebAPI](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [Esempio: modello di ML.NET scalabile in ASP.NET Core WebAPI](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [Guida di riferimento per i comandi di training automatico dell'interfaccia della riga di comando ML.NET](../reference/ml-net-cli-reference.md)
- [Telemetria nell'interfaccia della riga di comando ML.NET](../resources/ml-net-cli-telemetry.md)
