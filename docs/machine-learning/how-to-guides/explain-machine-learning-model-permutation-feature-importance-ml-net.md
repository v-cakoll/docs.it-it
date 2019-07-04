---
title: Descrivere le previsioni del modello con Permutation Feature Importance
description: Comprendere l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET
ms.date: 05/02/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 1037a1f1c21ef2c9b9a87a070a7d2003c1e76eb4
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307375"
---
# <a name="explain-model-predictions-using-permutation-feature-importance"></a><span data-ttu-id="304b3-103">Descrivere le previsioni del modello con Permutation Feature Importance</span><span class="sxs-lookup"><span data-stu-id="304b3-103">Explain model predictions using Permutation Feature Importance</span></span>

<span data-ttu-id="304b3-104">Di seguito viene illustrato come descrivere le previsioni del modello di Machine Learning di ML.NET e il contributo delle caratteristiche alle previsioni usando Permutation Feature Importance (PFI).</span><span class="sxs-lookup"><span data-stu-id="304b3-104">Learn how to explain ML.NET machine learning model predictions by understanding the contribution features have to predictions using Permutation Feature Importance (PFI).</span></span>

<span data-ttu-id="304b3-105">I modelli di Machine Learning sono spesso considerati black box che accettano gli input e generano un output.</span><span class="sxs-lookup"><span data-stu-id="304b3-105">Machine learning models are often thought of as black boxes that take inputs and generate an output.</span></span> <span data-ttu-id="304b3-106">I passaggi intermedi o le interazioni tra le caratteristiche che influenzano l'output vengono riconosciute raramente.</span><span class="sxs-lookup"><span data-stu-id="304b3-106">The intermediate steps or interactions among the features that influence the output are rarely understood.</span></span> <span data-ttu-id="304b3-107">Poiché il Machine Learning viene ora applicato a più aspetti delle attività quotidiane, ad esempio nel settore sanitario, è di importanza fondamentale comprenderne in che modo un modello di Machine Learning prende le decisioni.</span><span class="sxs-lookup"><span data-stu-id="304b3-107">As machine learning is introduced into more aspects of everyday life such as healthcare, it's of utmost importance to understand why a machine learning model makes the decisions it does.</span></span> <span data-ttu-id="304b3-108">Ad esempio, se le diagnosi vengono effettuate tramite un modello di Machine Learning, i professionisti del settore sanitario necessitano di un modo per esaminare i fattori che hanno contribuito alle diagnosi.</span><span class="sxs-lookup"><span data-stu-id="304b3-108">For example, if diagnoses are made by a machine learning model, healthcare professionals need a way to look into the factors that went into making that diagnoses.</span></span> <span data-ttu-id="304b3-109">Una diagnosi corretta può fare una grande differenza nella velocità di recupero di un paziente.</span><span class="sxs-lookup"><span data-stu-id="304b3-109">Providing the right diagnosis could make a great difference on whether a patient has a speedy recovery or not.</span></span> <span data-ttu-id="304b3-110">Più è dettagliato il livello di descrizione di un modello, maggiore sarà la fiducia dei professionisti del settore sanitario nell'accettare o rifiutare le decisioni prese dal modello.</span><span class="sxs-lookup"><span data-stu-id="304b3-110">Therefore the higher the level of explainability in a model, the greater confidence healthcare professionals have to accept or reject the decisions made by the model.</span></span>

<span data-ttu-id="304b3-111">Per descrivere i modelli vengono usate tecniche diverse, tra cui PFI.</span><span class="sxs-lookup"><span data-stu-id="304b3-111">Various techniques are used to explain models, one of which is PFI.</span></span> <span data-ttu-id="304b3-112">PFI è una tecnica usata per descrivere i modelli di classificazione e regressione basata sul [documento *Random Forests* di Breiman](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (vedere la sezione 10).</span><span class="sxs-lookup"><span data-stu-id="304b3-112">PFI is a technique used to explain classification and regression models that is inspired by [Breiman's *Random Forests* paper](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf)(see section 10).</span></span> <span data-ttu-id="304b3-113">A livello generale, il funzionamento è basato sulla selezione in ordine casuale dei dati una caratteristica alla volta per l'intero set di dati e sul calcolo della diminuzione della metrica delle prestazioni dell'interesse.</span><span class="sxs-lookup"><span data-stu-id="304b3-113">At a high level, the way it works is by randomly shuffling data one feature at a time for the entire dataset and calculating how much the performance metric of interest decreases.</span></span> <span data-ttu-id="304b3-114">Maggiore è la modifica, maggiore è l'importanza della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="304b3-114">The larger the change, the more important that feature is.</span></span> 

<span data-ttu-id="304b3-115">Inoltre, evidenziando le funzionalità più importanti, i generatori di modelli possono concentrarsi sull'uso di un subset di funzionalità più significative che possono potenzialmente ridurre il rumore e i tempi di training.</span><span class="sxs-lookup"><span data-stu-id="304b3-115">Additionally, by highlighting the most important features, model builders can focus on using a subset of more meaningful features which can potentially reduce noise and training time.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="304b3-116">Caricare i dati</span><span class="sxs-lookup"><span data-stu-id="304b3-116">Load the data</span></span>

<span data-ttu-id="304b3-117">Le funzionalità del set di dati usate per questo esempio si trovano dalla colonna 1 alla colonna 12.</span><span class="sxs-lookup"><span data-stu-id="304b3-117">The features in the dataset being used for this sample are in columns 1-12.</span></span> <span data-ttu-id="304b3-118">L'obiettivo consiste nella previsione di `Price`.</span><span class="sxs-lookup"><span data-stu-id="304b3-118">The goal is to predict `Price`.</span></span> 

| <span data-ttu-id="304b3-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="304b3-119">Column</span></span> | <span data-ttu-id="304b3-120">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="304b3-120">Feature</span></span> | <span data-ttu-id="304b3-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="304b3-121">Description</span></span> 
| --- | --- | --- |
| <span data-ttu-id="304b3-122">1</span><span class="sxs-lookup"><span data-stu-id="304b3-122">1</span></span> | <span data-ttu-id="304b3-123">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="304b3-123">CrimeRate</span></span> | <span data-ttu-id="304b3-124">Tasso di criminalità pro capite</span><span class="sxs-lookup"><span data-stu-id="304b3-124">Per capita crime rate</span></span>
| <span data-ttu-id="304b3-125">2</span><span class="sxs-lookup"><span data-stu-id="304b3-125">2</span></span> | <span data-ttu-id="304b3-126">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="304b3-126">ResidentialZones</span></span> | <span data-ttu-id="304b3-127">Zone residenziali della città</span><span class="sxs-lookup"><span data-stu-id="304b3-127">Residential zones in town</span></span>
| <span data-ttu-id="304b3-128">3</span><span class="sxs-lookup"><span data-stu-id="304b3-128">3</span></span> | <span data-ttu-id="304b3-129">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="304b3-129">CommercialZones</span></span> | <span data-ttu-id="304b3-130">Zone non residenziali della città</span><span class="sxs-lookup"><span data-stu-id="304b3-130">Non-residential zones in town</span></span>
| <span data-ttu-id="304b3-131">4</span><span class="sxs-lookup"><span data-stu-id="304b3-131">4</span></span> | <span data-ttu-id="304b3-132">NearWater</span><span class="sxs-lookup"><span data-stu-id="304b3-132">NearWater</span></span> | <span data-ttu-id="304b3-133">Prossimità al corpo idrico</span><span class="sxs-lookup"><span data-stu-id="304b3-133">Proximity to body of water</span></span>
| <span data-ttu-id="304b3-134">5</span><span class="sxs-lookup"><span data-stu-id="304b3-134">5</span></span> | <span data-ttu-id="304b3-135">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="304b3-135">ToxicWasteLevels</span></span> | <span data-ttu-id="304b3-136">Livelli di tossicità (PPM)</span><span class="sxs-lookup"><span data-stu-id="304b3-136">Toxicity levels (PPM)</span></span>
| <span data-ttu-id="304b3-137">6</span><span class="sxs-lookup"><span data-stu-id="304b3-137">6</span></span> | <span data-ttu-id="304b3-138">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="304b3-138">AverageRoomNumber</span></span> | <span data-ttu-id="304b3-139">Numero medio di locali di un'abitazione</span><span class="sxs-lookup"><span data-stu-id="304b3-139">Average number of rooms in house</span></span>
| <span data-ttu-id="304b3-140">7</span><span class="sxs-lookup"><span data-stu-id="304b3-140">7</span></span> | <span data-ttu-id="304b3-141">HomeAge</span><span class="sxs-lookup"><span data-stu-id="304b3-141">HomeAge</span></span> | <span data-ttu-id="304b3-142">Età dell'abitazione</span><span class="sxs-lookup"><span data-stu-id="304b3-142">Age of home</span></span>
| <span data-ttu-id="304b3-143">8</span><span class="sxs-lookup"><span data-stu-id="304b3-143">8</span></span> | <span data-ttu-id="304b3-144">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="304b3-144">BusinessCenterDistance</span></span> | <span data-ttu-id="304b3-145">Distanza dal quartiere direzionale più vicino</span><span class="sxs-lookup"><span data-stu-id="304b3-145">Distance to nearest business district</span></span>
| <span data-ttu-id="304b3-146">9</span><span class="sxs-lookup"><span data-stu-id="304b3-146">9</span></span> | <span data-ttu-id="304b3-147">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="304b3-147">HighwayAccess</span></span> | <span data-ttu-id="304b3-148">Prossimità alle autostrade</span><span class="sxs-lookup"><span data-stu-id="304b3-148">Proximity to highways</span></span>
| <span data-ttu-id="304b3-149">10</span><span class="sxs-lookup"><span data-stu-id="304b3-149">10</span></span> | <span data-ttu-id="304b3-150">TaxRate</span><span class="sxs-lookup"><span data-stu-id="304b3-150">TaxRate</span></span> | <span data-ttu-id="304b3-151">Aliquota dell'imposta sugli immobili</span><span class="sxs-lookup"><span data-stu-id="304b3-151">Property tax rate</span></span>
| <span data-ttu-id="304b3-152">11</span><span class="sxs-lookup"><span data-stu-id="304b3-152">11</span></span> | <span data-ttu-id="304b3-153">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="304b3-153">StudentTeacherRatio</span></span> | <span data-ttu-id="304b3-154">Rapporto studenti-insegnanti</span><span class="sxs-lookup"><span data-stu-id="304b3-154">Ratio of students to teachers</span></span>
| <span data-ttu-id="304b3-155">12</span><span class="sxs-lookup"><span data-stu-id="304b3-155">12</span></span> | <span data-ttu-id="304b3-156">PercentPopulationBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="304b3-156">PercentPopulationBelowPoverty</span></span> | <span data-ttu-id="304b3-157">Percentuale di popolazione che vive al di sotto della soglia di povertà</span><span class="sxs-lookup"><span data-stu-id="304b3-157">Percent of population living below poverty</span></span>
| <span data-ttu-id="304b3-158">13</span><span class="sxs-lookup"><span data-stu-id="304b3-158">13</span></span> | <span data-ttu-id="304b3-159">Price</span><span class="sxs-lookup"><span data-stu-id="304b3-159">Price</span></span> | <span data-ttu-id="304b3-160">Prezzo dell'abitazione</span><span class="sxs-lookup"><span data-stu-id="304b3-160">Price of the home</span></span>

<span data-ttu-id="304b3-161">Di seguito è riportato un esempio del set di dati:</span><span class="sxs-lookup"><span data-stu-id="304b3-161">A sample of the dataset is shown below:</span></span>

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

<span data-ttu-id="304b3-162">I dati in questo esempio possono essere modellati in base a una classe come `HousingPriceData`:</span><span class="sxs-lookup"><span data-stu-id="304b3-162">The data in this sample can be modeled by a class like `HousingPriceData`:</span></span>

```csharp
class HousingPriceData
{
    [LoadColumn(0)]
    public float CrimeRate { get; set; }

    [LoadColumn(1)]
    public float ResidentialZones { get; set; }

    [LoadColumn(2)]
    public float CommercialZones { get; set; }

    [LoadColumn(3)]
    public float NearWater { get; set; }

    [LoadColumn(4)]
    public float ToxicWasteLevels { get; set; }

    [LoadColumn(5)]
    public float AverageRoomNumber { get; set; }

    [LoadColumn(6)]
    public float HomeAge { get; set; }

    [LoadColumn(7)]
    public float BusinessCenterDistance { get; set; }

    [LoadColumn(8)]
    public float HighwayAccess { get; set; }

    [LoadColumn(9)]
    public float TaxRate { get; set; }

    [LoadColumn(10)]
    public float StudentTeacherRatio { get; set; }

    [LoadColumn(11)]
    public float PercentPopulationBelowPoverty { get; set; }

    [LoadColumn(12)]
    [ColumnName("Label")]
    public float Price { get; set; }
}
```

<span data-ttu-id="304b3-163">Caricare i dati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="304b3-163">Load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

## <a name="train-the-model"></a><span data-ttu-id="304b3-164">Eseguire il training del modello</span><span class="sxs-lookup"><span data-stu-id="304b3-164">Train the model</span></span>

<span data-ttu-id="304b3-165">L'esempio di codice seguente illustra il processo di training di un modello di regressione lineare per la previsione dei prezzi delle abitazioni.</span><span class="sxs-lookup"><span data-stu-id="304b3-165">The code sample below illustrates the process of training a linear regression model to predict house prices.</span></span>

```csharp
// 1. Get the column name of input features.
string[] featureColumnNames = 
    data.Schema
        .Select(column => column.Name)
        .Where(columnName => columnName != "Label").ToArray();

// 2. Define estimator with data pre-processing steps
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", featureColumnNames)
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// 3. Create transformer using the data pre-processing estimator
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// 4. Pre-process the training data
IDataView preprocessedTrainData = dataPrepTransformer.Transform(data);

// 5. Define Stochastic Dual Coordinate Ascent machine learning estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// 6. Train machine learning model
var sdcaModel = sdcaEstimator.Fit(preprocessedTrainData);
```

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a><span data-ttu-id="304b3-166">Descrivere il modello con Permutation Feature Importance (PFI)</span><span class="sxs-lookup"><span data-stu-id="304b3-166">Explain the model with Permutation Feature Importance (PFI)</span></span>

<span data-ttu-id="304b3-167">In ML.NET usare il metodo [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) per la rispettiva attività.</span><span class="sxs-lookup"><span data-stu-id="304b3-167">In ML.NET use the [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) method for your respective task.</span></span>

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance = 
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

<span data-ttu-id="304b3-168">Se viene usato [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) nel training set, viene restituita una [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) di oggetti [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics).</span><span class="sxs-lookup"><span data-stu-id="304b3-168">The result of using [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) on the training dataset is an [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) of [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) objects.</span></span> <span data-ttu-id="304b3-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) fornisce statistiche di riepilogo come la media e la deviazione standard per più osservazioni di [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics)corrispondente al numero di permutazioni specificate dal parametro `permutationCount`.</span><span class="sxs-lookup"><span data-stu-id="304b3-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) provides summary statistics like mean and standard deviation for multiple observations of [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equal to the number of permutations specified by the `permutationCount` parameter.</span></span>

<span data-ttu-id="304b3-170">L'importanza, o in questo caso la diminuzione della media assoluta nella metrica R quadrato calcolata da [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions), può quindi essere ordinata dalla più importante alla meno importante.</span><span class="sxs-lookup"><span data-stu-id="304b3-170">The importance, or in this case, the absolute average decrease in R-squared metric calculated by [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) can then be ordered from most important to least important.</span></span>  

```csharp
// Order features by importance
var featureImportanceMetrics =
    permutationFeatureImportance
        .Select((metric, index) => new { index, metric.RSquared })
        .OrderByDescending(myFeatures => Math.Abs(myFeatures.RSquared.Mean));

Console.WriteLine("Feature\tPFI");

foreach (var feature in featureImportanceMetrics)
{
    Console.WriteLine($"{featureColumnNames[feature.index],-20}|\t{feature.RSquared.Mean:F6}");
}
```

<span data-ttu-id="304b3-171">La stampa dei valori di ogni funzionalità in `featureImportanceMetrics` genererà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="304b3-171">Printing the values for each of the features in `featureImportanceMetrics` would generate output similar to that below.</span></span> <span data-ttu-id="304b3-172">Tenere presente che probabilmente verranno visualizzati risultati diversi poiché questi valori variano in base ai dati ricevuti.</span><span class="sxs-lookup"><span data-stu-id="304b3-172">Keep in mind that you should expect to see different results because these values vary based on the data that they are given.</span></span>  

| <span data-ttu-id="304b3-173">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="304b3-173">Feature</span></span> | <span data-ttu-id="304b3-174">Modifica in R quadrato</span><span class="sxs-lookup"><span data-stu-id="304b3-174">Change to R-Squared</span></span> |
|:--|:--:|
<span data-ttu-id="304b3-175">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="304b3-175">HighwayAccess</span></span>       |   <span data-ttu-id="304b3-176">-0.042731</span><span class="sxs-lookup"><span data-stu-id="304b3-176">-0.042731</span></span>
<span data-ttu-id="304b3-177">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="304b3-177">StudentTeacherRatio</span></span> |   <span data-ttu-id="304b3-178">-0.012730</span><span class="sxs-lookup"><span data-stu-id="304b3-178">-0.012730</span></span>
<span data-ttu-id="304b3-179">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="304b3-179">BusinessCenterDistance</span></span>| <span data-ttu-id="304b3-180">-0.010491</span><span class="sxs-lookup"><span data-stu-id="304b3-180">-0.010491</span></span>
<span data-ttu-id="304b3-181">TaxRate</span><span class="sxs-lookup"><span data-stu-id="304b3-181">TaxRate</span></span>             |   <span data-ttu-id="304b3-182">-0.008545</span><span class="sxs-lookup"><span data-stu-id="304b3-182">-0.008545</span></span>
<span data-ttu-id="304b3-183">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="304b3-183">AverageRoomNumber</span></span>   |   <span data-ttu-id="304b3-184">-0.003949</span><span class="sxs-lookup"><span data-stu-id="304b3-184">-0.003949</span></span>
<span data-ttu-id="304b3-185">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="304b3-185">CrimeRate</span></span>           |   <span data-ttu-id="304b3-186">-0.003665</span><span class="sxs-lookup"><span data-stu-id="304b3-186">-0.003665</span></span>
<span data-ttu-id="304b3-187">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="304b3-187">CommercialZones</span></span>     |   <span data-ttu-id="304b3-188">0.002749</span><span class="sxs-lookup"><span data-stu-id="304b3-188">0.002749</span></span>
<span data-ttu-id="304b3-189">HomeAge</span><span class="sxs-lookup"><span data-stu-id="304b3-189">HomeAge</span></span>             |   <span data-ttu-id="304b3-190">-0.002426</span><span class="sxs-lookup"><span data-stu-id="304b3-190">-0.002426</span></span>
<span data-ttu-id="304b3-191">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="304b3-191">ResidentialZones</span></span>    |   <span data-ttu-id="304b3-192">-0.002319</span><span class="sxs-lookup"><span data-stu-id="304b3-192">-0.002319</span></span>
<span data-ttu-id="304b3-193">NearWater</span><span class="sxs-lookup"><span data-stu-id="304b3-193">NearWater</span></span>           |   <span data-ttu-id="304b3-194">0.000203</span><span class="sxs-lookup"><span data-stu-id="304b3-194">0.000203</span></span>
<span data-ttu-id="304b3-195">PercentPopulationLivingBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="304b3-195">PercentPopulationLivingBelowPoverty</span></span>|    <span data-ttu-id="304b3-196">0.000031</span><span class="sxs-lookup"><span data-stu-id="304b3-196">0.000031</span></span>
<span data-ttu-id="304b3-197">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="304b3-197">ToxicWasteLevels</span></span>    |   <span data-ttu-id="304b3-198">-0.000019</span><span class="sxs-lookup"><span data-stu-id="304b3-198">-0.000019</span></span>

<span data-ttu-id="304b3-199">Esaminando le cinque caratteristiche più importanti di questo set di dati, è possibile osservare che il prezzo di un'abitazione previsto da questo modello è influenzato dalla vicinanza alle autostrade, dal rapporto studenti-insegnanti nelle scuole della zona, dalla vicinanza ai maggiori centri di occupazione, dall'aliquota dell'imposta sugli immobili e dal numero medio di locali dell'abitazione.</span><span class="sxs-lookup"><span data-stu-id="304b3-199">Taking a look at the five most important features for this dataset, the price of a house predicted by this model is influenced by its proximity to highways, student teacher ratio of schools in the area, proximity to major employment centers, property tax rate and average number of rooms in the home.</span></span>
