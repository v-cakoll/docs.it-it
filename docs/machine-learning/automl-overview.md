---
title: Machine Learning automatizzato con ML.NET
description: Panoramica sulla selezione e il training automatici del modello
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: da2d764e678debc78a25faeb8e48facb44fc4021
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929418"
---
# <a name="automated-machine-learning-with-mlnet"></a>Machine Learning automatizzato con ML.NET

Il Machine Learning automatizzato è una funzionalità di ML.NET che esegue la selezione e il training automatici del modello. Dopo aver specificato l'attività di Machine Learning e un set di dati, il Machine Learning automatizzato sceglie il modello con le metriche migliori. Vengono generati:

- un file di modello che può essere caricato nell'applicazione di previsione
- il codice dell'applicazione per eseguire previsioni
- il codice sorgente usato per la selezione delle caratteristiche e il training del modello (per comprendere il modello)

> [!NOTE]
> Questa funzionalità è attualmente in anteprima e il materiale può essere soggetto a modifiche. 

Il Machine Learning automatizzato è attualmente limitato alle [attività](resources/tasks.md) di Machine Learning di classificazione binaria, classificazione multiclasse e regressione. Le altre attività di Machine Learning saranno supportate nelle versioni future.

Il Machine Learning automatizzato può essere usato in tre modi:

1. Con un'interfaccia utente grafica con il [generatore di modelli di ML.NET](automate-training-with-model-builder.md)
1. Nella riga di comando con l'[interfaccia della riga di comando di ML.NET](automate-training-with-cli.md)
1. Tramite un'applicazione con l'[API di Machine Learning automatizzato](how-to-guides/how-to-use-the-automl-api.md)
