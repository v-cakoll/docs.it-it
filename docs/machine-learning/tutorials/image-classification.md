---
title: 'Esercitazione: Ripetere il training del classificatore di immagini TensorFlow - apprendimento trasferito'
description: Informazioni su come ripetere il training di un modello TensorFlow di classificazione delle immagini con l'apprendimento trasferito e ML.NET. Il modello originale è stato sottoposto a training per classificare le singole immagini. Dopo la ripetizione del training, il nuovo modello organizza le immagini in categorie ampie.
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: e069abe44b77b1dc31b78ecec1971ccc73f2e012
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054072"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a>Esercitazione: Ripetere il training di un classificatore di immagini TensorFlow con l'apprendimento trasferito e ML.NET

Informazioni su come ripetere il training di un modello TensorFlow di classificazione delle immagini con l'apprendimento trasferito e ML.NET. Il modello originale è stato sottoposto a training per classificare le singole immagini. Dopo la ripetizione del training, il nuovo modello organizza le immagini in categorie ampie. 

Il training di un modello di [classificazione delle immagini](https://en.wikipedia.org/wiki/Outline_of_object_recognition) da zero richiede l'impostazione di milioni di parametri, di una considerevole quantità di dati di training con etichetta e di un notevole importo di risorse di calcolo (centinaia di ore di GPU). Anche se non è così efficace come il training di un modello personalizzato da zero, l'apprendimento trasferito consente di semplificare questo processo usando migliaia di immagini anziché milioni di immagini con etichetta e di creare un modello personalizzato abbastanza rapidamente (entro un'ora in un computer senza GPU).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Riutilizzare e ottimizzare il modello con training preliminare
> * Classificare le immagini

## <a name="what-is-transfer-learning"></a>Che cos'è l'apprendimento trasferito?

Sarebbe bello poter riutilizzare un modello che è già stato sottoposto a training per risolvere un problema analogo e rieseguire il training di tutti o di alcuni livelli di tale modello per risolvere un problema riscontrato. Questa tecnica che prevede il riutilizzo di parte di un modello già sottoposto a training per crearne uno nuovo è nota come [apprendimento trasferito](https://en.wikipedia.org/wiki/Transfer_learning).

## <a name="image-classification-sample-overview"></a>Panoramica dell'esempio di classificazione delle immagini

L'esempio è un'applicazione console che usa ML.NET per creare un classificatore di immagini riutilizzando un modello con training preliminare per classificare le immagini con una piccola quantità di dati di training.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF). Si noti che per impostazione predefinita il progetto .NET per questa esercitazione è configurato per .NET Core 2.2.

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato. 

* Pacchetto NuGet Microsoft.ML 1.0.0
* Pacchetto NuGet Microsoft.ML.ImageAnalytics 1.0.0
* Pacchetto NuGet Microsoft.ML.TensorFlow 0.12.0

* [File ZIP della directory assets dell'esercitazione](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [Modello di Machine Learning InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Il [Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) è un subset di Machine Learning che sta rivoluzionando aree quali Visione artificiale e Riconoscimento vocale.

I modelli di Deep Learning vengono sottoposti a training con set di grandi dimensioni di [dati con etichetta](https://en.wikipedia.org/wiki/Labeled_data) e [reti neurali](https://en.wikipedia.org/wiki/Artificial_neural_network) contenenti più livelli di apprendimento. Il Deep Learning:

* Offre prestazioni ottimali per alcune attività come Visione artificiale.

* Assicura buone prestazioni con quantità di dati molto elevate.

La classificazione delle immagini è un'attività comune di Machine Learning che consente di classificare automaticamente le immagini in più categorie, ad esempio tramite:

* Rilevamento di un volto umano in un'immagine.
* Rilevamento di cani o gatti.

 Oppure, come nelle immagini seguenti, determinando se un'immagine appartiene alla categoria dei cibi, dei giocattoli o degli elettrodomestici:

![immagine di una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![immagine di un orsetto](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![immagine di un tostapane](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Le immagini precedenti appartengono a Wikimedia Commons, con gli attributi seguenti:
>
> * "220px-Pepperoni_pizza.jpg" pubblico dominio, https://commons.wikimedia.org/w/index.php?curid=79505,
> * "119px-Nalle_-_a_small_brown_teddy_bear.jpg" di [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Fotografia autoprodotta, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * "193px-Broodrooster.jpg" di [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Opera propria, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

L'apprendimento trasferito prevede alcune strategie, come la *ripetizione del training di tutti i livelli* e il *penultimo livello*. Questa esercitazione illustrerà e spiegherà come usare la *strategia del penultimo livello*. La *strategia del penultimo livello* riutilizza un modello che è già stato sottoposto a training per risolvere un problema specifico. Questa strategia prevede quindi la ripetizione del training del livello finale del modello per consentire la risoluzione di un nuovo problema. Il riutilizzo del modello già sottoposto a training nell'ambito del nuovo modello comporterà un risparmio significativo di tempo e risorse.

Il modello di classificazione delle immagini riutilizza il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), un modello di riconoscimento delle immagini ampiamente diffuso sottoposto a training con il set di dati `ImageNet`, in cui il modello TensorFlow prova a classificare intere immagini in migliaia di classi, come "Umbrella", "Jersey" e "Dishwasher".

`Inception v1 model` può essere classificato come una [rete neurale convoluzionale profonda](https://en.wikipedia.org/wiki/Convolutional_neural_network) e può ottenere prestazioni ragionevoli con attività di riconoscimento visivo complesse, uguagliando o superando le prestazioni umane in alcuni campi. Il modello/algoritmo è stato sviluppato da più ricercatori ed è basato sul whitepaper originale ["Rethinking the Inception Architecture for Computer Vision" a cura di Szegedy e altri autori](https://arxiv.org/abs/1512.00567).

Poiché il `Inception model` è già stato sottoposto a training con migliaia di immagini diverse, contiene le [caratteristiche delle immagini](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necessarie per la loro identificazione. I livelli delle caratteristiche delle immagini inferiori riconoscono caratteristiche semplici (come i contorni), mentre quelli più elevati riconoscono caratteristiche più complesse (come le forme). Il livello finale è sottoposto a training con un set di dati molto più piccolo perché si inizia con un modello con training preliminare che è già in grado di classificare le immagini. Dal momento che il modello consente di classificare più di due categorie, questo è un esempio di un [classificatore multiclasse](../resources/tasks.md#multiclass-classification). 

`TensorFlow` è un popolare toolkit di Deep Learning e Machine Learning che consente il training delle reti neurali profonde (e i calcoli numerici generali) e viene implementato come `transformer` in ML.NET. Per questa esercitazione, viene usato per riutilizzare il `Inception model`.

Come illustrato nel diagramma seguente, viene aggiunto un riferimento ai pacchetti NuGet ML.NET nelle applicazioni .NET Core o .NET Framework. Dietro le quinte, ML.NET include e fa riferimento alla libreria `TensorFlow` nativa che consente di scrivere codice che carica un file del modello `TensorFlow` esistente già sottoposto a training per l'assegnazione del punteggio.  

![Diagramma dell'architettura ML.NET per la trasformazione TensorFlow](./media/image-classification/tensorflow-mlnet.png)

Il `Inception model` viene sottoposto a training per classificare le immagini in migliaia di categorie, ma è necessario classificare le immagini in un set più piccolo di categorie limitate. Specificare la parte `transfer` di `transfer learning`. È possibile trasferire la capacità del `Inception model` di riconoscere e classificare le immagini alle nuove categorie limitate del classificatore di immagini personalizzato.  

 Si intende ripetere il training dell'ultimo livello di tale modello usando un set di tre categorie:

* Cibo
* Giocattoli
* Elettrodomestici

Il livello usa un [algoritmo di regressione logistica multinomiale](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) per trovare la categoria corretta nel minor tempo possibile. Questo algoritmo procede alla classificazione tramite l'uso delle probabilità per determinare la risposta, assegnando un valore uno alla categoria corretta e un valore zero alle altre.  

### <a name="dataset"></a>DataSet

Ci sono due origini dati: il file `.tsv` e i file di immagine.  Il file `tags.tsv` contiene due colonne: la prima è definita come `ImagePath` e la seconda è l'oggetto `Label` corrispondente all'immagine. Il file di esempio seguente non ha una riga di intestazione e ha l'aspetto seguente:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Le immagini di training e di test si trovano nelle cartelle assets che verranno scaricate in un file ZIP. Queste immagini appartengono a Wikimedia Commons.
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), il repository di file multimediali gratuiti.* Recuperate il 17 ottobre 2018, alle 10.48, da:  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>Creare un'applicazione console

### <a name="create-a-project"></a>Creare un progetto

1. Creare un'**applicazione console di .NET Core** con nome "TransferLearningTF".

2. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia e cercare **Microsoft.ML**. Fare clic sull'elenco a discesa **Versione**, selezionare il pacchetto **1.0.0** nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati. Ripetere questi passaggi per **Microsoft.ML.ImageAnalytics v1.0.0** e **Microsoft.ML.TensorFlow v0.12.0**.

### <a name="prepare-your-data"></a>Preparare i dati

1. Scaricare il [file ZIP della directory assets del progetto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) e decomprimerlo.

2. Copiare la directory `assets` nella directory del progetto *TransferLearningTF*. Questa directory e le relative sottodirectory contengono i file di dati e supporto (fatta eccezione per il modello Inception, che verrà scaricato e aggiunto nel passaggio successivo) richiesti per questa esercitazione.

3. Scaricare il [modello Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) e decomprimere il file.

4. Copiare il contenuto della directory `inception5h` appena decompressa nella directory `assets\inputs-train\inception` del progetto *TransferLearningTF*. Questa directory contiene il modello e i file di supporto aggiuntivi necessari per questa esercitazione, come illustrato nell'immagine seguente:

   ![Contenuto della directory Inception](./media/image-classification/inception-files.png)

5. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file nella directory assets e nelle relative sottodirectory e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

Creare campi globali per i percorsi delle diverse risorse e variabili globali per `LabelTokey`, `ImageReal` e `PredictedLabelValue`:

* `_assetsPath` contiene il percorso delle risorse.
* `_trainTagsTsv` contiene il percorso del file TSV dei tag dei dati delle immagini di training.
* `_predictTagsTsv` contiene il percorso del file TSV dei tag dei dati delle immagini di stima.
* `_trainImagesFolder` contiene il percorso delle immagini usate per il training del modello.
* `_predictImagesFolder` contiene il percorso delle immagini che devono essere classificate dal modello sottoposto a training.
* `_inceptionPb` contiene il percorso del modello Inception con training preliminare da riutilizzare per ripetere il training del modello.
* `_inputImageClassifierZip` contiene il percorso da cui viene caricato il modello sottoposto a training.
* `_outputImageClassifierZip` contiene il percorso in cui è salvato il modello sottoposto a training.
* `LabelTokey` è il valore `Label` associato a una chiave.
* `ImageReal` è la colonna contenente il valore dell'immagine stimato.
* `PredictedLabelValue` è la colonna contenente il valore dell'etichetta stimato.

Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

Creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ImageData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *ImageData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *ImageData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente per la classe `ImageData` al file *ImageData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData` è la classe dei dati di immagine di input e ha i campi <xref:System.String> seguenti:

* `ImagePath` contiene il nome del file di immagine.
* `Label` contiene un valore per l'etichetta dell'immagine.

Aggiungere una nuova classe al progetto per `ImagePrediction`:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ImagePrediction.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *ImagePrediction.cs* verrà aperto nell'editor del codice. Rimuovere entrambe le istruzioni `using` `System.Collections.Generic` e `System.Text` all'inizio di *ImagePrediction.cs*:

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene la classe `ImagePrediction`, al file *ImagePrediction.cs*:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction` è la classe di stima delle immagini e ha i campi seguenti:

* `Score` contiene la percentuale di probabilità per una data classificazione dell'immagine.
* `PredictedLabelValue` contiene un valore per l'etichetta di classificazione dell'immagine stimata.

`ImagePrediction` è la classe usata per la stima dopo il training del modello. Ha un oggetto `string` (`ImagePath`) per il percorso dell'immagine. L'elemento `Label` viene usato per riutilizzare il modello e ripeterne il training. `PredictedLabelValue` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Inizializzare la variabile `mlContext` con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>Creare uno struct per i parametri predefiniti

Il modello Inception ha diversi parametri predefiniti che è necessario passare. Creare uno struct per eseguire il mapping dei valori dei parametri predefiniti a nomi descrittivi con il codice seguente, subito dopo il metodo `Main()`:

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Creare un metodo dell'utilità di visualizzazione

Poiché i dati dell'immagine e le relative stime verranno visualizzati più volte, creare un metodo dell'utilità di visualizzazione per gestire la visualizzazione dell'immagine e dei risultati delle stime.

Il metodo `DisplayResults()` esegue le attività seguenti:

* Visualizza i risultati stimati.

Creare il metodo `DisplayResults()` subito dopo lo struct `InceptionSettings`, usando il codice seguente:

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

Il metodo `Transform()` ha popolato `ImagePath` in `ImagePrediction` insieme ai campi stimati. Nel corso del processo ML.NET ogni componente aggiunge colonne e ciò rende più facile visualizzare i risultati:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

Verrà chiamato il metodo `DisplayResults()` nei due metodi di classificazione delle immagini.

### <a name="create-a-tsv-file-utility-method"></a>Creare un metodo dell'utilità con file TSV

Il metodo `ReadFromTsv()` esegue le attività seguenti:

* Legge il file `tags.tsv` dei dati di immagine.
* Aggiunge il percorso del file al nome del file di immagine.
* Carica i dati del file in un oggetto IEnumerable`ImageData`.

Creare il metodo `ReadFromTsv()` subito dopo il metodo `PairAndDisplayResults()`, usando il codice seguente:

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

Il codice seguente analizza il file `tags.tsv` per aggiungere il percorso del file al nome del file di immagine per la proprietà `ImagePath` e carica `Label` in un oggetto `ImageData`. Aggiungerlo come prima riga del metodo `ReadFromTsv()`.  È necessario il percorso completo del file per visualizzare i risultati della stima.

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
ML.NET si basa su tre concetti fondamentali: [dati](../resources/glossary.md#data), [trasformatori](../resources/glossary.md#transformer) e [strumenti di stima](../resources/glossary.md#estimator).

## <a name="reuse-and-tune-pre-trained-model"></a>Riutilizzare e ottimizzare il modello con training preliminare

Aggiungere la seguente chiamata al metodo `ReuseAndTuneInceptionModel()` come riga successiva nel metodo `Main()`:

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

Il metodo `ReuseAndTuneInceptionModel()` esegue le attività seguenti:

* Carica i dati.
* Estrae e trasforma i dati.
* Assegna un punteggio al modello TensorFlow.
* Ottimizza il modello (ripete il training).
* Visualizza i risultati del modello.
* Valuta il modello.
* Restituisce il modello.

Creare il metodo `ReuseAndTuneInceptionModel()`, subito dopo lo struct `InceptionSettings` e subito prima del metodo `DisplayResults()`, usando il codice seguente:

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>Caricare i dati

I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.

Caricare i dati usando il wrapper `MLContext.Data.LoadFromTextFile`. Aggiungere il codice seguente al metodo `ReuseAndTuneInceptionModel()` come riga successiva:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>Estrarre le funzionalità e trasformare i dati

La pre-elaborazione e la pulizia dei dati sono attività importanti che devono essere eseguite prima che un set di dati possa essere usato efficacemente per l'apprendimento automatico.  L'uso dei dati senza queste attività di modellazione può generare risultati fuorvianti.

Gli algoritmi di Machine Learning sono in grado di comprendere i dati sottoposti a [estrazione delle caratteristiche](../resources/glossary.md#feature) e quando si ha a che fare con reti neurali profonde è necessario adattare le immagini al formato previsto dalla rete. Questo formato è un [vettore numerico](../resources/glossary.md#numerical-feature-vector).

Dopo il training e la valutazione, eseguire una stima con i valori della colonna **Etichetta**. Dal momento che si usa un modello con training preliminare, eseguire il mapping dei campi al nuovo modello con il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A). Questo metodo trasforma `Label` in una colonna di tipo chiave numerica (`LabelTokey`) aggiungendola come nuova colonna del set di dati.  Assegnare il nome `estimator` dal momento che verrà aggiunto anche l'algoritmo di training. Aggiungere la riga di codice successiva:

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

Lo strumento di stima per l'elaborazione delle immagini usa algoritmi di estrazione delle caratteristiche della [rete neurale profonda](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) con training preliminare per l'estrazione delle caratteristiche. Quando si usano reti neurali profonde, si adattano le immagini al formato di rete previsto. Questo è il motivo per cui si usano numerose trasformazioni delle immagini per ottenere i dati di immagine nel formato previsto del modello:

1. Le immagini della trasformazione `LoadImages` vengono caricate in memoria come tipo bitmap.
2. La trasformazione `ResizeImages` ridimensiona le immagini dal momento che il modello con training preliminare ha una larghezza e un'altezza definite dell'immagine di input.
3. La trasformazione `ExtractPixels` estrae i pixel dalle immagini di input e li converte in un vettore numerico.

Aggiungere queste trasformazioni delle immagini come righe di codice successive:

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

`LoadTensorFlowModel` è un metodo pratico che consente di caricare il modello `TensorFlow` una sola volta e quindi crea `TensorFlowEstimator` usando `ScoreTensorFlowModel`. `ScoreTensorFlowModel` estrae gli output specificati (le caratteristiche dell'immagine `softmax2_pre_activation` di `Inception model`) e assegna un punteggio a un set di dati usando il modello `TensorFlow` con training preliminare.

`softmax2_pre_activation` supporta il modello nella determinazione della classe a cui appartengono le immagini. `softmax2_pre_activation` restituisce una probabilità per ognuna delle categorie per un'immagine e tutte queste probabilità devono ammontare a 1. Si presuppone che un'immagine apparterrà solo a una categoria, come illustrato nell'esempio seguente:

| Classe         | Probabilità   |
| ------------- | ------------- |
| `Food`        |  0.001        |
| `Toy`         |  0.95         |
| `Appliance`   |  0.06         |

Aggiungere `TensorFlowTransform` a `estimator` con la riga di codice seguente:

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>Scegliere un algoritmo di training

Per aggiungere l'algoritmo di training, chiamare il metodo wrapper `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`.  L'oggetto [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) viene aggiunto a `estimator` e accetta le caratteristiche delle immagini di Inception (`softmax2_pre_activation`) e i parametri di input `Label` per l'apprendimento dai dati cronologici.  Aggiungere l'algoritmo di training con il codice seguente:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

È anche necessario eseguire il mapping di `predictedlabel` a `predictedlabelvalue`:

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

Il metodo `Fit()` esegue il training del modello trasformando il set di dati e applicando il training. Eseguire il fit del modello al set di dati e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `ReuseAndTuneInceptionModel()`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) effettua previsioni per più righe di input specificate di un set di dati di test.  Trasformare i dati `Training` aggiungendo il codice seguente a `ReuseAndTuneInceptionModel()`:

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

Convertire i dati di immagine e gli elementi `DataViews` della stima in `IEnumerables` fortemente tipizzati per associarli per una visualizzazione semplificata. Usare il metodo `MLContext.CreateEnumerable()` a tale scopo, con il codice seguente:

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

Aggiungere il codice seguente per visualizzare i dati e le stime come righe successive nel `ReuseAndTuneInceptionModel()` metodo:

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

Dopo aver impostato la stima, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):

* Valuta il modello (confrontando i valori stimati con gli oggetti `Labels` effettivi nel set di dati).

* Restituisce le metriche relative alle prestazioni del modello.

Aggiungere il codice seguente al metodo `ReuseAndTuneInceptionModel()` come riga successiva:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

Le metriche seguenti vengono valutate per la classificazione delle immagini:

* `Log-loss`: vedere [Perdita di log](../resources/glossary.md#log-loss). Il valore desiderato per LogLoss è il valore più prossimo a 0.

* [https://login.microsoftonline.com/consumers/](`Per class Log-loss`). Il valore desiderato per LogLoss per classe è il valore più prossimo a 0.

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 Aggiungere il codice seguente per restituire il modello sottoposto a training come riga successiva:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a>Classificare le immagini con un modello caricato

Aggiungere la chiamata seguente al metodo `ClassifyImages()` come riga di codice successiva nel metodo `Main`:

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

Il metodo `ClassifyImages()` esegue le attività seguenti:

* Legge il file TSV in `IEnumerable`.
* Stima le classificazioni delle immagini in base ai dati di test.

Creare il metodo `ClassifyImages()`, subito dopo il metodo `ReuseAndTuneInceptionModel()` e subito prima del metodo `PairAndDisplayResults()`, usando il codice seguente:

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

Per prima cosa, chiamare il metodo `ReadFromTsv()` per creare una classe `IEnumerable<ImageData>` contenente il percorso completo per ogni `ImagePath`. Questo percorso del file è necessario per associare i dati e i risultati della stima. È anche necessario convertire la classe `IEnumerable<ImageData>` in un elemento `IDataView` che verrà usato per la stima. Aggiungere il codice seguente al metodo `ClassifyImages()` come le due righe successive:

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

Come è stato fatto in precedenza con i dati delle immagini di training, stimare la categoria dei dati di immagine di test usando il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) del modello passato. Aggiungere il codice seguente al metodo `ClassifyImages()` per le stime e per convertire gli elementi `IDataView` di `predictions` in un `IEnumerable` per l'associazione e la visualizzazione:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

Per associare e visualizzare i dati di immagine di test e le stime, aggiungere il codice seguente per chiamare il metodo `DisplayResults()` precedentemente creato come riga successiva nel metodo `ClassifyImages()`:

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>Classificare una singola immagine con un modello caricato

Aggiungere la chiamata seguente al metodo `ClassifySingleImage()` come riga di codice successiva nel metodo `Main`:

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

Il metodo `ClassifySingleImage()` esegue le attività seguenti:

* Carica un'istanza di `ImageData`.
* Stima la classificazione delle immagini in base ai dati di test.

Creare il metodo `ClassifySingleImage()`, subito dopo il metodo `ClassifyImages()` e subito prima del metodo `PairAndDisplayResults()`, usando il codice seguente:

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

Per prima cosa, creare una classe `ImageData` contenente il percorso completo e il nome del file di immagine per il singolo `ImagePath`. Aggiungere il codice seguente al metodo `ClassifySingleImage()` come righe successive:

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

La [classe PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API utile che esegue una stima su una singola istanza di dati. La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una previsione su una singola colonna di dati. Passare `imageData` a `PredictionEngine` per prevedere la categoria dell'immagine aggiungendo il codice seguente a `ClassifySingleImage()`:

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

Visualizzare i risultati della stima come riga di codice successiva nel metodo `ClassifySingleImage()`:

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>Risultati

Dopo aver completato i passaggi precedenti, eseguire l'app console (CTRL+F5). I risultati saranno simili all'output seguente.  È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

La procedura è stata completata. È stato creato un modello di Machine Learning per la classificazione delle immagini riutilizzando un modello `TensorFlow` con training preliminare in ML.NET.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Riutilizzare e ottimizzare il modello con training preliminare
> * Classificare le immagini con un modello caricato

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di classificazione delle immagini esteso.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/)
