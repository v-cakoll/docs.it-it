---
title: 'Esercitazione: Prevedere i prezzi usando la regressione con Model BuilderTutorial: Predict prices using regression with Model Builder'
description: Questa esercitazione illustra come creare un modello di regressione usando il generatore di modelli ML.NET per stimare i prezzi, nel caso specifico le tariffe dei taxi di New York.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc, mlnet-tooling
ms.openlocfilehash: 750738f8e3c65363e9996667feeccd1b84391f9f
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438236"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a>Esercitazione: Prevedere i prezzi usando la regressione con Model BuilderTutorial: Predict prices using regression with Model Builder

Informazioni su come usare il generatore di modelli ML.NET per compilare un modello di regressione per stimare i prezzi.  L'app console .NET che viene sviluppata in questa esercitazione consente di stimare le tariffe dei taxi di New York in base ai relativi dati storici.

Il modello di stima dei prezzi del generatore di modelli può essere usato in qualsiasi scenario che richieda un valore numerico di stima. Tra gli scenari di esempio vi sono la stima dei prezzi delle abitazioni, la stima della domanda e le previsioni di vendita.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare i dati
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="pre-requisites"></a>Prerequisiti

Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare **un'applicazione console di C .NET Core** denominata "TaxiFarePrediction". Assicurarsi che **l'opzione Inserisci soluzione e progetto nella stessa directory** sia **deselezionata** (VS 2019) o **l'opzione Crea directory per soluzione** sia **selezionata** (VS 2017).

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Creare una directory denominata *Dati* nel progetto per archiviare i file del set di dati.

1. Il set di dati usato per il training e la valutazione del modello di Machine Learning è ricavato in origine dal set di dati NYC TLC Taxi Trip.

    1. Per scaricare il set di dati, passare al [collegamento per il download di taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).

    1. Quando si carica la pagina, fare clic con il pulsante destro del mouse in un punto qualsiasi della pagina e scegliere **Salva con nome**.

    1. Usare la **finestra di dialogo Salva con nome** per salvare il file nella cartella *Dati* creata nel passaggio precedente.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *taxi-fare-train.csv* e selezionare **Proprietà**. In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.

Ogni riga del set di dati `taxi-fare-train.csv` contiene i dettagli delle corse effettuate da un taxi.

1. Aprire il set di dati **taxi-fare-train.csv**

    Il set di dati fornito contiene le colonne seguenti:

    - **vendor_id:** l'ID della società di taxi è una funzionalità.
    - **rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.
    - **passenger_count:** il numero di passeggeri è una funzionalità.
    - **trip_time_in_secs:** il tempo impiegato per il viaggio. Si vuole stimare la tariffa del viaggio prima del termine. Al momento non si conosce la durata del viaggio. Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.
    - **trip_distance:** la distanza del viaggio è una funzionalità.
    - **payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.
    - **fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.

`label` è la colonna sulla quale eseguire le stime. Quando si esegue un'attività di regressione, l'obiettivo è stimare un valore numerico. In questo scenario di stima dei prezzi viene stimato il costo di una corsa in taxi. Pertanto, l'etichetta è **fare_amount**. Gli elementi identificati `features` sono gli input che vengono dati al modello per stimare l'oggetto `label`. In questo caso, il resto delle colonne, ad eccezione di **trip_time_in_secs** vengono utilizzate come funzioni o input per stimare l'importo della tariffa.

## <a name="choose-a-scenario"></a>Scegliere uno scenario

Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli. In questo caso lo scenario è `Price Prediction`.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto *TaxiFarePrediction* e selezionare **Aggiungi** > **Machine Learning**.
1. Nel passaggio relativo allo scenario dello strumento generatore di modelli, selezionare *Price Prediction*.

## <a name="load-the-data"></a>Caricare i dati

Il generatore di modelli accetta i dati da due origini, un database di SQL Server o un file locale in formato csv o tsv.

1. Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare *File* dall'elenco a discesa delle origini dati.
1. Selezionare il pulsante accanto alla casella di testo *Seleziona un file* e usare Esplora File per cercare e selezionare *taxi-fare-test.csv* nella directory *Dati*.
1. Scegliere *fare_amount* nell'elenco a discesa *Colonna da stimare (etichetta).*
1. Espandere l'elenco a discesa Colonne di *input (funzionalità)* e deselezionare la colonna *trip_time_in_secs* per escluderla come funzionalità durante il training.  Passare al passaggio del training dello strumento Generatore di modelli.

## <a name="train-the-model"></a>Eseguire il training del modello

L'attività di Machine Learning usata per eseguire il training del modello di stima dei prezzi in questa esercitazione è la regressione. Durante il processo di training del modello, il generatore di modelli esegue il training di modelli separati usando impostazioni e algoritmi di regressione diversi per individuare il modello di prestazioni migliore per il set di dati.

Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati. Model Builder seleziona automaticamente un valore predefinito per **Time to train (seconds)** in base alle dimensioni dell'origine dati.

1. Lasciare il valore predefinito come per il tempo di *formazione (secondi)* a meno che non si preferisce allenarsi per un periodo di tempo più lungo.
2. Selezionare *Start Training* (Avvia training).

Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.

- Stato visualizza lo stato di completamento del processo di training.
- Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli. Precisione maggiore indica il modello stimato più correttamente con i dati di test.
- Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.
- Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.

Una volta completato il training, passare alla valutazione.

## <a name="evaluate-the-model"></a>Valutare il modello

Il risultato del passaggio relativo al training è rappresentato dal modello con le prestazioni migliori. Nel passaggio di valutazione dello strumento generatore di modelli la sezione di output conterrà l'algoritmo usato dal modello con le prestazioni migliori nella voce *Best model* (Modello migliore), insieme con le metriche in *Best Model Quality (RSquared)* (Qualità modello migliore). Viene visualizzata anche una tabella di riepilogo con i cinque modelli migliori e le metriche relative.

Se non si è soddisfatti della precisione delle metriche,un modo semplice per migliorarla consiste nell'aumentare la durata del training del modello o nell'usare più dati. In caso contrario, passare al passaggio del codice.

## <a name="add-the-code-to-make-predictions"></a>Aggiungere il codice per eseguire stime

Il risultato del processo di training sarà la creazione di due progetti.

- TaxiFarePredictionML.ConsoleApp: un'applicazione console .NET Core che contiene il training del modello e il codice di consumo di esempio.
- TaxiFarePredictionML.Model: libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del `ConsumeModel` modello di input e di output, la versione salvata del modello con le prestazioni migliori durante il training e una classe helper chiamata per eseguire stime.

1. Nel passaggio del codice dello strumento generatore di modelli selezionare **Add Projects** (Aggiungi progetti) per aggiungere i progetti generati automaticamente alla soluzione.
1. Aprire il file *Program.cs* nel progetto *TaxiFarePrediction*.
1. Aggiungere l'istruzione using seguente per fare riferimento al progetto *TaxiFarePredictionML.Model:Add* the following using statement to reference the TaxiFarePredictionML.Model project:

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. Per eseguire una stima dei nuovi dati usando il `ModelInput` modello, `Main` creare una nuova istanza della classe all'interno del metodo dell'applicazione. Si noti che l'importo della tariffa non fa parte dell'input, perché il modello genererà la stima per tale importo.

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. Utilizzare `Predict` il metodo `ConsumeModel` della classe . Il `Predict` metodo carica il modello [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) sottoposto a training, crea un per il modello e lo usa per eseguire stime sui nuovi dati.

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. Eseguire l'applicazione.

    L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:

    ```bash
    Predicted Fare: 14.96086
    ```

Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare i dati
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

### <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:

- [Scenari del generatore di modelli](../automate-training-with-model-builder.md#scenario)
- [Regressione](../resources/glossary.md#regression)
- [Metriche del modello di regressione](../resources/metrics.md#evaluation-metrics-for-regression-and-recommendation)
- [Set di dati NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
