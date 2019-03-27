---
title: Eseguire il training di un modello di Machine Learning con dati non contenuti in un file di testo - ML.NET
description: Informazioni sull'uso di ML.NET per caricare dati di training non basati su file per il training di un modello di Machine Learning nell'ambito della pipeline di stima.
ms.date: 03/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 32de37e45b9e19669ea06d74c7f252ec885fe004
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186091"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="1f4ed-103">Eseguire il training di un modello di Machine Learning con dati non contenuti in un file di testo - ML.NET</span><span class="sxs-lookup"><span data-stu-id="1f4ed-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="1f4ed-104">Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="1f4ed-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1f4ed-105">Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1f4ed-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="1f4ed-106">Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.11**.</span><span class="sxs-lookup"><span data-stu-id="1f4ed-106">This how-to and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="1f4ed-107">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="1f4ed-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1f4ed-108">Nel caso d'uso solitamente illustrato per ML.NET viene usato `TextLoader` per la lettura dei dati di training da un file.</span><span class="sxs-lookup"><span data-stu-id="1f4ed-108">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="1f4ed-109">In scenari di training in tempo reale, tuttavia, i dati possono trovarsi altrove. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1f4ed-109">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="1f4ed-110">in tabelle SQL</span><span class="sxs-lookup"><span data-stu-id="1f4ed-110">in SQL tables</span></span>
* <span data-ttu-id="1f4ed-111">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="1f4ed-111">JSON/XML</span></span>
* <span data-ttu-id="1f4ed-112">estratti dai file di log</span><span class="sxs-lookup"><span data-stu-id="1f4ed-112">extracted from log files</span></span>
* <span data-ttu-id="1f4ed-113">generati al momento</span><span class="sxs-lookup"><span data-stu-id="1f4ed-113">generated on the fly</span></span>

<span data-ttu-id="1f4ed-114">Usare la [comprensione dello schema](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) per portare un elemento `IEnumerable` C# esistente in ML.NET come elemento `DataView`.</span><span class="sxs-lookup"><span data-stu-id="1f4ed-114">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="1f4ed-115">Per questo esempio verrà creato il modello di stima della varianza del cliente e verranno estratte dal sistema di produzione le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f4ed-115">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="1f4ed-116">L'ID cliente (ignorato dal modello)</span><span class="sxs-lookup"><span data-stu-id="1f4ed-116">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="1f4ed-117">L'eventuale varianza del cliente ("etichetta" di destinazione)</span><span class="sxs-lookup"><span data-stu-id="1f4ed-117">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="1f4ed-118">La "categoria demografica" (una stringa, ad esempio "giovane adulto" o altro)</span><span class="sxs-lookup"><span data-stu-id="1f4ed-118">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="1f4ed-119">Il numero di visite degli ultimi 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="1f4ed-119">The number of visits from the last 5 days.</span></span>

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

<span data-ttu-id="1f4ed-120">Caricare questi dati in `DataView` ed eseguire il training del modello usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f4ed-120">Load this data into the `DataView` and train the model, using the following code:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.LoadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
