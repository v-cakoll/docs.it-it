---
title: 'Esercitazione: rilevare oggetti usando un modello di apprendimento avanzato ONNX'
description: Questa esercitazione illustra come usare un modello di Deep Learning ONNX già sottoposto a training in ML.NET per rilevare gli oggetti nelle immagini.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b9fa8ef74dd4f8070884f6cee4eb2af3082af5e5
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394899"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a>Esercitazione: rilevare oggetti con ONNX in ML.NET

Informazioni su come usare un modello ONNX già sottoposto a training in ML.NET per rilevare gli oggetti nelle immagini.

Il training di un modello di rilevamento degli oggetti da zero richiede l'impostazione di milioni di parametri, numerosi dati di training con etichetta e una notevole quantità di risorse di calcolo (centinaia di ore di GPU). L'uso di un modello già sottoposto a training consente di abbreviare il processo di training.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Informazioni sul problema
> - Acquisire familiarità con ONNX e comprenderne il funzionamento con ML.NET
> - Acquisire familiarità con il modello
> - Riutilizzare il modello già sottoposto a training
> - Rilevare oggetti con un modello caricato

## <a name="pre-requisites"></a>Prerequisiti

- [Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.
- [Pacchetto NuGet Microsoft.ML](https://www.nuget.org/packages/Microsoft.ML/)
- [Pacchetto NuGet Microsoft.ML.ImageAnalytics](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [Pacchetto NuGet Microsoft.ML.OnnxTransformer](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [Modello Tiny YOLOv2 già sottoposto a training](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny-yolov2)
- [Netron](https://github.com/lutzroeder/netron) (facoltativo)

## <a name="onnx-object-detection-sample-overview"></a>Panoramica dell'esempio di rilevamento degli oggetti ONNX

Questo esempio crea un'applicazione console .NET Core che rileva gli oggetti all'interno di un'immagine usando un modello ONNX di Deep Learning già sottoposto a training. Il codice per questo esempio è disponibile nel [repository dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) in GitHub.

## <a name="what-is-object-detection"></a>Che cos'è il rilevamento degli oggetti?

Il rilevamento degli oggetti è una questione correlata alla visione artificiale. Sebbene sia un concetto strettamente correlato alla classificazione delle immagini, il rilevamento degli oggetti esegue l'operazione di classificazione delle immagini su scala più granulare. Il rilevamento degli oggetti individua _e_ classifica le entità all'interno delle immagini. Usare il rilevamento degli oggetti quando le immagini contengono più oggetti di tipi diversi.

![Schermate che mostrano la classificazione delle immagini rispetto alla classificazione degli oggetti.](./media/object-detection-onnx/img-classification-obj-detection.png)

Ecco alcuni casi d'uso per il rilevamento degli oggetti:

- Auto senza guidatore
- Robotica
- Rilevamento viso
- Sicurezza nell'ambiente di lavoro
- Conteggio di oggetti
- Riconoscimento di attività

## <a name="select-a-deep-learning-model"></a>Selezionare un modello di Deep Learning

Il Deep Learning è un subset del Machine Learning. Per eseguire il training di modelli di Deep Learning, sono necessarie grandi quantità di dati. I modelli nei dati sono rappresentati da una serie di livelli. Le relazioni nei dati sono codificate come connessioni tra i livelli contenenti pesi. Maggiore è il peso, più forte è la relazione. Collettivamente, questa serie di livelli e connessioni è nota come rete neurale artificiale. Maggiore è il numero di livelli in una rete, più "profonda" è la rete, che diventa una rete neurale profonda.

Ci sono diversi tipi di reti neurali, tra cui i più comuni sono percettrone multistrato (MLP, Multi-Layered Perceptron), rete neurale convoluzionale (CNN, Convolutional Neural Network) e rete neurale ricorrente (RNN, Recurrent Neural Network). Il tipo più semplice è MLP, che esegue il mapping di un set di input a un set di output. Questa rete neurale è efficace quando i dati non hanno una componente spaziale o temporale. La rete CNN usa i livelli convoluzionali per elaborare le informazioni spaziali contenute nei dati. Un buon caso d'uso per le reti CNN è l'elaborazione di immagini per rilevare la presenza di una caratteristica in un'area di un'immagine (ad esempio, è presente un naso al centro di un'immagine?). Infine, le reti RNN consentono di usare come input la persistenza dello stato o della memoria. Le reti RNN vengono usate per l'analisi delle serie temporali, in cui l'ordinamento sequenziale e il contesto degli eventi sono importanti.

### <a name="understand-the-model"></a>Acquisire familiarità con il modello

Il rilevamento di oggetti è un'attività di elaborazione di immagini. Per questo motivo, i modelli di Deep Learning sottoposti a training per risolvere questo problema sono prevalentemente di tipo CNN. Il modello usato in questa esercitazione è il piccolo modello YOLOv2, una versione più compatta del modello YOLOv2 descritto nel documento ["YOLO9000: migliore, più veloce, più forte" di Redmon e Fadhari](https://arxiv.org/pdf/1612.08242.pdf). Il training di Tiny YOLOv2 viene eseguito sul set di dati Pascal VOC ed è costituito da 15 livelli in grado di eseguire stime per 20 diverse classi di oggetti. Poiché il modello Tiny YOLOv2 è una versione ridotta del modello YOLOv2 originale, rappresenta un compromesso tra velocità e accuratezza. I diversi livelli che compongono il modello possono essere visualizzati usando strumenti come Netron. L'esame del modello restituirebbe un mapping delle connessioni tra tutti i livelli che compongono la rete neurale, in cui ogni livello contiene il nome del livello insieme alle dimensioni del rispettivo input/output. Le strutture di dati usate per descrivere gli input e gli output del modello sono note come tensori. I tensori possono essere considerati contenitori che archiviano i dati in N dimensioni. Nel caso di Tiny YOLOv2, il nome del livello di input è `image` e prevede un tensore con dimensioni `3 x 416 x 416`. Il nome del livello di output è `grid` e genera un tensore di output con dimensioni `125 x 13 x 13`.

![Livello di input suddiviso in livelli nascosti, quindi livello di output](./media/object-detection-onnx/netron-model-map-layers.png)

Il modello YOLO accetta un'immagine `3(RGB) x 416px x 416px`. Il modello accetta questo input e lo passa attraverso i diversi livelli per produrre un output. L'output divide l'immagine di input in una griglia `13 x 13`, con ogni cella della griglia costituita da `125` valori.

### <a name="what-is-an-onnx-model"></a>Che cos'è un modello ONNX?

Open Neural Network Exchange (ONNX) è un formato open source per i modelli di intelligenza artificiale. ONNX supporta l'interoperabilità tra framework. Ciò significa che è possibile eseguire il training di un modello in uno dei numerosi framework di apprendimento automatico diffusi, ad esempio PyTorch, eseguire la conversione in formato ONNX e utilizzare il modello ONNX in un framework diverso, come ML.NET. Per altre informazioni, vedere il [sito Web ONNX](https://onnx.ai/).

![Diagramma dei formati supportati da ONNX in uso.](./media/object-detection-onnx/onnx-supported-formats.png)

Il modello Tiny YOLOv2 già sottoposto a training è archiviato in formato ONNX, una rappresentazione serializzata dei livelli e dei modelli appresi di tali livelli. In ML.NET, l'interoperabilità con ONNX si raggiunge con i [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) pacchetti NuGet e. Il [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) pacchetto contiene una serie di trasformazioni che accettano un'immagine e la codificano in valori numerici che possono essere usati come input in una pipeline di stima o di training. Il [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) pacchetto si avvale del runtime ONNX per caricare un modello ONNX e utilizzarlo per eseguire stime basate sull'input fornito.

![Flusso di dati del file ONNX nel runtime di ONNX.](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a>Configurare il progetto .NET Core

Ora che sono state apprese le nozioni generali su ONNX e sul funzionamento di Tiny YOLOv2, è possibile creare l'applicazione.

### <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione console .NET Core** denominata "ObjectDetection".

1. Installare il **pacchetto NuGet Microsoft.ML**:

    - In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    - Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**.
    - Selezionare il pulsante **Installa**.
    - Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.
    - Ripetere questi passaggi per **Microsoft.ML.ImageAnalytics** e **Microsoft.ML.OnnxTransformer**.

### <a name="prepare-your-data-and-pre-trained-model"></a>Preparare i dati e il modello già sottoposto a training

1. Scaricare il [file ZIP della directory assets del progetto](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) e decomprimerlo.

1. Copiare la directory `assets` nella directory del progetto *ObjectDetection*. Questa directory e le relative sottodirectory contengono i file di immagine (ad eccezione del modello Tiny YOLOv2, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.

1. Scaricare il [modello Tiny YOLOv2](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) da [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) e decomprimerlo.

    Aprire il prompt dei comandi e immettere il comando seguente:

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. Copiare il file `model.onnx` estratto dalla directory appena decompressa nella directory `assets\Model` del progetto*ObjectDetection* e rinominarlo in `TinyYolo2_model.onnx`. Questa directory contiene il modello necessario per questa esercitazione.

1. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**. In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aprire il file *Program.cs* e aggiungere le istruzioni `using` aggiuntive seguenti all'inizio del file:

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

Definire quindi i percorsi dei diversi asset.

1. Prima di tutto, aggiungere il metodo `GetAbsolutePath` seguente al metodo `Main` nella classe `Program`.

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. Quindi, all'interno del metodo `Main` creare i campi per archiviare il percorso degli asset.

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

Aggiungere una nuova directory al progetto per archiviare i dati di input e le classi di stima.

In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**. Quando la nuova cartella viene visualizzata in Esplora soluzioni, assegnarle il nome "DataStructures".

Creare la classe di dati di input nella directory *DataStructures* appena creata.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *DataStructures* e quindi scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *ImageNetData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *ImageNetData.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *ImageNetData.cs*:

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageNetData` al file *ImageNetData.cs*:

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    `ImageNetData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:

    - `ImagePath` contiene il percorso in cui è archiviata l'immagine.
    - `Label` contiene il nome del file.

    Inoltre, `ImageNetData` contiene un metodo `ReadFromFile` che carica più file di immagine archiviati nel `imageFolder` percorso specificato e li restituisce come una raccolta di `ImageNetData` oggetti.

Creare la classe di stima nella directory *DataStructures*.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *DataStructures* e quindi scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *ImageNetPrediction.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *ImageNetPrediction.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *ImageNetPrediction.cs*:

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageNetPrediction` al file *ImageNetPrediction.cs*:

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    `ImageNetPrediction` è la classe di dati di stima e ha il campo `float[]` seguente:

    - `PredictedLabel`contiene le dimensioni, il Punteggio di oggetto e le probabilità della classe per ogni riquadro di delimitazione rilevato in un'immagine.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext` aggiungendo la riga seguente al metodo `Main` di *Program.cs* sotto il campo `outputFolder`.

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a>Creare un parser per la post-elaborazione degli output del modello

Il modello segmenta un'immagine in una griglia `13 x 13`, in cui ogni cella è `32px x 32px`. Ogni cella della griglia contiene 5 rettangoli di selezione di oggetti potenziali. Un rettangolo di selezione contiene 25 elementi:

![Esempio di griglia a sinistra e di esempio di rettangolo di delimitazione a destra](./media/object-detection-onnx/model-output-description.png)

- `x` la posizione x del centro del rettangolo di selezione rispetto alla cella della griglia a cui è associato.
- `y` la posizione y del centro del rettangolo di selezione rispetto alla cella della griglia a cui è associato.
- `w` la larghezza del rettangolo di selezione.
- `h` l'altezza del rettangolo di selezione.
- `o` il valore di confidenza che un oggetto esiste nel rettangolo di selezione, noto anche come punteggio di riconoscimento degli oggetti.
- `p1-p20` le probabilità delle classi per ognuna delle 20 classi stimate dal modello.

In totale, i 25 elementi che descrivono ognuno dei 5 rettangoli di selezione costituiscono i 125 elementi contenuti in ogni cella della griglia.

L'output generato dal modello ONNX già sottoposto a training è una matrice mobile di lunghezza `21125` che rappresenta gli elementi di un tensore con dimensioni `125 x 13 x 13`. Per trasformare le stime generate dal modello in un tensore, è necessario eseguire alcune operazioni di post-elaborazione. A tale scopo, creare un set di classi per l'analisi dell'output.

Aggiungere una nuova directory al progetto per organizzare il set di classi parser.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**. Quando la nuova cartella viene visualizzata in Esplora soluzioni, assegnarle il nome "YoloParser".

### <a name="create-bounding-boxes-and-dimensions"></a>Creare rettangoli di selezione e dimensioni

I dati restituiti dal modello contengono le coordinate e le dimensioni dei rettangoli di selezione degli oggetti all'interno dell'immagine. Creare una classe di base per le dimensioni.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *DimensionsBase.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *DimensionsBase.cs* viene aperto nell'editor del codice. Rimuovere tutte le istruzioni `using` e la definizione di classe esistente.

    Aggiungere il codice seguente per la classe `DimensionsBase` al file *DimensionsBase.cs*:

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    `DimensionsBase`dispone delle `float` proprietà seguenti:

    - `X` contiene la posizione dell'oggetto lungo l'asse x.
    - `Y` contiene la posizione dell'oggetto lungo l'asse y.
    - `Height` contiene l'altezza dell'oggetto.
    - `Width` contiene la larghezza dell'oggetto.

Creare quindi una classe per i rettangoli di selezione.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *YoloBoundingBox.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *YoloBoundingBox.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *YoloBoundingBox.cs*:

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    Appena sopra la definizione di classe esistente, aggiungere una nuova definizione di classe denominata `BoundingBoxDimensions` che eredita dalla `DimensionsBase` classe per contenere le dimensioni del rispettivo rettangolo di delimitazione.

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    Rimuovere la definizione di classe `YoloBoundingBox` esistente e aggiungere il codice seguente per la classe `YoloBoundingBox` al file *YoloBoundingBox.cs*:

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    `YoloBoundingBox`dispone delle proprietà seguenti:

    - `Dimensions` contiene le dimensioni del rettangolo di selezione.
    - `Label` contiene la classe dell'oggetto rilevato nel rettangolo di selezione.
    - `Confidence` contiene la confidenza della classe.
    - `Rect` contiene la rappresentazione del rettangolo delle dimensioni del rettangolo di selezione.
    - `BoxColor` contiene il colore associato alla rispettiva classe usata per disegnare l'immagine.

### <a name="create-the-parser"></a>Creare il parser

Dopo aver creato le classi per le dimensioni e i rettangoli di selezione, è possibile creare il parser.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla directory *YoloParser* e quindi scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *YoloOutputParser.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *YoloOutputParser.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *YoloOutputParser.cs*:

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    All'interno della definizione di classe `YoloOutputParser` esistente aggiungere una classe annidata che contiene le dimensioni di ciascuna cella nell'immagine. Aggiungere il codice seguente per la `CellDimensions` classe che eredita dalla `DimensionsBase` classe all'inizio della `YoloOutputParser` definizione della classe.

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. All'interno della `YoloOutputParser` definizione di classe aggiungere le costanti e i campi seguenti.

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - `ROW_COUNT`: numero di righe nella griglia in cui è divisa l'immagine.
    - `COL_COUNT`: numero di colonne nella griglia in cui è divisa l'immagine.
    - `CHANNEL_COUNT`: numero totale di valori contenuti in una cella della griglia.
    - `BOXES_PER_CELL`: numero di rettangoli di selezione in una cella.
    - `BOX_INFO_FEATURE_COUNT`: numero di funzionalità contenute all'interno di un rettangolo di selezione (x, y, altezza, larghezza, confidenza).
    - `CLASS_COUNT` numero di stime delle classi contenute in ogni rettangolo di selezione.
    - `CELL_WIDTH`: larghezza di una cella nella griglia dell'immagine.
    - `CELL_HEIGHT`: altezza di una cella nella griglia dell'immagine.
    - `channelStride`: posizione iniziale della cella corrente nella griglia.

    Quando il modello esegue una stima, operazione nota anche come assegnazione di punteggi, divide l'immagine di input `416px x 416px` in una griglia di celle delle dimensioni di `13 x 13`. Ogni cella contenuta è `32px x 32px`. All'interno di ogni cella sono presenti 5 rettangoli di selezione, ognuno contenente 5 funzionalità (x, y, larghezza, altezza, confidenza). Ogni rettangolo di delimitazione contiene inoltre la probabilità di ogni classe, che in questo caso è 20. Di conseguenza, ogni cella contiene 125 informazioni (5 funzionalità + 20 probabilità delle classi).

Creare un elenco di ancoraggi sotto `channelStride` per tutti i 5 rettangoli di selezione:

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

Gli ancoraggi sono rapporti di altezza e larghezza predefiniti per i rettangoli di selezione. La maggior parte degli oggetti o delle classi rilevate da un modello ha proporzioni simili. Questo è importante quando si tratta di creare rettangoli di selezione. Anziché stimare i rettangoli di selezione, viene calcolato l'offset dalle dimensioni predefinite, riducendo di conseguenza il calcolo necessario per stimare il rettangolo di selezione. In genere i rapporti di ancoraggio vengono calcolati in base al set di dati usato. In questo caso, poiché il set di dati è noto e i valori sono stati pre-calcolati, gli ancoraggi possono essere hardcoded.

Definire quindi le etichette o le classi che devono essere stimate dal modello. Questo modello stima 20 classi, ovvero un subset del numero totale di classi stimate dal modello YOLOv2 originale.

Aggiungere l'elenco di etichette sotto `anchors`.

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

A ognuna delle classi sono associati colori specifici. Assegnare i colori delle classi sotto `labels`:

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a>Creare funzioni di supporto

La fase di post-elaborazione prevede una serie di passaggi. Per semplificare questi passaggi, è possibile usare diversi metodi di supporto.

I metodi di supporto usati dal parser sono:

- `Sigmoid`: applica la funzione sigma che restituisce un numero compreso tra 0 e 1.
- `Softmax`: normalizza un vettore di input in una distribuzione di probabilità.
- `GetOffset`: esegue il mapping degli elementi nell'output di un modello unidimensionale alla posizione corrispondente in un tensore `125 x 13 x 13`.
- `ExtractBoundingBoxes`: estrae le dimensioni dei rettangoli di selezione usando il metodo `GetOffset` dall'output del modello.
- `GetConfidence`estrae il valore di confidenza che indica il modo in cui il modello ha rilevato un oggetto e utilizza la `Sigmoid` funzione per trasformarla in una percentuale.
- `MapBoundingBoxToCell`: usa le dimensioni del rettangolo di selezione e ne esegue il mapping alla rispettiva cella all'interno dell'immagine.
- `ExtractClasses`: estrae le stime delle classi per il rettangolo di selezione dall'output del modello usando il metodo `GetOffset` e le converte in una distribuzione di probabilità tramite il metodo `Softmax`.
- `GetTopResult`: seleziona la classe dall'elenco delle classi stimate con la probabilità maggiore.
- `IntersectionOverUnion`: filtra i rettangoli di selezione sovrapposti con probabilità inferiori.

Aggiungere il codice per tutti i metodi di supporto sotto l'elenco `classColors`.

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

Dopo aver definito tutti i metodi di supporto, è possibile usarli per elaborare l'output del modello.

Sotto il metodo `IntersectionOverUnion` creare il metodo `ParseOutputs` per elaborare l'output generato dal modello.

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

Creare un elenco per archiviare i rettangoli di selezione e definire variabili all'interno del metodo `ParseOutputs`.

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

Ogni immagine è divisa in una griglia di celle `13 x 13`. Ogni cella contiene cinque rettangoli di selezione. Sotto la variabile `boxes` aggiungere il codice per elaborare tutti i rettangoli in ognuna delle celle.

```csharp
for (int row = 0; row < ROW_COUNT; row++)
{
    for (int column = 0; column < COL_COUNT; column++)
    {
        for (int box = 0; box < BOXES_PER_CELL; box++)
        {

        }
    }
}
```

All'interno del ciclo più interno calcolare la posizione iniziale del rettangolo corrente all'interno dell'output del modello unidimensionale.

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

Direttamente sotto usare il metodo `ExtractBoundingBoxDimensions` per ottenere le dimensioni del rettangolo di selezione corrente.

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

Usare quindi il metodo `GetConfidence` per ottenere la confidenza per il rettangolo di selezione corrente.

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

Usare ora il metodo `MapBoundingBoxToCell` per eseguire il mapping del rettangolo di selezione corrente alla cella corrente in fase di elaborazione.

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

Prima di eseguire altre operazioni di elaborazione, controllare se il valore di confidenza è maggiore della soglia specificata. In caso contrario, elaborare il rettangolo di selezione successivo.

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

Altrimenti, proseguire con l'elaborazione dell'output. Il passaggio successivo consiste nell'ottenere la distribuzione di probabilità delle classi stimate per il rettangolo di selezione corrente usando il metodo `ExtractClasses`.

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

Usare quindi il metodo `GetTopResult` per ottenere il valore e l'indice della classe con la probabilità maggiore per il rettangolo corrente e calcolarne il punteggio.

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

Usare `topScore` ancora una volta per mantenere solo i rettangoli di selezione che superano la soglia specificata.

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

Infine, se il rettangolo di selezione corrente supera la soglia, creare un nuovo oggetto `BoundingBox` e aggiungerlo all'elenco `boxes`.

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

Dopo aver elaborato tutte le celle nell'immagine, restituire l'elenco `boxes`. Aggiungere l'istruzione return seguente sotto il ciclo for più esterno nel metodo `ParseOutputs`.

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a>Filtrare i rettangoli sovrapposti

Ora che tutti i rettangoli di selezione con confidenza elevata sono stati estratti dall'output del modello, è necessario filtrarli ulteriormente per rimuovere le immagini sovrapposte. Aggiungere un metodo denominato `FilterBoundingBoxes` sotto il metodo `ParseOutputs`:

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

All'interno del metodo `FilterBoundingBoxes` iniziare creando una matrice uguale alle dimensioni dei rettangoli rilevati e contrassegnando tutti gli slot come attivi o pronti per l'elaborazione.

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

Ordinare quindi l'elenco contenente i rettangoli di selezione in ordine decrescente in base alla confidenza.

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

Infine, creare un elenco che conterrà i risultati filtrati.

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

Iniziare a elaborare ogni rettangolo di selezione tramite l'iterazione.

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

All'interno di questo ciclo for controllare se il rettangolo di selezione corrente può essere elaborato.

```csharp
if (isActiveBoxes[i])
{

}
```

Se sì, aggiungere il rettangolo di selezione all'elenco dei risultati. Se i risultati superano il limite specificato di caselle da estrarre, interrompere il ciclo. Aggiungere il codice seguente all'interno dell'istruzione if.

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

In caso contrario, controllare i rettangoli di selezione adiacenti. Aggiungere il codice seguente sotto il controllo del limite di rettangoli.

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

Come per il primo rettangolo, se il rettangolo adiacente è attivo o pronto per l'elaborazione, usare il metodo `IntersectionOverUnion` per verificare se il primo e il secondo rettangolo superano la soglia specificata. Aggiungere il codice seguente al ciclo for più interno.

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

All'esterno del ciclo for più interno che controlla i rettangoli di selezione adiacenti, verificare se sono presenti altri rettangoli di selezione da elaborare. In caso contrario, interrompere il ciclo for esterno.

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

Infine, all'esterno del ciclo for iniziale del metodo `FilterBoundingBoxes` restituire i risultati:

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

Ottimo. È ora possibile usare il codice insieme al modello per l'assegnazione dei punteggi.

## <a name="use-the-model-for-scoring"></a>Usare il modello per l'assegnazione dei punteggi

Analogamente alla post-elaborazione, la fase di assegnazione dei punteggi prevede alcuni passaggi. Per semplificare questi passaggi, aggiungere una classe che conterrà la logica di assegnazione dei punteggi al progetto.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *OnnxModelScorer.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *OnnxModelScorer.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *OnnxModelScorer.cs*:

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    Aggiungere le variabili seguenti all'interno della definizione di classe `OnnxModelScorer`.

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    Direttamente sotto creare un costruttore per la classe `OnnxModelScorer` che Inizializzerà le variabili definite in precedenza.

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    Dopo aver creato il costruttore, definire un paio di struct che contengono variabili correlate alle impostazioni dell'immagine e del modello. Creare uno struct denominato `ImageNetSettings` che conterrà l'altezza e la larghezza previste come input per il modello.

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    Successivamente, creare un'altra struttura denominata `TinyYoloModelSettings` che contiene i nomi dei livelli di input e di output del modello. Per visualizzare il nome dei livelli di input e output del modello, è possibile usare uno strumento come [Netron](https://github.com/lutzroeder/netron).

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    Creare quindi il primo set di metodi da usare per l'assegnazione dei punteggi. Creare il metodo `LoadModel` all'interno della classe `OnnxModelScorer`.

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    All'interno del metodo `LoadModel` aggiungere il codice seguente per la registrazione.

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    Le pipeline ML.NET devono essere a conoscenza dello schema dei dati per operare quando [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) viene chiamato il metodo. In questo caso, verrà usato un processo simile al training. Tuttavia, poiché non si verifica alcun training effettivo, è accettabile usare un oggetto vuoto [`IDataView`](xref:Microsoft.ML.IDataView) . Crea un nuovo oggetto [`IDataView`](xref:Microsoft.ML.IDataView) per la pipeline da un elenco vuoto.

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    Sotto questo codice definire la pipeline. La pipeline sarà costituita da quattro trasformazioni.

    - [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*)carica l'immagine come bitmap.
    - [`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*)Ridimensiona l'immagine alla dimensione specificata (in questo caso `416 x 416` ).
    - [`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*)modifica la rappresentazione in pixel dell'immagine da una bitmap a un vettore numerico.
    - [`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*)carica il modello ONNX e lo usa per assegnare un punteggio ai dati forniti.

    Definire la pipeline nel metodo `LoadModel` sotto la variabile `data`.

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    È ora possibile creare un'istanza del modello per l'assegnazione dei punteggi. Chiamare il [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) Metodo sulla pipeline e restituirlo per un'ulteriore elaborazione.

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

Una volta caricato, il modello può essere usato per eseguire stime. Per semplificare il processo, creare un metodo denominato `PredictDataUsingModel` sotto il metodo `LoadModel`.

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

All'interno di `PredictDataUsingModel` aggiungere il codice seguente per la registrazione.

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

Usare quindi il [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) metodo per assegnare un punteggio ai dati.

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

Estrarre le probabilità stimate e restituirle per l'ulteriore elaborazione.

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

Una volta configurati entrambi i passaggi, combinarli in un unico metodo. Sotto il metodo `PredictDataUsingModel` aggiungere un nuovo metodo denominato `Score`.

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

La configurazione è stata completata. È ora possibile usarla per lo scopo di questa esercitazione.

## <a name="detect-objects"></a>Rilevare oggetti

Dopo aver completato la configurazione, è possibile iniziare a rilevare alcuni oggetti. Per iniziare, aggiungere i riferimenti al marcatore e al parser nella classe *Program.cs*.

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a>Assegnare punteggi agli output del modello e analizzarli

All'interno del metodo `Main` della classe *Program.cs* aggiungere un'istruzione try-catch.

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

All'interno del blocco `try` iniziare a implementare la logica di rilevamento degli oggetti. Per prima cosa, caricare i dati in un oggetto [`IDataView`](xref:Microsoft.ML.IDataView) .

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

Creare quindi un'istanza di `OnnxModelScorer` e usarla per assegnare punteggi ai dati caricati.

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

È ora possibile passare alla fase di post-elaborazione. Creare un'istanza di `YoloOutputParser` e usarla per elaborare l'output del modello.

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

Dopo aver elaborato l'output del modello, è possibile tracciare i rettangoli di selezione sulle immagini.

### <a name="visualize-predictions"></a>Visualizzare stime

Dopo che il modello ha assegnato un punteggio alle immagini e gli output sono stati elaborati, è necessario disegnare i rettangoli di selezione sull'immagine. A tale scopo, aggiungere un metodo denominato `DrawBoundingBox` sotto il metodo `GetAbsolutePath` all'interno di *Program.cs*.

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

Caricare prima di tutto l'immagine e ottenere le dimensioni di altezza e larghezza nel metodo `DrawBoundingBox`.

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

Creare quindi un ciclo for-each per eseguire l'iterazione di ogni rettangolo di selezione rilevato dal modello.

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

All'interno del ciclo for-each, ottenere le dimensioni del rettangolo di selezione.

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

Poiché le dimensioni del rettangolo di selezione corrispondono all'input del modello di `416 x 416`, ridimensionare il rettangolo di selezione in modo che le sue dimensioni corrispondano a quelle effettive dell'immagine.

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

Definire quindi un modello per il testo che verrà visualizzato al di sopra di ogni rettangolo di delimitazione. Il testo conterrà la classe dell'oggetto all'interno del rispettivo rettangolo di selezione e la confidenza.

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

Per creare l'immagine, convertirla in un [`Graphics`](xref:System.Drawing.Graphics) oggetto.

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

All'interno del `using` blocco di codice, ottimizzare le [`Graphics`](xref:System.Drawing.Graphics) impostazioni dell'oggetto grafico.

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

Al di sotto, impostare le opzioni relative al tipo di carattere e al colore per il testo e il rettangolo di selezione.

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

Creare e riempire un rettangolo sopra il rettangolo di delimitazione per contenere il testo usando il [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) metodo. Ciò consentirà di creare un contrasto per il testo e migliorare la leggibilità.

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

Quindi, creare il testo e il rettangolo di delimitazione dell'immagine usando [`DrawString`](xref:System.Drawing.Graphics.DrawString*) i [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) metodi e.

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

Al di fuori del ciclo for-each aggiungere il codice per salvare le immagini in `outputDirectory`.

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

Per ottenere un ulteriore riscontro che l'applicazione stia eseguendo le stime come previsto in fase di runtime, aggiungere un metodo denominato `LogDetectedObjects` sotto il metodo `DrawBoundingBox` nel file *Program.cs* per restituire gli oggetti rilevati nella console.

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

Ora che sono disponibili metodi helper per creare un riscontro visivo dalle stime, aggiungere un ciclo for per scorrere ognuna delle immagini con punteggio.

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

All'interno del ciclo for ottenere il nome del file di immagine e dei rettangoli di selezione associati.

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

Sotto questo codice usare il metodo `DrawBoundingBox` per tracciare i rettangoli di selezione sull'immagine.

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

Infine, usare il metodo `LogDetectedObjects` per restituire le stime alla console.

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

Dopo l'istruzione try-catch aggiungere logica aggiuntiva per indicare che l'esecuzione del processo è stata completata.

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

Ecco fatto!

## <a name="results"></a>Risultati

Dopo aver completato i passaggi precedenti, eseguire l'app console (CTRL+F5). I risultati saranno simili all'output seguente. È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.

```console
=====Identify the objects in the images=====

.....The objects in the image image1.jpg are detected as below....
car and its Confidence score: 0.9697262
car and its Confidence score: 0.6674225
person and its Confidence score: 0.5226039
car and its Confidence score: 0.5224892
car and its Confidence score: 0.4675332

.....The objects in the image image2.jpg are detected as below....
cat and its Confidence score: 0.6461141
cat and its Confidence score: 0.6400049

.....The objects in the image image3.jpg are detected as below....
chair and its Confidence score: 0.840578
chair and its Confidence score: 0.796363
diningtable and its Confidence score: 0.6056048
diningtable and its Confidence score: 0.3737402

.....The objects in the image image4.jpg are detected as below....
dog and its Confidence score: 0.7608147
person and its Confidence score: 0.6321323
dog and its Confidence score: 0.5967442
person and its Confidence score: 0.5730394
person and its Confidence score: 0.5551759

========= End of Process..Hit any Key ========
```

Per visualizzare le immagini con i rettangoli di selezione, passare alla directory `assets/images/output/`. Di seguito viene fornito un esempio da una delle immagini elaborate.

![Esempio di immagine elaborata di una sala da pranzo](./media/object-detection-onnx/dinning-room-table-chairs.png)

Congratulazioni! È stato creato un modello di Machine Learning per il rilevamento di oggetti riutilizzando un modello `ONNX` già sottoposto a training in ML.NET.

Il codice sorgente per questa esercitazione è reperibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) .

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Informazioni sul problema
> - Acquisire familiarità con ONNX e comprenderne il funzionamento con ML.NET
> - Acquisire familiarità con il modello
> - Riutilizzare il modello già sottoposto a training
> - Rilevare oggetti con un modello caricato

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di oggetti esteso.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
