---
title: 'Esercitazione: ispezione visiva automatizzata tramite trasferimento Learning'
description: Questa esercitazione illustra come usare Transfer learning per eseguire il training di un modello di apprendimento approfondito di TensorFlow in ML.NET usando l'API di rilevamento immagini per classificare le immagini di superfici concrete come incrinate o non incrinate.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2915259d7c7031b9e699c7fd0cf65cf723c41680
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144422"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a>Esercitazione: ispezione visiva automatizzata tramite il trasferimento dell'apprendimento con l'API di classificazione delle immagini ML.NET

Informazioni su come eseguire il training di un modello di apprendimento avanzato personalizzato usando il servizio di formazione per il trasferimento, un modello TensorFlow pretrainato e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Informazioni sul problema
> - Informazioni sull'API di classificazione delle immagini ML.NET
> - Informazioni sul modello sottoposto a training
> - Usare Transfer learning per eseguire il training di un modello di classificazione immagini TensorFlow personalizzato
> - Classificare le immagini con il modello personalizzato

## <a name="prerequisites"></a>Prerequisiti

- [Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

## <a name="image-classification-transfer-learning-sample-overview"></a>Panoramica dell'esempio di apprendimento della classificazione delle immagini Transfer

Questo esempio è un'applicazione console .NET Core C# che classifica le immagini usando un modello TensorFlow di apprendimento avanzato con training. Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) in GitHub.

## <a name="understand-the-problem"></a>Informazioni sul problema

La classificazione delle immagini è un problema di visione artificiale. La classificazione delle immagini acquisisce un'immagine come input e la Categorizza in una classe prescritta. Di seguito sono riportati alcuni scenari in cui è utile la classificazione delle immagini:

- Riconoscimento facciale
- Rilevamento emozioni
- Diagnosi medica
- Rilevamento di punti di riferimento

Questa esercitazione esegue il training di un modello di classificazione delle immagini personalizzato per eseguire un'ispezione visiva automatizzata dei deck Bridge per identificare le strutture danneggiate da crepe.

## <a name="mlnet-image-classification-api"></a>API di classificazione delle immagini ML.NET

ML.NET offre diversi modi per eseguire la classificazione delle immagini. Questa esercitazione applica l'apprendimento del trasferimento usando l'API di classificazione delle immagini. L'API di classificazione delle immagini USA [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una libreria di basso livello che fornisce associazioni C# per l'API C++ TensorFlow.

## <a name="what-is-transfer-learning"></a>Che cos'è l'apprendimento trasferito?

Transfer Learning applica le informazioni ottenute dalla risoluzione di un problema a un altro problema correlato.

Per il training di un modello di apprendimento avanzato da zero è necessario impostare diversi parametri, una grande quantità di dati di training con etichette e una grande quantità di risorse di calcolo (centinaia di ore GPU). L'uso di un modello pretrainato insieme a transfer Learning consente di abbreviare il processo di training.

## <a name="training-process"></a>Processo di training

L'API di classificazione delle immagini avvia il processo di training caricando un modello TensorFlow pre-trainato. Il processo di training è costituito da due passaggi:

1. Fase collo di bottiglia
2. Fase di training

![Passaggi di training](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a>Fase collo di bottiglia

Durante la fase di collo di bottiglia, viene caricato il set di immagini di training e i valori dei pixel vengono usati come input, o funzionalità, per i livelli bloccati del modello con training. I livelli bloccati includono tutti i livelli nella rete neurale fino al penultimo livello, noto in modo informale come livello del collo di bottiglia. A questi livelli viene fatto riferimento come bloccato perché non si verificherà alcun training su questi livelli e le operazioni sono pass-through. Si trova in questi livelli bloccati in cui vengono calcolati i modelli di livello inferiore che consentono di distinguere un modello tra le diverse classi. Maggiore è il numero di livelli, più elevato a livello di calcolo questo passaggio è. Fortunatamente, dal momento che si tratta di un calcolo monouso, i risultati possono essere memorizzati nella cache e usati nelle esecuzioni successive quando si sperimentano parametri diversi.

### <a name="training-phase"></a>Fase di training

Una volta calcolati i valori di output della fase di collo di bottiglia, essi vengono utilizzati come input per ripetere il training del livello finale del modello. Questo processo è iterativo e viene eseguito per il numero di volte specificato dai parametri del modello. Durante ogni esecuzione, la perdita e l'accuratezza vengono valutate. Quindi, vengono apportate le regolazioni appropriate per migliorare il modello con l'obiettivo di ridurre al minimo la perdita e massimizzare la precisione. Al termine del training, vengono restituiti due formati di modello. Una di esse è la `.pb` versione del modello e l'altra è la `.zip` versione serializzata ml.NET del modello. Quando si lavora in ambienti supportati da ML.NET, è consigliabile usare la `.zip` versione del modello. Tuttavia, negli ambienti in cui ML.NET non è supportato, è possibile usare la `.pb` versione.

## <a name="understand-the-pretrained-model"></a>Informazioni sul modello sottoposto a training

Il modello con training pretrain usato in questa esercitazione è la variante a 101 livelli del modello di rete residua (ResNet) v2. Il modello originale viene sottoposto a training per classificare le immagini in un centinaio di categorie. Il modello accetta come input un'immagine di dimensione 224 x 224 e restituisce le probabilità della classe per ogni classe su cui è stato eseguito il training. Parte di questo modello viene utilizzata per eseguire il training di un nuovo modello utilizzando immagini personalizzate per eseguire stime tra due classi.

## <a name="create-console-application"></a>Creare un'applicazione console

Ora che si dispone di una conoscenza generale del trasferimento dell'apprendimento e dell'API di classificazione delle immagini, è il momento di compilare l'applicazione.

1. Creare un' **applicazione console C# .NET Core** denominata "DeepLearning_ImageClassification_Binary".
1. Installare il pacchetto NuGet **Microsoft.ml** versione **1.4.0** :
    1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    1. Scegliere "nuget.org" come origine del pacchetto.
    1. Selezionare la scheda **Sfoglia**.
    1. Selezionare la casella di controllo **Includi versione preliminare** .
    1. Cercare **Microsoft.ml**.
    1. Selezionare il pulsante **Installa**.
    1. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.
    1. Ripetere questi passaggi per i pacchetti NuGet **Microsoft. ml. Vision** versione **1.4.0**, **SciSharp. TensorFlow. Redist** Version **1.15.0**e **Microsoft. ml. ImageAnalytics** Version **1.4.0** .

### <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

> [!NOTE]
> I set di impostazioni per questa esercitazione sono di Maguire, Marc; Dorafshan, Sattar; e Thomas, Robert J., "SDNET2018: un set di dati concreti per le immagini per le applicazioni di Machine Learning" (2018). Esplorare tutti i set di impostazioni. Carta 48. <https://digitalcommons.usu.edu/all_datasets/48>

SDNET2018 è un set di dati di immagini che contiene annotazioni per le strutture concrete incrinate e non incrinate (Bridge, muri e pavimentazione).

![Esempi di Deck Bridge per set di dati SDNET2018](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

I dati sono organizzati in tre sottodirectory:

- D contiene immagini del deck Bridge
- P contiene immagini pavimentali
- W contiene immagini a parete

Ognuna di queste sottodirectory contiene due sottodirectory con prefisso aggiuntivo:

- C è il prefisso usato per le superfici incrinate
- U è il prefisso usato per le superfici non incrinate

In questa esercitazione vengono usate solo le immagini del deck Bridge.

1. Scaricare il [set di dati](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) e decomprimere.
1. Creare una directory denominata "assets" nel progetto per salvare i file del set di dati.
1. Copiare le sottodirectory *CD* e *UD* dalla directory decomprimeta di recente alla directory *assets* .

### <a name="create-input-and-output-classes"></a>Creare classi di input e output

1. Aprire il file *Program.cs* e sostituire le `using` istruzioni esistenti all'inizio del file con il codice seguente:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. Sotto la `Program` classe in *Program.cs*creare una classe denominata `ImageData` . Questa classe viene utilizzata per rappresentare i dati caricati inizialmente.

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    `ImageData`contiene le proprietà seguenti:

    - `ImagePath`è il percorso completo in cui è archiviata l'immagine.
    - `Label`categoria a cui appartiene l'immagine. Si tratta del valore da stimare.

1. Creare classi per i dati di input e di output

    1. Sotto la `ImageData` classe definire lo schema dei dati di input in una nuova classe denominata `ModelInput` .

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        `ModelInput`contiene le proprietà seguenti:

        - `Image``byte[]`rappresentazione dell'immagine. Il modello prevede che i dati dell'immagine siano di questo tipo per il training.
        - `LabelAsKey`rappresentazione numerica dell'oggetto `Label` .
        - `ImagePath`è il percorso completo in cui è archiviata l'immagine.
        - `Label`categoria a cui appartiene l'immagine. Si tratta del valore da stimare.

        Solo `Image` e `LabelAsKey` vengono utilizzati per eseguire il training del modello ed eseguire stime. Le `ImagePath` `Label` proprietà e vengono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.

    1. Quindi, sotto la `ModelInput` classe, definire lo schema dei dati di output in una nuova classe denominata `ModelOutput` .

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        `ModelOutput`contiene le proprietà seguenti:

        - `ImagePath`è il percorso completo in cui è archiviata l'immagine.
        - `Label`è la categoria originale a cui appartiene l'immagine. Si tratta del valore da stimare.
        - `PredictedLabel`valore stimato dal modello.

        Analogamente a `ModelInput` , `PredictedLabel` è necessario solo per eseguire stime poiché contiene la stima effettuata dal modello. Le `ImagePath` `Label` proprietà e vengono conservate per praticità per accedere al nome del file di immagine originale e alla categoria.

### <a name="create-workspace-directory"></a>Crea directory dell'area di lavoro

Quando i dati di training e convalida non cambiano spesso, è consigliabile memorizzare nella cache i valori del collo di bottiglia calcolati per altre esecuzioni.

1. Nel progetto creare una nuova directory denominata *Workspace* per archiviare i valori del collo di bottiglia calcolati e la `.pb` versione del modello.

### <a name="define-paths-and-initialize-variables"></a>Definire i percorsi e inizializzare le variabili

1. All'interno del `Main` metodo, definire la posizione degli asset, i valori del collo di bottiglia calcolati e la `.pb` versione del modello.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. Inizializzare la `mlContext` variabile con una nuova istanza di [MLContext](xref:Microsoft.ML.MLContext).

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    La classe [MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni di ml.NET e l'inizializzazione di MLContext crea un nuovo ambiente ml.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Caricare i dati

### <a name="create-data-loading-utility-method"></a>Metodo di creazione dell'utilità di caricamento dati

Le immagini vengono archiviate in due sottodirectory. Prima di caricare i dati, è necessario formattarli in un elenco di `ImageData` oggetti. A tale scopo, creare il `LoadImagesFromDirectory` Metodo sotto il `Main` metodo.

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. All'interno `LoadImagesDirectory` di aggiungere il codice seguente per ottenere tutti i percorsi di file dalle sottodirectory:

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. Scorrere quindi ogni file usando un' `foreach` istruzione.

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. All'interno dell' `foreach` istruzione, verificare che le estensioni di file siano supportate. L'API di classificazione delle immagini supporta i formati JPEG e PNG.

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. Ottenere quindi l'etichetta per il file. Se il `useFolderNameAsLabel` parametro è impostato su `true` , viene usata come etichetta la directory padre in cui viene salvato il file. In caso contrario, prevede che l'etichetta sia un prefisso del nome file o il nome del file stesso.

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. Infine, creare una nuova istanza di `ModelInput` .

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a>Preparare i dati

1. Tornando al `Main` metodo, utilizzare il `LoadFromDirectory` Metodo Utility per ottenere l'elenco delle immagini utilizzate per il training.

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. Quindi, caricare le immagini in un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) usando il [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) metodo.

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. I dati vengono caricati nell'ordine in cui sono stati letti dalle directory. Per bilanciare i dati, eseguire il shuffle usando il [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) metodo.

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. Per i modelli di apprendimento automatico si prevede che l'input sia in formato numerico. Pertanto, è necessario eseguire alcune operazioni di pre-elaborazione sui dati prima di eseguire il training. Creare un oggetto [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) costituito da [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) `LoadRawImageBytes` trasformazioni e. La `MapValueToKey` trasformazione acquisisce il valore categorico nella `Label` colonna, lo converte in un `KeyType` valore numerico e lo archivia in una nuova colonna denominata `LabelAsKey` . `LoadImages`Accetta i valori dalla `ImagePath` colonna insieme al `imageFolder` parametro per caricare le immagini per il training.

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. Usare il [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) metodo per applicare i dati a `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) seguito dal [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) metodo, che restituisce un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) contenente i dati pre-elaborati.

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. Per eseguire il training di un modello, è importante avere un set di dati di training e un set di dati di convalida. Viene eseguito il training del modello nel training set. Il modo in cui esegue le stime sui dati non visualizzati viene misurato in base alle prestazioni rispetto al set di convalida. In base ai risultati di tali prestazioni, il modello apporta modifiche a quanto appreso nel tentativo di migliorare. Il set di convalida può derivare dalla suddivisione del set di dati originale o da un'altra origine che è già stata riservata a questo scopo. In questo caso, il set di dati pre-elaborato viene suddiviso in set di training, convalida e test.

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    L'esempio di codice precedente esegue due divisioni. In primo luogo, i dati pre-elaborati sono divisi e il 70% viene usato per il training, mentre il 30% rimanente viene usato per la convalida. Il set di convalida del 30% viene quindi suddiviso ulteriormente nei set di convalida e di test, in cui il 90% viene usato per la convalida e il 10% viene usato per il test.

    Un modo per considerare lo scopo di queste partizioni di dati consiste nell'esame. Quando si studia un esame, si esaminano le note, i libri o altre risorse per approfondire i concetti relativi all'esame. Questo è il set di training. Quindi, è possibile eseguire un esame fittizio per convalidare le proprie conoscenze. Questo è il punto in cui il set di convalida risulta utile. Si desidera controllare se si dispone di una conoscenza adeguata dei concetti prima di intraprendere l'esame effettivo. In base a questi risultati, si prende nota di quanto si è verificato un errore o non si è capito bene e si inseriscono le modifiche durante la revisione del vero esame. Infine, si prenderà in esame. Per questa operazione viene usato il set di test. Non hai mai visto le domande che sono in fase di esame e ora usi quanto appreso dalla formazione e dalla convalida per applicare le tue conoscenze all'attività.

1. Assegnare alle partizioni i rispettivi valori per i dati di training, convalida e test.

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a>Definire la pipeline di training

Il training del modello è costituito da un paio di passaggi. Per prima cosa, viene utilizzata l'API di classificazione delle immagini per eseguire il training del modello. Quindi, le etichette codificate nella `PredictedLabel` colonna vengono riconvertite nel valore categorico originale usando la `MapKeyToValue` trasformazione.

1. Creare una nuova variabile per archiviare un set di parametri obbligatori e facoltativi per un oggetto `ImageClassificationTrainer` .

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    Un `ImageClassificationTrainer` accetta diversi parametri facoltativi:

    - `FeatureColumnName`colonna utilizzata come input per il modello.
    - `LabelColumnName`colonna per il valore da stimare.
    - `ValidationSet`oggetto [`IDataView`](xref:Microsoft.ML.IDataView) che contiene i dati di convalida.
    - `Arch`definisce quale delle architetture del modello con training. Questa esercitazione usa la variante a 101 livelli del modello ResNetv2.
    - `MetricsCallback`associa una funzione per tenere traccia dello stato di avanzamento durante il training.
    - `TestOnTrainSet`indica al modello di misurare le prestazioni rispetto al set di training quando non è presente alcun set di convalida.
    - `ReuseTrainSetBottleneckCachedValues`indica al modello se utilizzare i valori memorizzati nella cache della fase di collo di bottiglia nelle esecuzioni successive. La fase di collo di bottiglia è un calcolo pass-through monouso che richiede un utilizzo intensivo di calcolo alla prima esecuzione. Se i dati di training non cambiano e si vuole provare a usare un numero diverso di epoche o dimensioni del batch, l'uso dei valori memorizzati nella cache riduce significativamente la quantità di tempo necessaria per eseguire il training di un modello.
    - `ReuseValidationSetBottleneckCachedValues`è simile `ReuseTrainSetBottleneckCachedValues` solo a quello che in questo caso è per il set di dati di convalida.
    - `WorkspacePath`definisce la directory in cui archiviare i valori del collo di bottiglia calcolati e la `.pb` versione del modello.

1. Definire la [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) pipeline di training costituita sia da che da `mapLabelEstimator` `ImageClassificationTrainer` .

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. Utilizzare il [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) metodo per eseguire il training del modello.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a>Usare il modello

A questo punto, dopo aver eseguito il training del modello, è possibile usarlo per classificare le immagini.

Sotto il `Main` metodo, creare un nuovo metodo di utilità denominato `OutputPrediction` per visualizzare le informazioni di stima nella console di.

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a>Classificare una singola immagine

1. Aggiungere un nuovo metodo denominato `ClassifySingleImage` sotto il `Main` metodo per creare e restituire una singola stima di immagine.

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Creare un oggetto [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) all'interno del `ClassifySingleImage` metodo. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)È un'API utile che consente di passare ed eseguire una stima su una singola istanza di dati.

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. Per accedere a una singola `ModelInput` istanza, convertire `data` [`IDataView`](xref:Microsoft.ML.IDataView) in un oggetto [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) metodo e quindi ottenere la prima osservazione.

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. Usare il [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) metodo per classificare l'immagine.

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. Restituire la stima alla console con il `OutputPrediction` metodo.

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. All'interno del `Main` metodo chiamare `ClassifySingleImage` usando il set di immagini di test.

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a>Classificare più immagini

1. Aggiungere un nuovo metodo denominato `ClassifyImages` sotto il `ClassifySingleImage` metodo per creare e restituire più stime di immagine.

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Creare un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) contenente le stime tramite il [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) metodo. Aggiungere il codice seguente all'interno del metodo `ClassifyImages`.

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. Per eseguire l'iterazione delle stime, convertire `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) in un oggetto [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) usando il [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) metodo e quindi ottenere le prime 10 osservazioni.

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. Eseguire l'iterazione e restituire le etichette originali e stimate per le stime.

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. Infine, all'interno del `Main` metodo, chiamare `ClassifyImages` utilizzando il set di immagini di test.

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a>Eseguire l'applicazione

Eseguire l'app console. L'output dovrebbe essere simile a quello riportato di seguito. È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito. Per brevità, l'output è stato condensato.

**Fase collo di bottiglia**

Non viene stampato alcun valore per il nome dell'immagine perché le immagini vengono caricate come un oggetto, `byte[]` di conseguenza non è presente alcun nome di immagine da visualizzare.

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

**Fase di training**

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

**Classifica output immagini**

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

Quando si verifica l'immagine *7001 -220. jpg* , è possibile notare che in realtà non è incrinato.

![Immagine del set di dati SDNET2018 utilizzata per la stima](./media/image-classification-api-transfer-learning/predictedimage.jpg)

Congratulazioni! A questo punto è stato creato un modello di apprendimento avanzato per la classificazione delle immagini.

### <a name="improve-the-model"></a>Migliorare il modello

Se non si è soddisfatti dei risultati del modello, è possibile provare a migliorarne le prestazioni provando alcuni degli approcci seguenti:

- **Altri dati**: maggiore è il numero di esempi apportati da un modello, migliori saranno le prestazioni. Scaricare il [set di dati SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo e usarlo per il training.
- **Migliorare i dati**: una tecnica comune per aggiungere varietà ai dati consiste nell'aumentare i dati mediante l'acquisizione di un'immagine e l'applicazione di trasformazioni diverse (ruotare, capovolgere, spostare o ritagliare). In questo modo vengono aggiunti esempi più diversi per il modello da cui apprendere.
- Eseguire il **training per un periodo di tempo più lungo**: maggiore sarà il training del modello. L'aumento del numero di epoche può migliorare le prestazioni del modello.
- **Esperimento con i parametri ipertestuali**: oltre ai parametri usati in questa esercitazione, è possibile ottimizzare altri parametri per migliorare le prestazioni. Modifica della velocità di apprendimento, che determina la grandezza degli aggiornamenti apportati al modello dopo che ogni Epoch può migliorare le prestazioni.
- **Usare un'architettura del modello diversa**: a seconda dell'aspetto dei dati, il modello che può apprendere meglio le sue funzionalità può essere diverso. Se non si è soddisfatti delle prestazioni del modello, provare a modificare l'architettura.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Visual Studio e Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come creare un modello di apprendimento avanzato personalizzato usando Transfer Learning, un modello di classificazione di immagini con training TensorFlow e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non incrinate.

Passare all'esercitazione successiva per altre informazioni.

> [!div class="nextstepaction"]
> [Rilevamento oggetti](object-detection-onnx.md)
