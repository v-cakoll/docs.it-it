---
title: "Esercitazione: Ispezione visiva automatizzata tramite l'apprendimento dei trasferimentiTutorial: Automated visual inspection using transfer learning"
description: Questa esercitazione illustra come usare l'apprendimento tramite trasferimento per eseguire il training di un modello di deep learning TensorFlow in ML.NET usando l'API di rilevamento delle immagini per classificare le immagini di superfici in calcestruzzo come incrinate o non incrinate.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2dfa3cdab9de47b55f7a3f73f0d6e9460390700c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76920092"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a>Esercitazione: Ispezione visiva automatizzata tramite l'apprendimento del trasferimento con l'API di classificazione delle immagini ML.NETTutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API

Informazioni su come eseguire il training di un modello di deep learning personalizzato usando l'apprendimento tramite trasferimento, un modello TensorFlow preaddestrato e l'API ML.NET image Classification per classificare le immagini di superfici concrete come incrinate o non superate.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Informazioni sul problema
> - Informazioni su ML.NETAPI di classificazione delle immagini
> - Comprendere il modello preformato
> - Usare l'apprendimento di trasferimento per eseguire il training di un modello di classificazione delle immagini TensorFlow personalizzatoUse transfer learning to train a custom TensorFlow image classification model
> - Classificare le immagini con il modello personalizzato

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro ".NET Core cross-platform development" installato.

## <a name="image-classification-transfer-learning-sample-overview"></a>Panoramica dell'esempio di apprendimento sul trasferimento della classificazione delle immagini

Questo esempio è un'applicazione console .NET Core di C.NET che classifica le immagini usando un modello TensorFlow di deep learning con training preliminare. Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) in GitHub.

## <a name="understand-the-problem"></a>Informazioni sul problema

La classificazione delle immagini è un problema di visione artificiale. La classificazione delle immagini accetta un'immagine come input e la classifica in una classe prescritta. Alcuni scenari in cui la classificazione delle immagini è utile includono:Some scenarios where image classification is useful include:

- Riconoscimento facciale
- Rilevamento emozioni
- Diagnosi medica
- Rilevamento dei punti di riferimento

Questa esercitazione esegue il training di un modello di classificazione delle immagini personalizzato per eseguire l'ispezione visiva automatica dei ponti per identificare le strutture danneggiate dalle fessure.

## <a name="mlnet-image-classification-api"></a>ML.NET Image Classification API

ML.NET fornisce vari modi per eseguire la classificazione delle immagini. Questa esercitazione applica l'apprendimento di trasferimento usando l'API di classificazione delle immagini. L'API di classificazione delle immagini utilizza [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una libreria di basso livello che fornisce le associazioni di C, per l'API TensorFlow.

## <a name="what-is-transfer-learning"></a>Che cos'è l'apprendimento trasferito?

L'apprendimento del trasferimento applica le conoscenze acquisite risolvendo un problema a un altro problema correlato.

Il training di un modello di deep learning da zero richiede l'impostazione di diversi parametri, una grande quantità di dati di training con etichetta e una grande quantità di risorse di calcolo (centinaia di ore GPU). L'utilizzo di un modello con training preliminare e l'apprendimento di trasferimento consente di eseguire il collegamento del processo di training.

## <a name="training-process"></a>Processo di formazione

L'API di classificazione delle immagini avvia il processo di training caricando un modello TensorFlow con training preliminare. Il processo di formazione si articola in due fasi:

1. Fase collo di bottiglia
2. Fase di formazione

![Passaggi di formazione](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a>Fase collo di bottiglia

Durante la fase di collo di bottiglia, viene caricato il set di immagini di training e i valori dei pixel vengono utilizzati come input, o funzionalità, per i livelli congelati del modello con training preliminare. I livelli congelati includono tutti i livelli della rete neurale fino al penultimo strato, informalmente noto come strato di collo di bottiglia. Questi layer vengono definiti congelati perché non verrà eseguito alcun addestramento su questi layer e le operazioni sono pass-through. Si trova a questi strati congelati dove vengono calcolati i modelli di livello inferiore che aiutano un modello a distinguere tra le diverse classi. Maggiore è il numero di strati, più intenso è il calcolo di questo passaggio. Fortunatamente, poiché si tratta di un calcolo una tantera, i risultati possono essere memorizzati nella cache e utilizzati nelle esecuzioni successive durante la sperimentazione con parametri diversi.

### <a name="training-phase"></a>Fase di formazione

Una volta calcolati, i valori di output della fase di collo di bottiglia vengono utilizzati come input per riqualificare il livello finale del modello. Questo processo è iterativo e viene eseguito per il numero di volte specificato dai parametri del modello. Durante ogni corsa, la perdita e la precisione vengono valutate. Quindi, vengono apportate le regolazioni appropriate per migliorare il modello con l'obiettivo di ridurre al minimo la perdita e massimizzare la precisione. Al termine del training, vengono restituiti due formati di modello. Uno di essi `.pb` è la versione del `.zip` modello e l'altro è la versione serializzata ML.NET del modello. Quando si lavora in ambienti supportati da `.zip` ML.NET, si consiglia di utilizzare la versione del modello. Tuttavia, in ambienti in cui ML.NET non è `.pb` supportato, è possibile utilizzare la versione.

## <a name="understand-the-pretrained-model"></a>Comprendere il modello preformato

Il modello preformato utilizzato in questa esercitazione è la variante a 101 livelli del modello Residual Network (ResNet) v2. Il modello originale viene addestrato per classificare le immagini in mille categorie. Il modello accetta come input un'immagine di dimensioni 224 x 224 e restituisce le probabilità di classe per ciascuna delle classi su cui è stato eseguito il training. Parte di questo modello viene usato per eseguire il training di un nuovo modello usando immagini personalizzate per eseguire stime tra due classi.

## <a name="create-console-application"></a>Creare un'applicazione console

Ora che si ha una conoscenza generale dell'apprendimento dei trasferimenti e dell'API di classificazione delle immagini, è il momento di compilare l'applicazione.

1. Creare **un'applicazione console di Core di C .NET** denominata "DeepLearning_ImageClassification_Binary".
1. Installare il pacchetto NuGet **di Microsoft.ML** versione **1.4.0:Install** the Microsoft.ML version 1.4.0 NuGet Package:
    1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    1. Scegliere "nuget.org" come origine del pacchetto.
    1. Selezionare la scheda **Sfoglia**.
    1. Selezionare la casella di **controllo Includi versione non definitiva.**
    1. Cerca **Microsoft.ML**.
    1. Selezionare il pulsante **Installa**.
    1. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.
    1. Ripetere questi passaggi per i pacchetti **Microsoft.ML.Vision** **versione 1.4.0**, **SciSharp.TensorFlow.Redist** versione **1.15.0**e **Microsoft.ML.ImageAnalytics** versione **1.4.0** NuGet.

### <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

> [!NOTE]
> I set di dati per questa esercitazione provengono da Maguire, Marc. Dorafshan, Sattar; e Thomas, Robert J., "SDNET2018: un set di dati di immagini crepa concreta per applicazioni di apprendimento automatico" (2018). Sfogliare tutti i set di dati. Fascicolo 48. https://digitalcommons.usu.edu/all_datasets/48

SDNET2018 è un set di dati di immagini che contiene annotazioni per strutture in calcestruzzo incrinate e non (ponti, muri e pavimentazione).

![Esempi di bridge bridge di set di dati SDNET2018SDNET2018 dataset bridge deck samples](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

I dati sono organizzati in tre sottodirectory:

- D contiene immagini del ponte
- P contiene immagini di pavimentazione
- W contiene immagini a muro

Ognuna di queste sottodirectory contiene due sottodirectory con prefisso aggiuntive:

- C è il prefisso utilizzato per le superfici incrinate
- U è il prefisso utilizzato per le superfici non screpolate

In questa esercitazione vengono utilizzate solo le immagini del bridge.

1. Scaricare il [set di dati](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) e decomprimere.
1. Creare una directory denominata "assets" nel progetto per salvare i file del dataset.
1. Copiare le sottodirectory *CD* e *UD* dalla directory decompressa di recente nella directory *assets.*

### <a name="create-input-and-output-classes"></a>Creare classi di input e outputCreate input and output classes

1. Aprire il file *Program.cs* `using` e sostituire le istruzioni esistenti all'inizio del file con quanto segue:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. Sotto `Program` la classe *di Program.cs* `ImageData`creare una classe denominata . Questa classe viene utilizzata per rappresentare i dati caricati inizialmente.

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    `ImageData`contiene le seguenti proprietà:

    - `ImagePath`è il percorso completo in cui è memorizzata l'immagine.
    - `Label`è la categoria a cui appartiene l'immagine. Questo è il valore da stimare.

1. Creare classi per i dati di input e outputCreate classes for your input and output data

    1. Sotto `ImageData` la classe, definire lo schema dei dati `ModelInput`di input in una nuova classe denominata .

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        `ModelInput`contiene le seguenti proprietà:

        - `Image`è `byte[]` la rappresentazione dell'immagine. Il modello prevede che i dati immagine siano di questo tipo per il training.
        - `LabelAsKey`è la rappresentazione `Label`numerica del file .
        - `ImagePath`è il percorso completo in cui è memorizzata l'immagine.
        - `Label`è la categoria a cui appartiene l'immagine. Questo è il valore da stimare.

        Solo `Image` `LabelAsKey` e vengono utilizzati per eseguire il training del modello ed eseguire stime. Le `ImagePath` `Label` proprietà e vengono mantenute per comodità di accedere al nome e alla categoria del file di immagine originale.

    1. Quindi, sotto `ModelInput` la classe , definire lo schema dei `ModelOutput`dati di output in una nuova classe denominata .

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        `ModelOutput`contiene le seguenti proprietà:

        - `ImagePath`è il percorso completo in cui è memorizzata l'immagine.
        - `Label`è la categoria originale a cui appartiene l'immagine. Questo è il valore da stimare.
        - `PredictedLabel`è il valore previsto dal modello.

        Simile `ModelInput`a , `PredictedLabel` solo l'oggetto è necessario per eseguire stime poiché contiene la stima effettuata dal modello. Le `ImagePath` `Label` proprietà e vengono mantenute per comodità di accedere al nome e alla categoria del file di immagine originale.

### <a name="create-workspace-directory"></a>Creare una directory dell'area di lavoro

Quando i dati di training e convalida non cambiano spesso, è consigliabile memorizzare nella cache i valori di collo di bottiglia calcolati per ulteriori esecuzioni.

1. Nel progetto creare una nuova directory denominata *workspace* per `.pb` archiviare i valori dei colli di bottiglia calcolati e la versione del modello.

### <a name="define-paths-and-initialize-variables"></a>Definire percorsi e inizializzare le variabiliDefine paths and initialize variables

1. All'interno del `Main` metodo, definire la posizione degli `.pb` asset, i valori di collo di bottiglia calcolati e la versione del modello.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. Inizializzare `mlContext` la variabile con una nuova istanza di [MLContext.](xref:Microsoft.ML.MLContext)

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    La classe [MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di mlContext crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Caricare i dati

### <a name="create-data-loading-utility-method"></a>Creare il metodo di utilità di caricamento dei datiCreate data loading utility method

Le immagini sono memorizzate in due sottodirectory. Prima di caricare i dati, è necessario `ImageData` formattarli in un elenco di oggetti. A tale scopo, `LoadImagesFromDirectory` creare `Main` il metodo sotto il metodo .

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. All'interno del `LoadImagesDirectory` codice aggiungere il codice seguente per ottenere tutti i percorsi dei file dalle sottodirectory:

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. Quindi, scorrere ognuno dei `foreach` file utilizzando un'istruzione.

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. All'interno dell'istruzione, `foreach` verificare che le estensioni dei file siano supportate. L'API di classificazione delle immagini supporta i formati JPEG e PNG.

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. Quindi, ottenere l'etichetta per il file. Se `useFolderNameAsLabel` il parametro `true`è impostato su , come etichetta viene utilizzata la directory padre in cui viene salvato il file. In caso contrario, si prevede che l'etichetta sia un prefisso del nome del file o del nome del file stesso.

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. Infine, creare una `ModelInput`nuova istanza di .

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a>Preparare i dati

1. Nel `Main` metodo, utilizzare `LoadFromDirectory` il metodo di utilità per ottenere l'elenco delle immagini utilizzate per il training.

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. Quindi, caricare le [`IDataView`](xref:Microsoft.ML.IDataView) immagini [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) in un utilizzando il metodo .

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. I dati vengono caricati nell'ordine in cui sono stati letti dalle directory. Per bilanciare i dati, mischiali usando il [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) metodo .

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. I modelli di apprendimento automatico prevedono che l'input sia in formato numerico. Pertanto, è necessario eseguire alcune pre-elaborazione sui dati prima del training. Creare [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) un composto [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) di `LoadRawImageBytes` trasformazioni e . La `MapValueToKey` trasformazione accetta il valore `Label` categorico nella colonna, `KeyType` lo converte in un `LabelAsKey`valore numerico e lo archivia in una nuova colonna denominata . Accetta `LoadImages` i valori `ImagePath` dalla colonna `imageFolder` insieme al parametro per caricare le immagini per il training.

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. Utilizzare [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) il metodo per applicare `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) i [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) dati a quelli [`IDataView`](xref:Microsoft.ML.IDataView) seguiti dal metodo , che restituisce un contenente i dati pre-elaborati.

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. Per eseguire il training di un modello, è importante disporre di un set di dati di training e di un set di dati di convalida. Il modello viene eseguito il training sul set di training. Il livello di ottimizzazione delle stime sui dati non visti viene misurato in base alle prestazioni rispetto al set di convalida. In base ai risultati di tali prestazioni, il modello apporta modifiche a ciò che ha appreso nel tentativo di migliorare. Il set di convalida può derivare dalla suddivisione del set di dati originale o da un'altra origine che è già stata messa da parte per questo scopo. In questo caso, il set di dati pre-elaborato viene suddiviso in set di training, convalida e test.

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    L'esempio di codice precedente esegue due divisioni. In primo luogo, i dati pre-elaborati vengono suddivisi e il 70% viene utilizzato per il training mentre il restante 30% viene utilizzato per la convalida. Quindi, il set di convalida 30% viene ulteriormente suddiviso in set di convalida e test in cui 90% viene utilizzato per la convalida e 10% viene utilizzato per il test.

    Un modo per pensare allo scopo di queste partizioni di dati è sostenere un esame. Quando studi per un esame, rivedi le note, i libri o altre risorse per comprendere i concetti relativi all'esame. Questo è ciò che il treno è per. Quindi, si potrebbe prendere un esame fittizio per convalidare le conoscenze. Questo è dove il set di convalida è utile. Si desidera verificare se si dispone di una buona comprensione dei concetti prima di sostenere l'esame effettivo. Sulla base di questi risultati, prendi nota di ciò che hai sbagliato o non hai capito bene e incorpora le modifiche mentre rivedi l'esame reale. Infine, fai l'esame. Questo è ciò per cui viene utilizzato il set di test. Non hai mai visto le domande che sono all'esame e ora usa ciò che hai imparato dalla formazione e dalla convalida per applicare le tue conoscenze al compito a portata di mano.

1. Assegnare alle partizioni i rispettivi valori per i dati di training, convalida e test.

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a>Definire la pipeline di trainingDefine the training pipeline

L'addestramento del modello consiste in un paio di passaggi. In primo luogo, l'API di classificazione delle immagini viene usata per eseguire il training del modello. Quindi, le etichette `PredictedLabel` codificate nella colonna vengono riconvertite nel `MapKeyToValue` valore categorico originale utilizzando la trasformazione.

1. Creare una nuova variabile per archiviare un `ImageClassificationTrainer`set di parametri obbligatori e facoltativi per un oggetto .

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    Un `ImageClassificationTrainer` accetta diversi parametri facoltativi:

    - `FeatureColumnName`è la colonna utilizzata come input per il modello.
    - `LabelColumnName`è la colonna per il valore da stimare.
    - `ValidationSet`è [`IDataView`](xref:Microsoft.ML.IDataView) l'oggetto contenente i dati di convalida.
    - `Arch`definisce quale delle architetture di modelli pre-addestrati utilizzare. Questa esercitazione usa la variante a 101 livelli del modello ResNetv2.This tutorial uses the 101-layer variant of the ResNetv2 model.
    - `MetricsCallback`associa una funzione per tenere traccia dello stato di avanzamento durante l'allenamento.
    - `TestOnTrainSet`indica al modello di misurare le prestazioni rispetto al set di training quando non è presente alcun set di convalida.
    - `ReuseTrainSetBottleneckCachedValues`indica al modello se utilizzare i valori memorizzati nella cache dalla fase di collo di bottiglia nelle esecuzioni successive. La fase di collo di bottiglia è un calcolo pass-through una tantera che richiede un utilizzo intensivo del calcolo alla prima esecuzione. Se i dati di training non cambiano e si vuole sperimentare usando un numero diverso di epoche o dimensioni del batch, l'uso dei valori memorizzati nella cache riduce in modo significativo la quantità di tempo necessaria per eseguire il training di un modello.
    - `ReuseValidationSetBottleneckCachedValues`è simile `ReuseTrainSetBottleneckCachedValues` solo a quello che in questo caso è per il set di dati di convalida.
    - `WorkspacePath`definisce la directory in cui archiviare `.pb` i valori dei colli di bottiglia calcolati e la versione del modello.

1. Definire [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) la pipeline di training `mapLabelEstimator` costituita sia da e . `ImageClassificationTrainer`

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. Usare [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) il metodo per eseguire il training del modello.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a>Usare il modello

Dopo aver eseguito il training del modello, è necessario usarlo per classificare le immagini.

Sotto `Main` il metodo, creare un `OutputPrediction` nuovo metodo di utilità chiamato per visualizzare le informazioni di stima nella console.

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a>Classificare una singola immagine

1. Aggiungere un nuovo `ClassifySingleImage` metodo `Main` chiamato sotto il metodo per eseguire e restituire una singola stima dell'immagine.

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Creare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) un `ClassifySingleImage` all'interno del metodo. Si [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) tratta di un'API di convenienza, che consente di passare e quindi eseguire una stima su una singola istanza di dati.

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. Per accedere `ModelInput` a una `data` [`IDataView`](xref:Microsoft.ML.IDataView) singola [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) istanza, [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) convertire l'oggetto in un utilizzando il metodo e quindi ottenere la prima osservazione.

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. Utilizzare [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) il metodo per classificare l'immagine.

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. Eseguire l'output della `OutputPrediction` stima nella console con il metodo .

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. All'interno `Main` del `ClassifySingleImage` metodo, chiamare utilizzando il set di test di immagini.

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a>Classificare più immagini

1. Aggiungere un nuovo `ClassifyImages` metodo `ClassifySingleImage` chiamato sotto il metodo per eseguire ed eseguire più stime di immagine.

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Creare [`IDataView`](xref:Microsoft.ML.IDataView) un contenente le stime utilizzando il [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) metodo . Aggiungere il codice seguente all'interno del metodo `ClassifyImages`.

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. Per scorrere le stime, convertire `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) il [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) in [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) un utilizzando il metodo e quindi ottenere le prime 10 osservazioni.

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. Iterare ed eseguire l'output delle etichette originali e stimate per le stime.

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. Infine, all'interno `Main` `ClassifyImages` del metodo, chiamare utilizzando il set di test di immagini.

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a>Eseguire l'applicazione

Eseguire l'app console. L'output dovrebbe essere simile a quello riportato di seguito. È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito. Per brevità, l'output è stato condensato.

**Fase collo di bottiglia**

Non viene stampato alcun valore per il nome `byte[]` dell'immagine perché le immagini vengono caricate in modo tale da non visualizzare alcun nome di immagine.

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

**Fase di formazione**

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

**Classificare l'output delle immagini**

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

Dopo l'ispezione dell'immagine *7001-220.jpg,* si può vedere che in realtà non è incrinato.

![Immagine del set di dati SDNET2018 usata per la stimaSDNET2018 dataset image used for prediction](./media/image-classification-api-transfer-learning/predictedimage.jpg)

Congratulazioni! Ora hai creato con successo un modello di deep learning per classificare le immagini.

### <a name="improve-the-model"></a>Migliorare il modello

Se non si è soddisfatti dei risultati del modello, è possibile provare a migliorarne le prestazioni provando alcuni degli approcci seguenti:

- **Più dati**: più esempi apprende un modello, meglio si comporta. Scaricare il [set di dati SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo e usarlo per il training.
- **Aumentare i dati**: Una tecnica comune per aggiungere varietà ai dati è quello di aumentare i dati prendendo un'immagine e applicando diverse trasformazioni (ruotare, capovolgere, spostare, ritagliare). Questo aggiunge esempi più diversi per il modello da cui imparare.
- **Allenati per un tempo più lungo**: Più a lungo ti alleni, più il modello sarà sintonizzato. L'aumento del numero di epoche può migliorare le prestazioni del modello.
- **Sperimentare con gli iperparametri**: Oltre ai parametri utilizzati in questa esercitazione, altri parametri possono essere sintonizzati per migliorare potenzialmente le prestazioni. La modifica della velocità di apprendimento, che determina l'entità degli aggiornamenti apportati al modello dopo ogni epoca può migliorare le prestazioni.
- **Usare un'architettura**del modello diversa: a seconda dell'aspetto dei dati, il modello che meglio è in grado di apprendere le funzionalità potrebbe essere diverso. Se non si è soddisfatti delle prestazioni del modello, provare a modificare l'architettura.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stato illustrato come creare un modello di deep learning personalizzato usando l'apprendimento tramite trasferimento, un modello TensorFlow di classificazione delle immagini con training preliminare e l'API di classificazione delle immagini ML.NET per classificare le immagini di superfici concrete come incrinate o non crittografate.

Passare all'esercitazione successiva per altre informazioni.

> [!div class="nextstepaction"]
> [Rilevamento di oggetti](object-detection-onnx.md)
