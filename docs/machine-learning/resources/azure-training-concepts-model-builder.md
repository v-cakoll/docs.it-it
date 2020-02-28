---
title: Risorse di formazione di Azure per generatore di modelli
description: Guida alle risorse per Azure Machine Learning
ms.topic: reference
ms.date: 02/25/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: a0a75283cdc7402c67b6bfb0799189fa34cd39a7
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "77675205"
---
# <a name="model-builder-azure-training-resources"></a>Risorse di formazione di Azure per generatore di modelli

Di seguito è riportata una guida che consente di ottenere altre informazioni sulle risorse usate per eseguire il training dei modelli in Azure con generatore di modelli.

## <a name="what-is-an-azure-machine-learning-experiment"></a>Che cos'è un esperimento di Azure Machine Learning?

Un esperimento di Azure Machine Learning è una risorsa che è necessario creare prima di eseguire il training del generatore di modelli in Azure.

L'esperimento incapsula la configurazione e i risultati per una o più esecuzioni di training di machine learning. Gli esperimenti appartengono a un'area di lavoro specifica. La prima volta che si crea un esperimento, il relativo nome viene registrato nell'area di lavoro. Tutte le esecuzioni successive: se viene usato lo stesso nome di esperimento, vengono registrate come parte dello stesso esperimento. In caso contrario, viene creato un nuovo esperimento.

## <a name="what-is-an-azure-machine-learning-workspace"></a>Che cos'è un'area di lavoro Azure Machine Learning?

Un'area di lavoro è una risorsa Azure Machine Learning che fornisce una posizione centrale per tutte le risorse Azure Machine Learning e gli artefatti creati come parte dell'esecuzione del training.

Per creare un'area di lavoro di Azure Machine Learning, sono necessari gli elementi seguenti:

- Nome: nome dell'area di lavoro compreso tra 3-33 caratteri. I nomi possono contenere solo caratteri alfanumerici e trattini. 
- Region: la posizione geografica del data center in cui sono distribuite le risorse e l'area di lavoro. Si consiglia di scegliere una località vicina a quella in cui si trovano i clienti.
- Gruppo di risorse: contenitore che contiene tutte le risorse correlate per una soluzione di Azure.

## <a name="what-is-an-azure-machine-learning-compute"></a>Che cos'è un calcolo Azure Machine Learning?

Un calcolo Azure Machine Learning è una macchina virtuale Linux basata sul cloud usata per il training.

Per creare un'area di lavoro di Azure Machine Learning, sono necessari gli elementi seguenti:

- Nome: nome dell'area di lavoro compreso tra 2-16 caratteri. I nomi possono contenere solo caratteri alfanumerici e trattini.
- Dimensioni di calcolo

    Il generatore di modelli può usare uno dei tipi di calcolo ottimizzati per GPU seguenti:

    | Dimensione | vCPU | Memoria: GiB | GiB di archiviazione temp (unità SSD) | GPU | Memoria GPU: GiB | Numero massimo di dischi dati | Schede di interfaccia di rete max |
    |---|---|---|---|---|---|---|---|
    | Standard_NC12   | 12 | 112 | 680  | 2 | 24 | 48 | 2 |
    | Standard_NC24   | 24 | 224 | 1440 | 4 | 48 | 64 | 4 |

    Per altri dettagli sui tipi di calcolo ottimizzati per GPU, vedere la [documentazione della VM Linux della serie NC](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json) .

## <a name="training"></a>Formazione

Il training in Azure è disponibile solo per lo scenario di classificazione delle immagini del generatore di modelli. L'algoritmo usato per il training di questi modelli è una rete neurale profonda basata sull'architettura ResNet50. Durante il training, viene effettuato il provisioning delle risorse necessarie per eseguire il training del modello e viene eseguito il training del modello. Questo processo richiede alcuni minuti e la quantità di tempo può variare a seconda delle dimensioni del calcolo selezionato e della quantità di dati. È possibile tenere traccia dello stato di avanzamento delle esecuzioni selezionando il collegamento "monitora esecuzione corrente in portale di Azure" in Visual Studio.

## <a name="results"></a>Risultati

Al termine del training, verranno aggiunti due progetti alla soluzione con i suffissi seguenti:

- *ConsoleApp*: applicazione C# console .NET Core che fornisce il codice di avvio per compilare la pipeline di stima ed eseguire stime.
- *Modello*: un' C# applicazione .NET standard che contiene i modelli di dati che definiscono lo schema dei dati del modello di input e di output, nonché gli asset seguenti:

  - bestModel. Onnx: una versione serializzata del modello nel formato Open Neural Network Exchange (ONNX). ONNX è un formato Open Source per i modelli di intelligenza artificiale che supporta l'interoperabilità tra Framework come ML.NET, PyTorch e TensorFlow.
  - bestModelMap. JSON: elenco di categorie utilizzate per eseguire stime per eseguire il mapping dell'output del modello a una categoria di testo.
  - MLModel. zip: una versione serializzata della pipeline di stima ML.NET che utilizza la versione serializzata del modello *bestModel. Onnx* per eseguire stime ed eseguire il mapping degli output utilizzando il file di `bestModelMap.json`.
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="cannot-create-compute"></a>Non è possibile creare il calcolo

Se si verifica un errore durante la creazione di Azure Machine Learning calcolo, è possibile che la risorsa di calcolo esista ancora, in uno stato di errore. Se si tenta di ricreare la risorsa di calcolo con lo stesso nome, l'operazione non riesce. Per correggere l'errore, eseguire una delle operazioni seguenti:

* Crea il nuovo calcolo con un nome diverso
* Passare alla portale di Azure e rimuovere la risorsa di calcolo originale
