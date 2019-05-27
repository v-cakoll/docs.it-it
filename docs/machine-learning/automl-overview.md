---
title: Machine Learning automatizzato con ML.NET
description: Panoramica sulla selezione e il training automatici del modello
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: e6654718f174c9d8b628b05d85d74952c222eb66
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452736"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="02713-103">Machine Learning automatizzato con ML.NET</span><span class="sxs-lookup"><span data-stu-id="02713-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="02713-104">Il Machine Learning automatizzato è una funzionalità di ML.NET che esegue la selezione e il training automatici del modello.</span><span class="sxs-lookup"><span data-stu-id="02713-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="02713-105">Dopo aver specificato l'attività di Machine Learning e un set di dati, il Machine Learning automatizzato sceglie il modello con le metriche migliori.</span><span class="sxs-lookup"><span data-stu-id="02713-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="02713-106">Vengono generati:</span><span class="sxs-lookup"><span data-stu-id="02713-106">It outputs:</span></span>
- <span data-ttu-id="02713-107">un file di modello che può essere caricato nell'applicazione di previsione</span><span class="sxs-lookup"><span data-stu-id="02713-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="02713-108">il codice dell'applicazione per eseguire previsioni</span><span class="sxs-lookup"><span data-stu-id="02713-108">application code to make predictions</span></span>
- <span data-ttu-id="02713-109">il codice sorgente usato per la selezione delle caratteristiche e il training del modello (per comprendere il modello)</span><span class="sxs-lookup"><span data-stu-id="02713-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="02713-110">Questa funzionalità è attualmente in anteprima e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="02713-110">This feature is currently in Preview, and material may be subject to change.</span></span> 

<span data-ttu-id="02713-111">Il Machine Learning automatizzato è attualmente limitato alle [attività](resources/tasks.md) di Machine Learning di classificazione binaria, classificazione multiclasse e regressione.</span><span class="sxs-lookup"><span data-stu-id="02713-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="02713-112">Le altre attività di Machine Learning saranno supportate nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="02713-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="02713-113">Il Machine Learning automatizzato può essere usato in tre modi:</span><span class="sxs-lookup"><span data-stu-id="02713-113">There are three ways to use automated ML:</span></span>
1. <span data-ttu-id="02713-114">Nella riga di comando con l'[interfaccia della riga di comando di ML.NET](automate-training-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="02713-114">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="02713-115">Tramite un'applicazione con l'[API di Machine Learning automatizzato](how-to-guides/how-to-use-the-automl-api.md)</span><span class="sxs-lookup"><span data-stu-id="02713-115">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>
1. <span data-ttu-id="02713-116">Con un'interfaccia utente grafica con il generatore di modelli di ML.NET</span><span class="sxs-lookup"><span data-stu-id="02713-116">With a graphical user interface, with the the ML.NET Model Builder</span></span>
