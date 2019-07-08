---
title: Stimare i prezzi usando la regressione con il generatore di modelli
description: Questa esercitazione illustra come creare un modello di regressione usando il generatore di modelli ML.NET per stimare i prezzi, nel caso specifico le tariffe dei taxi di New York.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d9a6f193d877fc1a679b7a3cafd7491e021cb2ad
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539630"
---
# <a name="predict-prices-using-regression-with-model-builder"></a>Stimare i prezzi usando la regressione con il generatore di modelli

Informazioni su come usare il generatore di modelli ML.NET per compilare un [modello di regressione](../resources/glossary.md#regression) per stimare i prezzi.  L'app console .NET che viene sviluppata in questa esercitazione consente di stimare le tariffe dei taxi di New York in base ai relativi dati storici.

Il modello di stima dei prezzi del generatore di modelli può essere usato in qualsiasi scenario che richieda un valore numerico di stima. Tra gli scenari di esempio vi sono la stima dei prezzi delle abitazioni, la stima della domanda e le previsioni di vendita.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Preparare e identificare i dati
> * Scegliere uno scenario
> * Caricare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Usare il modello per le stime

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="pre-requisites"></a>Prerequisiti

Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".

1. Installare il pacchetto NuGet **Microsoft.ML**:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine del pacchetto, selezionare la scheda **Sfoglia**, trovare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Creare una directory denominata *Dati* nel progetto per archiviare i file del set di dati.

1. Scaricare il set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e salvarlo nella cartella *Dati* creata nel passaggio precedente. Il set di dati consente di eseguire il training del modello di Machine Learning e di valutarlo. Questo set di dati deriva dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *taxi-fare-train.csv* e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

Ogni riga del set di dati `taxi-fare-train.csv` contiene i dettagli delle corse effettuate da un taxi.

1. Aprire il set di dati **taxi-fare-train.csv**

    Il set di dati fornito contiene le colonne seguenti:

    * **vendor_id:** l'ID della società di taxi è una funzionalità.
    * **rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.
    * **passenger_count:** il numero di passeggeri è una funzionalità.
    * **trip_time_in_secs:** il tempo impiegato per il viaggio. Si vuole stimare la tariffa del viaggio prima del termine. Al momento non si conosce la durata del viaggio. Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.
    * **trip_distance:** la distanza del viaggio è una funzionalità.
    * **payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.
    * **fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.

`label` è la colonna sulla quale eseguire le stime. Quando si esegue un'attività di regressione, l'obiettivo è stimare un valore numerico. In questo scenario di stima dei prezzi viene stimato il costo di una corsa in taxi. Pertanto, l'etichetta è **fare_amount**. Gli elementi identificati `features` sono gli input che vengono dati al modello per stimare l'oggetto `label`. In questo caso le colonne rimanenti vengono usate come input o funzionalità per stimare l'importo della tariffa.

## <a name="choose-a-scenario"></a>Scegliere uno scenario

Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli. In questo caso lo scenario è `Price Prediction`. Per un elenco più completo, vedere l'[articolo sulla panoramica del generatore di modelli](../automate-training-with-model-builder.md#scenarios).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi** > **Machine Learning**.
1. Nel passaggio relativo allo scenario dello strumento generatore di modelli, selezionare *Price Prediction*.

## <a name="load-the-data"></a>Caricare i dati

Il generatore di modelli accetta i dati da due origini, un database di SQL Server o un file locale con estensione csv o tsv. Per altre informazioni sui requisiti di formato dei dati, selezionare il [collegamento](../how-to-guides/install-model-builder.md#limitations) seguente.

1. Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare *File* dall'elenco a discesa delle origini dati.
1. Selezionare il pulsante accanto alla casella di testo *Seleziona un file* e usare Esplora File per cercare e selezionare *taxi-fare-test.csv* nella directory *Dati*.
1. Scegliere *fare_amount* nell'elenco a discesa *Label or Column to Predict* (Etichetta o colonna per stima) e passare al passaggio relativo al training dello strumento generatore di modelli.

## <a name="train-the-model"></a>Eseguire il training del modello

L'attività di Machine Learning usata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la regressione. Durante il processo di training del modello, il generatore di modelli esegue il training di modelli separati usando impostazioni e algoritmi di regressione diversi per individuare il modello di prestazioni migliore per il set di dati.

Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati. Usare questo grafico come guida per selezionare un valore adeguato per il campo `Time to train (seconds)`:

*Dimensioni del set di dati  | Tipo di set di dati       | Avg. Durata del training*
------------- | ------------------ | --------------
0 - 10 MB     | Numerico e testo   | 10 sec
10 - 100 MB   | Numerico e testo   | 10 min
100 - 500 MB  | Numerico e testo   | 30 min
500 - 1 GB    | Numerico e testo   | 60 min
1 GB+         | Numerico e testo   | 3 ore+

1. Poiché il file di dati di training è più di 10MB, usare 600 secondi (10 minuti) come valore per *Time to train (seconds)* (Durata training (secondi)).
2. Selezionare *Start Training* (Avvia training).

Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.

- Stato visualizza lo stato di completamento del processo di training.
- Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli. Precisione maggiore indica il modello stimato più correttamente con i dati di test.
- Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.
- Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.

Una volta completato il training, passare alla valutazione.

## <a name="evaluate-the-model"></a>Valutare il modello

Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori. Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce *Best model* (Modello migliore), insieme con le metriche in *Best Model Quality (RSquared)* (Qualità modello migliore). Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative. Selezionare il collegamento seguente per altre informazioni sulla [valutazione delle metriche dei modelli](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).

Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati.

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime

Il risultato del processo di training sarà la creazione di due progetti.

- TaxiFarePredictionML.ConsoleApp: un'applicazione console .NET che contiene il codice del modello di training e il consumo.
- TaxiFarePredictionML.Model: una libreria di classi .NET Standard che contiene i modelli di dati che definiscono lo schema di input e output dei dati del modello, nonché la versione persistente del modello che ha avuto le prestazioni migliori durante il training.

1. Nella sezione relativa al codice dello strumento generatore di modelli selezionare **Added Projects** (Progetti aggiunti) per aggiungere i progetti alla soluzione.
2. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi > Elemento esistente**. Nell'elenco a discesa del tipo di file selezionare `All Files`, passare alla directory del progetto *TaxiFarePredictionML.Model* e selezionare il file `MLModel.zip`. In seguito fare clic con il pulsante destro del mouse sul file `MLModel.zip` appena aggiunto e selezionare *Proprietà*. Per l'opzione Copia nella directory di output, selezionare *Copia se più recente* dall'elenco a discesa.
3. Fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction*. In seguito, selezionare **Aggiungi > Riferimento**. Scegliere il nodo **Progetti > Soluzione** e dall'elenco contrassegnare il progetto *TaxiFarePredictionML.Model* e fare clic su OK.

4. Aprire il file *Program.cs* nel progetto *TaxiFarePrediction*.
5. Aggiungere le istruzioni using seguenti:

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. Aggiungere il metodo `ConsumeModel` alla classe `Program`. `ConsumeModel` creerà un elemento `PredictionEngine` basato sul modello generato dal generatore di modelli per eseguire stime sui nuovi dati e stamparle sulla console.

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. Aggiungere il codice seguente al metodo `Main` ed eseguire l'applicazione.

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:

    ```bash
    Predicted Fare: 16.82245
    ```

Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Preparare e identificare i dati
> * Scegliere uno scenario
> * Caricare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Usare il modello per le stime

Per informazioni su come distribuire il modello, vedere uno degli articoli seguenti relativi a procedure.

> [!div class="nextstepaction"]
> [Distribuire un modello in Funzioni di Azure](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [Distribuire un modello in un'API Web](../how-to-guides/serve-model-web-api-ml-net.md)
