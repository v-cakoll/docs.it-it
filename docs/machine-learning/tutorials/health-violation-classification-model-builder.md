---
title: 'Esercitazione: Classificare le violazioni di integrità con Model BuilderTutorial: Classify health violations with Model Builder'
description: Questa esercitazione illustra come creare un modello di classificazione multiclasse usando ML.NET Model Builder per classificare la gravità della violazione dell'integrità del ristorante a San Francisco.This tutorial illustrates how to build a multiclass classification model using ML.NET Model Builder to classify restaurant health violation severity in San Francisco.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: e94313277a025d482105a6d78b6608d4df442c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185853"
---
# <a name="tutorial-classify-the-severity-of-restaurant-health-violations-with-model-builder"></a>Esercitazione: Classificare la gravità delle violazioni di integrità del ristorante con Model BuilderTutorial: Classify the severity of restaurant health violations with Model Builder

Informazioni su come creare un modello di classificazione multiclasse utilizzando Model Builder per classificare il livello di rischio delle violazioni dei ristoranti rilevate durante le ispezioni sanitarie.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare dati da un databaseLoad data from a database
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

## <a name="prerequisites"></a>Prerequisites

Per un elenco dei prerequisiti e delle istruzioni di installazione, visitare la [guida all'installazione](../how-to-guides/install-model-builder.md)di Model Builder .

## <a name="model-builder-multiclass-classification-overview"></a>Panoramica della classificazione multiclasse di Model Builder

In questo esempio viene creata un'applicazione console di .NET Core di C. che classifica il rischio di violazioni dell'integrità usando un modello di apprendimento automatico compilato con Model Builder.This sample creates a C.NET Core console application that categorizes the risk of health violations using a machine learning model built with Model Builder. È possibile trovare il codice sorgente per questa esercitazione nel repository [GitHub dotnet/machinelearning-samples.](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations)

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare **un'applicazione console di C .NET Core** denominata "RestaurantViolations". Assicurarsi che **l'opzione Inserisci soluzione e progetto nella stessa directory** sia **deselezionata** (VS 2019) o **l'opzione Crea directory per soluzione** sia **selezionata** (VS 2017).

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

> Il set di dati utilizzato per addestrare e valutare il modello di apprendimento automatico è originariamente del Dipartimento di San Francisco dei punteggi di sicurezza del [ristorante della sanità pubblica.](https://www.sfdph.org/dph/EH/Food/score/default.asp) Per comodità, il set di dati è stato condensato per includere solo le colonne rilevanti per eseguire il training del modello ed eseguire stime. Visitare il seguente sito Web per ulteriori informazioni sul [set di dati](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i?row_index=0).

[Scaricare il set](https://github.com/luisquintanilla/machinelearning-samples/raw/AB1608219/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantScores.zip) di dati Restaurant Safety Scores e decomprimerlo.

Ogni riga del set di dati contiene informazioni relative alle violazioni osservate durante un'ispezione da parte del Dipartimento della salute e una valutazione del rischio della minaccia che tali violazioni presentano alla salute e alla sicurezza pubblica.

| IspezioneTipo | ViolazioneDescrizione | Categoria Rischio |
| --- | --- | --- |
| Routine - Non pianificato | Superfici di contatto degli alimenti non adeguatamente pulite o igienizzate | Rischio moderato |
| Nuova proprietà | Infestazione di parassiti ad alto rischio | Alto rischio |
| Routine - Non pianificato | Pulire i tessuti non puliti o correttamente conservati o disinadeguato | Basso rischio |

- **InspectionType**: il tipo di ispezione. Questa può essere un'ispezione per la prima volta per un nuovo stabilimento, un'ispezione di routine, un'ispezione dei reclami e molti altri tipi.
- **ViolationDescription**: una descrizione della violazione rilevata durante l'ispezione.
- **RiskCategory**: la gravità del rischio che una violazione pone alla salute e alla sicurezza pubblica.

`label` è la colonna sulla quale eseguire le stime. Quando si esegue un'attività di classificazione, l'obiettivo è assegnare una categoria (testo o numerica). In questo scenario di classificazione, alla gravità della violazione viene assegnato il valore di rischio basso, moderato o elevato. Pertanto, il **RiskCategory** è l'etichetta. Gli `features` input vengono dati al modello `label`per stimare il file . In questo caso, **InspectionType** e **ViolationDescription** vengono utilizzati come feature o input per stimare **RiskCategory**.

## <a name="choose-a-scenario"></a>Scegliere uno scenario

![Creazione guidata Generatore di modelli in Visual StudioModel Builder wizard in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Per eseguire il training del modello, selezionare dall'elenco degli scenari di apprendimento automatico disponibili fornito da Model Builder.To train your model, select from the list of available machine learning scenarios provided by Model Builder. In questo caso, lo scenario è *Classificazione dei problemi*.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *RestaurantViolations* e scegliere **Aggiungi** > **Machine Learning**.
1. Per questo esempio, lo scenario è la classificazione multiclasse. Nel passaggio *Scenario* di Model Builder selezionare lo scenario **Di classificazione dei problemi.**

## <a name="load-the-data"></a>Caricare i dati

Model Builder accetta dati da un database di `csv` `tsv` SQL ServerSQL Server o da un file locale in formato o in formato.

1. Nel passaggio dati dello strumento Generatore di modelli selezionare **SQL Server** dall'elenco a discesa dell'origine dati.
1. Selezionare il pulsante accanto alla casella di testo **Connetti al database sql Server.**
    1. Nella finestra di dialogo **Scegli dati** selezionare File di database di Microsoft **SQL Server**.
    1. Deselezionare la casella di controllo **Usa sempre questa selezione** e selezionare **Continua**.
    1. Nella finestra di dialogo **Proprietà connessione** selezionare **Sfoglia** e selezionare il file *RestaurantScores.mdf* scaricato.
    1. Selezionare **OK**.
1. Scegliere **Violazioni** dall'elenco a discesa **Nome tabella.**
1. Scegliere **RiskCategory** nell'elenco a discesa **Colonna da stimare (etichetta).**
1. Lasciare selezionata la selezione predefinita delle colonne, **InspectionType** e **ViolationDescription**, selezionata nell'elenco a discesa **Colonne di input (funzionalità).**
1. Selezionare il collegamento **Allenatore** per passare al passaggio successivo in Generatore di modelli.

## <a name="train-the-model"></a>Eseguire il training del modello

L'attività di apprendimento automatico usata per eseguire il training del modello di classificazione dei problemi in questa esercitazione è la classificazione multiclasse. Durante il processo di training del modello, Model Builder esegue il training di modelli separati utilizzando algoritmi e impostazioni di classificazione multiclasse diversi per trovare il modello con le prestazioni migliori per il set di dati.

Il tempo necessario per il training del modello è proporzionale alla quantità di dati. Model Builder seleziona automaticamente un valore predefinito per **Time to train (seconds)** in base alle dimensioni dell'origine dati.

1. Anche se Model Builder imposta il valore di **Time to train (secondi)** su 10 secondi, aumentarlo a 30 secondi. Il training per un periodo di tempo più lungo consente a Model Builder di esplorare un numero maggiore di algoritmi e una combinazione di parametri alla ricerca del modello migliore.
1. Selezionare **Start Training** (Avvia training).

    Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.

    - **Stato** visualizza lo stato di completamento del processo di formazione.
    - **La migliore precisione** mostra la precisione del modello con le migliori prestazioni trovato finora da Model Builder. Precisione maggiore indica il modello stimato più correttamente con i dati di test.
    - **L'algoritmo migliore** visualizza il nome dell'algoritmo con le prestazioni migliori trovato finora da Model Builder.
    - **L'ultimo algoritmo** visualizza il nome dell'algoritmo utilizzato più di recente da Model Builder per eseguire il training del modello.

1. Una volta completato l'allenamento, selezionare il collegamento **Valuta** per passare al passaggio successivo.

## <a name="evaluate-the-model"></a>Valutare il modello

Il risultato del passaggio di training è l'unico modello che ha prestazioni migliori. Nel passaggio di valutazione di Model Builder, la sezione di output contiene l'algoritmo utilizzato dal modello con le migliori prestazioni nella voce **Best Model** insieme alle metriche in Best **Model Accuracy**. Inoltre, viene visualizzata una tabella di riepilogo contenente fino a cinque modelli esplorati e le relative metriche.

Se non si è soddisfatti delle metriche di accuratezza, alcuni modi semplici per cercare di migliorare l'accuratezza del modello sono per aumentare la quantità di tempo per eseguire il training del modello o usare più dati. In caso contrario, selezionare il collegamento al **codice** per passare al passaggio finale in Model Builder.Otherwise, select the code link to move to the final step in Model Builder.

## <a name="add-the-code-to-make-predictions"></a>Aggiungere il codice per eseguire stime

Due progetti sono stati creati come risultato del processo di formazione.

- RestaurantViolationsML.ConsoleApp: un'applicazione console di .NET Core di C.NET che contiene il training del modello e il codice di consumo di esempio.
- RestaurantViolationsML.Model: libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del `ConsumeModel` modello di input e di output, la versione salvata del modello con le prestazioni migliori durante il training e una classe helper chiamata per eseguire stime.

1. Nel passaggio di codice di Generatore di modelli selezionare **Aggiungi progetti** per aggiungere i progetti generati automaticamente alla soluzione.
1. Aprire il file *Program.cs* nel progetto *RestaurantViolations.*
1. Aggiungere la seguente istruzione using per fare riferimento al progetto *RestaurantViolationsML.Model:*

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L2)]

1. Per eseguire una stima dei nuovi dati usando il `ModelInput` modello, `Main` creare una nuova istanza della classe all'interno del metodo dell'applicazione. Si noti che la categoria di rischio non fa parte dell'input. Ciò è dovuto al fatto che il modello genera la stima per tale modello.

    [!code-csharp [TestData](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L11-L15)]

1. Utilizzare `Predict` il metodo `ConsumeModel` della classe . Il `Predict` metodo carica il modello [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) sottoposto a training, crea un per il modello e lo usa per eseguire stime sui nuovi dati.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L17-L24)]

1. Eseguire l'applicazione.

    L'output generato dal programma dovrebbe essere simile al frammento di codice seguente:

    ```bash
    Inspection Type: Complaint
    Violation Description: Inadequate sewage or wastewater disposal
    Risk Category: Moderate Risk
    ```

Se in un secondo momento è necessario fare riferimento ai progetti generati all'interno di un'altra soluzione, è possibile trovarli all'interno della directory `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

Congratulazioni! È stato creato correttamente un modello di apprendimento automatico per classificare il rischio di violazioni di integrità tramite Model Builder.You've successfully built a machine learning model to categorize the risk of health violations using Model Builder. È possibile trovare il codice sorgente per questa esercitazione nel repository [GitHub dotnet/machinelearning-samples.](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations)

## <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:

- [Scenari del generatore di modelli](../automate-training-with-model-builder.md#scenarios)
- [Classificazione multiclasse](../resources/glossary.md#multiclass-classification)
- [Metriche del modello di classificazione multiclasseMulticlass Classification Model Metrics](../resources/metrics.md#evaluation-metrics-for-multi-class-classification)
