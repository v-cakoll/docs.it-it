---
title: Raggruppare i fiori iris usando un algoritmo di apprendimento automatico basato sul clustering - ML.NET
description: Informazioni su come usare ML.NET in uno scenario di clustering
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 5bd73c774f60466daaf52215c34e7e17b5f5cc9c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145628"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a>Esercitazione: Raggruppare i fiori iris usando un algoritmo di apprendimento automatico basato sul clustering con ML.NET

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa esercitazione illustra come usare ML.NET per compilare un [modello di clustering](../resources/tasks.md#clustering) per il [set di dati dei fiori iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> - Informazioni sul problema
> - Selezionare l'attività di apprendimento automatico appropriata
> - Preparare i dati
> - Caricare e trasformare i dati
> - Scegliere un algoritmo di apprendimento
> - Eseguire il training del modello
> - Usare il modello per le stime

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

## <a name="understand-the-problem"></a>Informazioni sul problema

Questo problema riguarda il set dei fiori iris in gruppi diversi in base alle caratteristiche dei fiori. Tali caratteristiche sono la lunghezza e la larghezza di un sepalo e la lunghezza e la larghezza di un petalo. Per questa esercitazione, si supponga che il tipo di ogni fiore sia sconosciuto. Si desidera apprendere la struttura di un set di dati dalle caratteristiche e prevedere come un'istanza di dati si adatta a questa struttura.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Poiché non si sa a quale gruppo appartenga ciascun fiore, scegliere l'attività di [apprendimento automatico senza supervisione](../resources/glossary.md#unsupervised-machine-learning). Per dividere un set di dati in gruppi in modo che gli elementi nello stesso gruppo siano più simili tra loro rispetto a quelli di altri gruppi, usare un'attività di apprendimento automatico di [clustering](../resources/tasks.md#clustering).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "IrisClustering" e quindi selezionare il pulsante **OK**.

1. Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

1. Installare il pacchetto NuGet **Microsoft.ML**:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="prepare-the-data"></a>Preparare i dati

1. Scaricare il set di dati [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) e salvarlo nella cartella *Dati* creata nel passaggio precedente. Per altre informazioni sui set di dati iris, vedere la pagina [Dataset Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) di Wikipedia e la pagina [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris), che rappresenta l'origine del set di dati.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *iris.data* e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

Il file *iris.data* contiene cinque colonne che rappresentano:

- lunghezza del sepalo in centimetri
- larghezza del sepalo in centimetri
- lunghezza del petalo in centimetri
- larghezza del petalo in centimetri
- tipo di fiore iris

Per l'esempio del clustering, questa esercitazione ignora l'ultima colonna.

## <a name="create-data-classes"></a>Creare classi di dati

Creare le classi per i dati di input e le stime:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *IrisData.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere la direttiva `using` seguente al nuovo file:

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le classi `IrisData` e `ClusterPrediction`, al file *IrisData.cs*:

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

`IrisData` è la classe dei dati di input e contiene le definizioni per ogni caratteristica del set di dati. Usare l'attributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) per specificare gli indici delle colonne di origine nel file del set di dati.

La classe `ClusterPrediction` rappresenta l'output del modello di clustering applicato a un'istanza `IrisData`. Usare l'attributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) per associare i campi `PredictedClusterId` e `Distances` rispettivamente alle colonne **PredictedLabel** e **Score**. In caso di attività di clustering, queste colonne hanno il significato seguente:

- La colonna **PredictedLabel** include l'ID del cluster stimato.
- La colonna **Score** contiene una matrice con le distanze Euclidee quadrate rispetto ai centroidi del cluster. La lunghezza della matrice è uguale al numero di cluster.

> [!NOTE]
> Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.

## <a name="define-data-and-model-paths"></a>Definire i percorsi dei dati e del modello

Tornare al file *Program.cs* e aggiungere due campi per i percorsi del file dei set di dati e del file per il salvataggio del modello:

- `_dataPath` contiene il percorso del file con il set di dati usato per il training del modello.
- `_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.

Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi:

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

Per consentire la compilazione del codice precedente, aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a>Creare una pipeline di apprendimento

Aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

Nel metodo `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

Il metodo `Train` esegue il training del modello. Creare il metodo subito sotto il metodo `Main` usando il codice seguente:

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello. Aggiungere nel metodo `Train` il codice seguente:

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a>Caricare e trasformare i dati

Il primo passaggio da eseguire consiste nel caricare il set di dati del training. Nel caso di questo esempio il training set è archiviato nel file di testo con un percorso definito dal campo `_dataPath`. Le colonne nel file sono separate da una virgola (","). Aggiungere nel metodo `Train` il codice seguente:

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

Il passaggio successivo combina tutte le colonne delle caratteristiche nella colonna **Features** usando la classe di trasformazione <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>. Per impostazione predefinita, un algoritmo di apprendimento elabora solo le caratteristiche della colonna **Features**. Aggiungere il codice seguente:

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**. L'algoritmo di apprendimento esegue il training del modello. ML.NET fornisce un algoritmo di apprendimento <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> che implementa l'[algoritmo k-means](https://en.wikipedia.org/wiki/K-means_clustering) con un metodo migliorato per la scelta dei centroidi del cluster iniziale.

Aggiungere il codice seguente nel metodo `Train` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

Usare la proprietà <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> per specificare il numero di cluster. Il codice precedente specifica che il set di dati deve essere suddiviso in tre cluster.

## <a name="train-the-model"></a>Eseguire il training del modello

I passaggi aggiunti nelle sezioni precedenti hanno preparato la pipeline per il training, che tuttavia non è stato eseguito. Il metodo `pipeline.Train<TInput, TOutput>` produce il modello che accetta un'istanza del tipo `TInput` e restituisce un'istanza del tipo `TOutput`. Aggiungere nel metodo `Train` il codice seguente:

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a>Salvare il modello

A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti. Per salvare il modello in un file con estensione zip, aggiungere il codice seguente al metodo `Main` sotto la chiamata al metodo `Train`:

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

L'uso di `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

È anche necessario aggiungere la direttiva `using` seguente all'inizio del file *Program.cs*:

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

Poiché il metodo `async Main` è la funzionalità aggiunta in C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva. A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime

Creare la classe `TestIrisData` per ospitare le istanze dei dati di test:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestIrisData.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Modificare la classe in modo da renderla statica, come nell'esempio seguente:

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

Questa esercitazione presenta un'istanza di dati iris all'interno di questa classe. È possibile aggiungere altri scenari da sperimentare con il modello. Aggiungere il codice seguente nella classe `TestIrisData`:

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

Per individuare il cluster a cui appartiene l'elemento specificato, tornare al file *Program.cs* e aggiungere il codice seguente nel metodo `Main`:

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

Eseguire il programma per vedere quale cluster contiene l'istanza dati specificata e le distanze al quadrato da tale istanza ai centroidi del cluster. I risultati dovrebbero essere simili a quanto riportato di seguito. Mentre la pipeline viene elaborata, potrebbe visualizzare avvisi o elaborare messaggi. Questi elementi sono stati rimossi dall'output seguente per maggiore chiarezza.

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

La procedura è stata completata. È stato creato un modello di apprendimento automatico per il clustering iris, quindi il modello è stato usato per produrre stime. È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> - Informazioni sul problema
> - Selezionare l'attività di apprendimento automatico appropriata
> - Preparare i dati
> - Caricare e trasformare i dati
> - Scegliere un algoritmo di apprendimento
> - Eseguire il training del modello
> - Usare il modello per le stime

Visitare il repository GitHub per ottenere altre informazioni ed esempi.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/)
