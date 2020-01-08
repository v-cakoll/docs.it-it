---
title: 'Esercitazione: classificare le violazioni di integrità con il generatore di modelli'
description: Questa esercitazione illustra come creare un modello di classificazione multiclasse usando il generatore di modelli ML.NET per classificare la gravità della violazione dell'integrità del ristorante a San Francisco.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 90abbc9ffe5765880d18d0d29c8e13bc1330ddc3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341563"
---
# <a name="tutorial-classify-the-severity-of-restaurant-health-violations-with-model-builder"></a>Esercitazione: classificare la gravità delle violazioni di integrità del ristorante con generatore di modelli

Informazioni su come creare un modello di classificazione multiclasse usando generatore di modelli per categorizzare il livello di rischio delle violazioni del ristorante trovate durante i controlli di integrità.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare dati da un database
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="prerequisites"></a>Prerequisiti

Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione di generatore di modelli](../how-to-guides/install-model-builder.md).

## <a name="model-builder-multiclass-classification-overview"></a>Panoramica della classificazione multiclasse del generatore di modelli

Questo esempio crea un' C# applicazione console .NET Core che categorizza il rischio di violazioni di integrità usando un modello di Machine Learning compilato con il generatore di modelli. Il codice sorgente per questa esercitazione è reperibile nel repository GitHub [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) .

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'  **C# applicazione console .NET Core** denominata "RestaurantViolations". Assicurarsi che **la posizione della soluzione e del progetto nella stessa directory** sia **deselezionata** (vs 2019) oppure che sia **selezionata** l'opzione **Crea directory per soluzione** (vs 2017).

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

> Il set di dati usato per il training e la valutazione del modello di Machine Learning è stato originato dal [reparto San Francisco dei punteggi di sicurezza del ristorante Public Health](https://www.sfdph.org/dph/EH/Food/score/default.asp). Per praticità, il set di dati è stato condensato in modo da includere solo le colonne rilevanti per eseguire il training del modello ed eseguire stime. Visitare il sito Web seguente per altre informazioni sul [set di dati](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i?row_index=0).

[Scaricare il set di dati dei punteggi di sicurezza del ristorante](https://github.com/luisquintanilla/machinelearning-samples/raw/AB1608219/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantScores.zip) e decomprimerlo.

Ogni riga del set di dati contiene informazioni relative alle violazioni osservate durante un'ispezione dal reparto integrità e una valutazione dei rischi della minaccia che tali violazioni presentano alla salute e alla sicurezza pubbliche.

| InspectionType | ViolationDescription | RiskCategory |
| --- | --- | --- |
| Routine-non pianificata | Superficie di contatto cibo pulita o purificata in modo non adeguato | Rischio moderato |
| Nuova proprietà | Rischio elevato | Rischio elevato |
| Routine-non pianificata | Cancellazione di panni non puliti o archiviati in modo appropriato o igienizzatore inadeguato | Rischio basso |

- **InspectionType**: il tipo di controllo. Questo può essere un primo controllo per un nuovo stabilimento, un'ispezione di routine, un'ispezione di reclamo e molti altri tipi.
- **ViolationDescription**: Descrizione della violazione trovata durante l'ispezione.
- **RiskCategory**: la gravità del rischio rappresenta una violazione per l'integrità e la sicurezza pubbliche.

`label` è la colonna sulla quale eseguire le stime. Quando si esegue un'attività di classificazione, l'obiettivo consiste nell'assegnare una categoria (testo o numerico). In questo scenario di classificazione, alla gravità della violazione viene assegnato il valore di basso, medio o alto rischio. Di conseguenza, **RiskCategory** è l'etichetta. Il `features` sono gli input da assegnare al modello per stimare l'`label`. In questo caso, **InspectionType** e **ViolationDescription** vengono usati come funzionalità o input per stimare il **RiskCategory**.

## <a name="choose-a-scenario"></a>Scegliere uno scenario

![Creazione guidata generatore di modelli in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Per eseguire il training del modello, selezionare nell'elenco degli scenari di machine learning disponibili forniti da generatore di modelli. In questo caso, lo scenario è la *classificazione dei problemi*.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *RestaurantViolations* e selezionare **Aggiungi** > **Machine Learning**.
1. Per questo esempio, lo scenario è la classificazione multiclasse. Nel passaggio dello *scenario* di generatore di modelli selezionare lo scenario di **classificazione dei problemi** .

## <a name="load-the-data"></a>Caricare i dati

Il generatore di modelli accetta dati da un database SQL Server o da un file locale in formato `csv` o `tsv`.

1. Nel passaggio dati dello strumento generatore di modelli selezionare **SQL Server** dall'elenco a discesa origine dati.
1. Selezionare il pulsante accanto alla casella di testo **Connetti a SQL Server database** .
    1. Nella finestra di dialogo **Scegli dati** selezionare **Microsoft SQL Server file di database**.
    1. Deselezionare la casella di controllo **Usa sempre questa selezione** e selezionare **continua**.
    1. Nella finestra di dialogo **Proprietà connessione** selezionare **Sfoglia** e selezionare il file *RestaurantScores. MDF* scaricato.
    1. Scegliere **OK**.
1. Scegliere **violazioni** dall'elenco a discesa **nome tabella** .
1. Scegliere **RiskCategory** nell'elenco **a discesa colonna da stimare (etichetta)** .
1. Lasciare le selezioni di colonna predefinite, **InspectionType** e **ViolationDescription**, archiviate nell'elenco a discesa **colonne di input (funzionalità)** .
1. Selezionare il collegamento **Train (Train** ) per passare al passaggio successivo in Generatore di modelli.

## <a name="train-the-model"></a>Eseguire il training del modello

L'attività di Machine Learning usata per eseguire il training del modello di classificazione dei problemi in questa esercitazione è la classificazione multiclasse. Durante il processo di training del modello, generatore di modelli esegue il training di modelli distinti usando diversi algoritmi di classificazione multiclasse e impostazioni per trovare il modello di prestazioni migliori per il set di dati.

Il tempo necessario per il training del modello è proporzionale alla quantità di dati. Generatore di modelli seleziona automaticamente un valore predefinito per il **tempo di training (secondi)** in base alle dimensioni dell'origine dati.

1. Sebbene generatore di modelli imposti il valore di **tempo per il training (secondi)** su 10 secondi, aumentarlo a 30 secondi. Il training per un periodo di tempo più lungo consente a Generatore di modelli di esplorare un numero maggiore di algoritmi e una combinazione di parametri nella ricerca del modello migliore.
1. Selezionare **Start Training** (Avvia training).

    Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.

    - **Stato** consente di visualizzare lo stato di completamento del processo di training.
    -  **accuratezza ottimale** Visualizza l'accuratezza del modello con le prestazioni migliori rilevato finora dal generatore di modelli. Precisione maggiore indica il modello stimato più correttamente con i dati di test.
    - **Best algorithm** Visualizza il nome dell'algoritmo con le prestazioni migliori trovato finora dal generatore di modelli.
    - **Last algorithm** Visualizza il nome dell'algoritmo utilizzato più di recente dal generatore di modelli per eseguire il training del modello.

1. Al termine del training, selezionare il collegamento **Evaluate (valuta** ) per passare al passaggio successivo.

## <a name="evaluate-the-model"></a>Valutare il modello

Il risultato del passaggio di training è quello che ha ottenuto le prestazioni migliori. Nel passaggio Evaluate di generatore di modelli, la sezione output contiene l'algoritmo utilizzato dal modello con le migliori prestazioni nella **migliore** voce del modello insieme alle metriche nell' **accuratezza del modello migliore**. Viene inoltre visualizzata una tabella riepilogativa contenente fino a cinque modelli esplorati e le relative metriche.

Se non si è soddisfatti della metrica di accuratezza, è possibile provare a migliorare l'accuratezza del modello aumentando il tempo necessario per il training del modello o l'utilizzo di più dati. In caso contrario, selezionare il collegamento al **codice** per passare al passaggio finale in Generatore di modelli.

## <a name="add-the-code-to-make-predictions"></a>Aggiungere il codice per eseguire stime

Due progetti vengono creati in seguito al processo di training.

- RestaurantViolationsML. ConsoleApp: applicazione C# console .NET Core che contiene il codice di training e di utilizzo del modello di esempio.
- RestaurantViolationsML. Model: una libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del modello di input e di output, la versione salvata del modello con le prestazioni migliori durante il training e una classe helper denominata `ConsumeModel` per eseguire stime.

1. Nel passaggio del codice del generatore di modelli selezionare **Aggiungi progetti** per aggiungere i progetti generati automaticamente alla soluzione.
1. Aprire il file *Program.cs* nel progetto *RestaurantViolations* .
1. Aggiungere l'istruzione using seguente per fare riferimento al progetto *RestaurantViolationsML. Model* :

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L2)]

1. Per eseguire una stima sui nuovi dati utilizzando il modello, creare una nuova istanza della classe `ModelInput` all'interno del metodo `Main` dell'applicazione. Si noti che la categoria di rischio non fa parte dell'input. Questo perché il modello genera la stima per l'oggetto.

    [!code-csharp [TestData](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L11-L15)]

1. Usare il metodo `Predict` dalla classe `ConsumeModel`. Il metodo `Predict` carica il modello sottoposto a training, crea una [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) per il modello e la utilizza per eseguire stime sui nuovi dati.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L17-L24)]

1. Eseguire l'applicazione.

    L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:

    ```bash
    Inspection Type: Complaint
    Violation Description: Inadequate sewage or wastewater disposal
    Risk Category: Moderate Risk
    ```

Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

La procedura è stata completata. È stato creato un modello di apprendimento automatico per suddividere in categorie il rischio di violazioni di integrità mediante generatore di modelli. Il codice sorgente per questa esercitazione è reperibile nel repository GitHub [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) .

## <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:

- [Scenari del generatore di modelli](../automate-training-with-model-builder.md#scenarios)
- [Classificazione multiclasse](../resources/glossary.md#multiclass-classification)
- [Metriche del modello di classificazione multiclasse](../resources/metrics.md#evaluation-metrics-for-multi-class-classification)
