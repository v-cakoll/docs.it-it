---
title: Guide pratiche di Machine Learning per .NET - ML.NET
description: Informazioni su come eseguire attività specifiche per agevolare la creazione di soluzioni di intelligenza artificiale personalizzate e l'integrazione di Machine Learning nelle applicazioni .NET.
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: c8d1258629f777cd8bced47e4b956c9cf100a682
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427583"
---
# <a name="net-machine-learning-how-to-guides---mlnet"></a><span data-ttu-id="2e704-103">Guide pratiche di Machine Learning per .NET - ML.NET</span><span class="sxs-lookup"><span data-stu-id="2e704-103">.NET Machine learning how-to guides - ML.NET</span></span>

<span data-ttu-id="2e704-104">Nella sezione Guida pratica della guida di ML.NET sono disponibili le risposte alle domande più frequenti.</span><span class="sxs-lookup"><span data-stu-id="2e704-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="2e704-105">In alcuni casi gli articoli sono presenti in più sezioni per facilitarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="2e704-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="2e704-106">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="2e704-106">Load the data</span></span>

* [<span data-ttu-id="2e704-107">Caricare dati con più colonne da un file CSV per l'elaborazione con Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2e704-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="2e704-108">Caricare dati da più file per l'elaborazione con Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2e704-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="2e704-109">Caricare dati da un file di testo per l'elaborazione con Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2e704-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="2e704-110">Preparare i dati</span><span class="sxs-lookup"><span data-stu-id="2e704-110">Prepare the data</span></span>

* [<span data-ttu-id="2e704-111">Pre-elaborare i dati di training con normalizzatori da usare nell'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="2e704-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="2e704-112">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="2e704-112">Train the model</span></span>

* [<span data-ttu-id="2e704-113">Eseguire il training di un modello di Machine Learning con dati non contenuti in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2e704-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="2e704-114">Eseguire il training di un modello di Machine Learning tramite convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="2e704-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="2e704-115">Eseguire il training di un modello di regressione per stimare un valore usando ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2e704-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="2e704-116">Valutare la qualità del modello</span><span class="sxs-lookup"><span data-stu-id="2e704-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="2e704-117">Calcolare le metriche per valutare la qualità di un modello.</span><span class="sxs-lookup"><span data-stu-id="2e704-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="2e704-118">Comprensibilità dei modelli</span><span class="sxs-lookup"><span data-stu-id="2e704-118">Model explainability</span></span>

* [<span data-ttu-id="2e704-119">Determinare l'importanza delle funzionalità dei modelli con Permutation Feature Importance.</span><span class="sxs-lookup"><span data-stu-id="2e704-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="2e704-120">Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli.</span><span class="sxs-lookup"><span data-stu-id="2e704-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="2e704-121">Progettazione di funzionalità</span><span class="sxs-lookup"><span data-stu-id="2e704-121">Feature engineering</span></span>

* [<span data-ttu-id="2e704-122">Applicare la progettazione di funzionalità per il training del modello ai dati categorici.</span><span class="sxs-lookup"><span data-stu-id="2e704-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="2e704-123">Applicare la progettazione di funzionalità per il training del modello ai dati testuali con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2e704-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="2e704-124">Esegui</span><span class="sxs-lookup"><span data-stu-id="2e704-124">Run</span></span>

* [<span data-ttu-id="2e704-125">Esaminare i valori dei dati intermedi durante l'elaborazione della pipeline di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2e704-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="2e704-126">Rendere operativo un modello di Machine Learning sottoposto a training nelle app.</span><span class="sxs-lookup"><span data-stu-id="2e704-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="2e704-127">Usare PredictionFunction per effettuare una stima alla volta.</span><span class="sxs-lookup"><span data-stu-id="2e704-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="2e704-128">Programmazione probabalistica (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="2e704-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="2e704-129">Creare un'app elenco di corrispondenze di gioco con Infer.NET e la programmazione probabilistica.</span><span class="sxs-lookup"><span data-stu-id="2e704-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)