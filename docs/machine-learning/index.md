---
title: Guida ai contenuti su ML.NET
description: Informazioni su come creare soluzioni di intelligenza artificiale personalizzate e integrarle nelle applicazioni .NET usando ML.NET.
ms.date: 04/05/2019
ms.custom: seodec18
ms.openlocfilehash: de681daea5a29a121d350271ced4ccc2c0b1b533
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231331"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="7a208-103">Guida ai contenuti su ML.NET</span><span class="sxs-lookup"><span data-stu-id="7a208-103">ML.NET Content Guide</span></span>

<span data-ttu-id="7a208-104">Questa guida illustra i concetti di base e fornisce esercitazioni e un riferimento all'API per usare ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7a208-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="7a208-105">Questa documentazione si riferisce a ML.NET, che è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="7a208-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="7a208-106">Il materiale potrà essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a208-106">Material may be subject to change.</span></span> <span data-ttu-id="7a208-107">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7a208-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="7a208-108">Introduzione</span><span class="sxs-lookup"><span data-stu-id="7a208-108">Get started</span></span>

<span data-ttu-id="7a208-109">Per eseguire l'installazione e iniziare a compilare in ML.NET, seguire l'[esercitazione introduttiva](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span><span class="sxs-lookup"><span data-stu-id="7a208-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="7a208-110">Per informazioni su ML.NET, vedere [Informazioni su ML.NET](what-is-mldotnet.md).</span><span class="sxs-lookup"><span data-stu-id="7a208-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="7a208-111">Per informazioni di base, vedere [Concetti fondamentali sul training dei modelli in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span><span class="sxs-lookup"><span data-stu-id="7a208-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="7a208-112">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="7a208-112">Tutorials</span></span>

<span data-ttu-id="7a208-113">L'esercitazione [Analizzare il sentiment usando un modello di classificazione binaria](./tutorials/sentiment-analysis.md) illustra come compilare un'app che determina se il sentiment è positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="7a208-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="7a208-114">[Classificare i problemi di GitHub usando un modello di classificazione multiclasse](./tutorials/github-issue-classification.md) illustra come creare un'app che determina l'etichetta Area per un problema di GitHub.</span><span class="sxs-lookup"><span data-stu-id="7a208-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="7a208-115">L'esercitazione [Prevedere i prezzi usando un modello di regressione](./tutorials/taxi-fare.md) illustra come compilare un'app predittiva che usa diversi fattori dei dati cronologici per determinare la risposta.</span><span class="sxs-lookup"><span data-stu-id="7a208-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="7a208-116">L'esercitazione [Classificare i fiori di iris in base alle caratteristiche](./tutorials/iris-clustering.md) illustra come usare un modello di clustering per analizzare il set di dati Iris.</span><span class="sxs-lookup"><span data-stu-id="7a208-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span>

<span data-ttu-id="7a208-117">[Creare un sistema di raccomandazione di film con a ML.NET](./tutorials/movie-recommmendation.md) illustra come creare un'app per consigliare i film agli utenti in base alla loro cronologia.</span><span class="sxs-lookup"><span data-stu-id="7a208-117">[Create a Movie Recommender with ML.NET](./tutorials/movie-recommmendation.md) shows you how to build a recommendation app to recommend movies to users based on their history.</span></span>

<span data-ttu-id="7a208-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md) (Creare un classificatore di immagini personalizzato ML.NET con TensorFlow): illustra come ripetere il training di un modello Tensorflow esistente per creare un classificatore di immagini personalizzato usando ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7a208-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md): demonstrates how to retrain an existing Tensorflow model to create a custom image classifier using ML.NET.</span></span>

## <a name="how-to-guide"></a><span data-ttu-id="7a208-119">Guida pratica</span><span class="sxs-lookup"><span data-stu-id="7a208-119">How to guide</span></span>

<span data-ttu-id="7a208-120">La guida [Compilare un'app elenco di corrispondenze di gioco con Infer.NET e la programmazione probabilistica](./how-to-guides/matchup-app-infer-net.md) illustra come compilare una versione semplificata di un'app di corrispondenze così come sarebbe visualizzata in un gioco per Xbox.</span><span class="sxs-lookup"><span data-stu-id="7a208-120">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="7a208-121">Risorse</span><span class="sxs-lookup"><span data-stu-id="7a208-121">Resources</span></span>

<span data-ttu-id="7a208-122">L'articolo [Glossario di Machine Learning](./resources/glossary.md) contiene le definizioni dei termini chiave.</span><span class="sxs-lookup"><span data-stu-id="7a208-122">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="7a208-123">L'articolo [Attività di Machine Learning](./resources/tasks.md) descrive attività come la classificazione e il rilevamento anomalie.</span><span class="sxs-lookup"><span data-stu-id="7a208-123">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="7a208-124">L'articolo [Trasformazioni di dati](./resources/transforms.md) descrive le funzionalità di preparazione dei dati in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7a208-124">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>

## <a name="api-reference"></a><span data-ttu-id="7a208-125">API (riferimento)</span><span class="sxs-lookup"><span data-stu-id="7a208-125">API reference</span></span>

<span data-ttu-id="7a208-126">[Informazioni di riferimento sulle API ML.NET](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) descrive la gamma di API disponibili.</span><span class="sxs-lookup"><span data-stu-id="7a208-126">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
