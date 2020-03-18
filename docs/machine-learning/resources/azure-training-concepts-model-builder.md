---
title: Risorse per la formazione di Azure per Il Generatore di modelliModel Builder Azure Training Resources
description: Guida alle risorse per Azure Machine Learning
ms.topic: reference
ms.date: 02/27/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: a19e13955d0eaea344109eb817f3a3959c3dd883
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185815"
---
# <a name="model-builder-azure-training-resources"></a>Risorse per la formazione di Azure per Il Generatore di modelliModel Builder Azure Training Resources

Di seguito è riportata una guida che illustra altre informazioni sulle risorse usate per eseguire il training dei modelli in Azure con Model Builder.The following is a guide to help you learn more about resources used to train models in Azure with Model Builder.

## <a name="what-is-an-azure-machine-learning-experiment"></a>Che cos'è un esperimento di Azure Machine Learning?

Un esperimento di Azure Machine Learning è una risorsa che deve essere creata prima di eseguire il training di Model Builder in Azure.An Azure Machine Learning experiment is a resource that needs to be created before running Model Builder training on Azure.

L'esperimento incapsula la configurazione e i risultati per una o più esecuzioni di training di apprendimento automatico. Gli esperimenti appartengono a un'area di lavoro specifica. La prima volta che viene creato un esperimento, il suo nome viene registrato nell'area di lavoro. Tutte le esecuzioni successive, se viene utilizzato lo stesso nome dell'esperimento, vengono registrate come parte dello stesso esperimento. In caso contrario, viene creato un nuovo esperimento.

## <a name="what-is-an-azure-machine-learning-workspace"></a>Che cos'è un'area di lavoro di Azure Machine Learning?

Un'area di lavoro è una risorsa di Azure Machine Learning che fornisce una posizione centrale per tutte le risorse e gli elementi di Azure Machine Learning creati durante l'esecuzione del training.

Per creare un'area di lavoro di Azure Machine Learning, sono necessari gli elementi seguenti:To create an Azure Machine Learning workspace, the following are required:

- Nome: un nome per l'area di lavoro compreso tra 3 e 33 caratteri. I nomi possono contenere solo caratteri alfanumerici e trattini.
- Area geografica: la posizione geografica del data center in cui vengono distribuite l'area di lavoro e le risorse. Si consiglia di scegliere una posizione vicina a dove si trovano voi o i vostri clienti.
- Gruppo di risorse: un contenitore che contiene tutte le risorse correlate per una soluzione Azure.Resource group: A container that contains all related resources for an Azure solution.

## <a name="what-is-an-azure-machine-learning-compute"></a>Che cos'è un calcolo di Azure Machine Learning?

Un calcolo di Azure Machine Learning è una macchina virtuale Linux basata su cloud usata per il training.

Per creare un'area di lavoro di Azure Machine Learning, sono necessari gli elementi seguenti:To create an Azure Machine Learning workspace, the following are required:

- Nome: un nome per l'area di lavoro compreso tra 2 e 16 caratteri. I nomi possono contenere solo caratteri alfanumerici e trattini.
- Dimensioni di calcolo

    Model Builder può utilizzare uno dei seguenti tipi di calcolo ottimizzati per GPU:

    | Dimensione | vCPU | Memoria: GiB | GiB di archiviazione temp (unità SSD) | GPU | Memoria GPU: GiB | Numero massimo di dischi dati | Schede di interfaccia di rete max |
    |---|---|---|---|---|---|---|---|
    | Standard_NC12   | 12 | 112 | 680  | 2 | 24 | 48 | 2 |
    | Standard_NC24   | 24 | 224 | 1440 | 4 | 48 | 64 | 4 |

    Visitare la [documentazione](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json) della macchina virtuale Linux serie NC per ulteriori dettagli sui tipi di calcolo ottimizzati Per GPU.

## <a name="training"></a>Formazione

La formazione in Azure è disponibile solo per lo scenario di classificazione delle immagini di Model Builder.Training on Azure is only available for the Model Builder image classification scenario. L'algoritmo utilizzato per eseguire il training di questi modelli è una rete neurale profonda basata sull'architettura ResNet50.The algorithm used to train these models is a Deep Neural Network based on the ResNet50 architecture. Il processo di training richiede un certo tempo e la quantità di tempo può variare a seconda delle dimensioni del calcolo selezionato e della quantità di dati. La prima volta che viene eseguito il training di un modello, è possibile prevedere un tempo di formazione leggermente più lungo perché è necessario eseguire il provisioning delle risorse. È possibile tenere traccia dello stato di avanzamento delle esecuzioni selezionando il collegamento "Monitora l'esecuzione corrente nel portale di Azure" in Visual Studio.You can track the progress of your runs by selecting the "Monitor current run in Azure portal" link in Visual Studio.

## <a name="results"></a>Risultati

Al termine della formazione, alla soluzione vengono aggiunti due progetti con i suffissi seguenti:Once training is complete, two projects are added to your solution with the following suffixes:

- *ConsoleApp*: Un'applicazione console di C .NET Core che fornisce il codice iniziale per compilare la pipeline di stima ed eseguire stime.
- *Modello*: Un'applicazione .NET Standard di C .NET che contiene i modelli di dati che definiscono lo schema dei dati del modello di input e di output, nonché gli asset seguenti:

  - bestModel.onnx: versione serializzata del modello in formato ONNX (Open Neural Network Exchange). ONNX è un formato open source per i modelli Di IA che supporta l'interoperabilità tra framework come ML.NET, PyTorch e TensorFlow.
  - bestModelMap.json: elenco di categorie utilizzate durante l'esecuzione di stime per eseguire il mapping dell'output del modello a una categoria di testo.BestModelMap.json: A list of categories used when making predictions to map the model output to a text category.
  - MLModel.zip: una versione serializzata della pipeline di stima ML.NET che utilizza la versione serializzata del modello *bestModel.onnx* per eseguire stime ed eseguire il mapping degli output usando il `bestModelMap.json` file.

## <a name="use-the-machine-learning-model"></a>Usare il modello di apprendimento automaticoUse the machine learning model

Le `ModelInput` `ModelOutput` classi e nel progetto *Model* definiscono lo schema rispettivamente dell'input e dell'output previsti del modello.

In uno scenario di `ModelInput` classificazione delle immagini, il contiene due colonne:In an image classification scenario, the contains two columns:

- `ImageSource`: il percorso della stringa della posizione dell'immagine.
- `Label`: la categoria effettiva a cui appartiene l'immagine. `Label`viene utilizzato solo come input durante l'allenamento e non deve essere fornito quando si effettuano previsioni.

Il `ModelOutput` contiene due colonne:

- `Prediction`: categoria prevista dell'immagine.
- `Score`: l'elenco delle probabilità per tutte le `Prediction`categorie (il più alto appartiene al ).

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="cannot-create-compute"></a>Impossibile creare il calcolo

Se si verifica un errore durante la creazione del calcolo di Azure Machine Learning, la risorsa di calcolo potrebbe essere ancora presente, in uno stato con errori. Se si tenta di ricreare la risorsa di calcolo con lo stesso nome, l'operazione non riesce. Per correggere l'errore, eseguire una delle operazioni seguenti:

- Creare il nuovo calcolo con un nome diversoCreate the new compute with a different name
- Passare al portale di Azure e rimuovere la risorsa di calcolo originale
