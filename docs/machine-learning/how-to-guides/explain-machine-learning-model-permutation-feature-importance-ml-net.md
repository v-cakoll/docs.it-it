---
title: Interpretare ML.NET modelli con priorità delle funzioni di permutazione
description: Comprendere l'importanza delle caratteristiche dei modelli con Permutation Feature Importance in ML.NET
ms.date: 01/30/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: c1163a41cd2feb0e8785ae9d4c6a71dfbedf3f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092616"
---
# <a name="interpret-model-predictions-using-permutation-feature-importance"></a>Interpretare le stime del modello usando l'importanza della funzionalità permutazione

Usando il PFI (Permutation Feature Importance), scopri come interpretare le stime del modello di apprendimento automatico ML.NET. PFI dà il contributo relativo che ogni caratteristica apporta a una previsione.

I modelli di Machine Learning sono spesso considerati black box che accettano gli input e generano un output. I passaggi intermedi o le interazioni tra le caratteristiche che influenzano l'output vengono riconosciute raramente. Poiché il Machine Learning viene ora applicato a più aspetti delle attività quotidiane, ad esempio nel settore sanitario, è di importanza fondamentale comprenderne in che modo un modello di Machine Learning prende le decisioni. Ad esempio, se le diagnosi vengono effettuate tramite un modello di Machine Learning, i professionisti del settore sanitario necessitano di un modo per esaminare i fattori che hanno contribuito alle diagnosi. Una diagnosi corretta può fare una grande differenza nella velocità di recupero di un paziente. Più è dettagliato il livello di descrizione di un modello, maggiore sarà la fiducia dei professionisti del settore sanitario nell'accettare o rifiutare le decisioni prese dal modello.

Per descrivere i modelli vengono usate tecniche diverse, tra cui PFI. La PFI è una tecnica utilizzata per spiegare i modelli di classificazione e regressione che si ispira alla carta Random Forests di [Breiman *Random Forests* ](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (vedi sezione 10). A livello generale, il funzionamento è basato sulla selezione in ordine casuale dei dati una caratteristica alla volta per l'intero set di dati e sul calcolo della diminuzione della metrica delle prestazioni dell'interesse. Maggiore è la modifica, maggiore è l'importanza della funzionalità.

Inoltre, evidenziando le funzionalità più importanti, i generatori di modelli possono concentrarsi sull'uso di un subset di funzionalità più significative che possono potenzialmente ridurre il rumore e i tempi di training.

## <a name="load-the-data"></a>Caricare i dati

Le funzionalità del set di dati usate per questo esempio si trovano dalla colonna 1 alla colonna 12. L'obiettivo consiste nella previsione di `Price`.

| Colonna | Funzionalità | Descrizione
| --- | --- | --- |
| 1 | CrimeRate | Tasso di criminalità pro capite
| 2 | ResidentialZones | Zone residenziali della città
| 3 | CommercialZones | Zone non residenziali della città
| 4 | NearWater | Prossimità al corpo idrico
| 5 | ToxicWasteLevels | Livelli di tossicità (PPM)
| 6 | AverageRoomNumber | Numero medio di locali di un'abitazione
| 7 | HomeAge | Età dell'abitazione
| 8 | BusinessCenterDistance | Distanza dal quartiere direzionale più vicino
| 9 | HighwayAccess | Prossimità alle autostrade
| 10 | TaxRate | Aliquota dell'imposta sugli immobili
| 11 | StudentTeacherRatio | Rapporto studenti-insegnanti
| 12 | PercentPopulationBelowPoverty | Percentuale di popolazione che vive al di sotto della soglia di povertà
| 13 | Price | Prezzo dell'abitazione

Di seguito è riportato un esempio del set di dati:

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

I dati in questo esempio possono essere `HousingPriceData` modellati [`IDataView`](xref:Microsoft.ML.IDataView)da una classe come e caricati in un oggetto .

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

## <a name="train-the-model"></a>Eseguire il training del modello

L'esempio di codice seguente illustra il processo di training di un modello di regressione lineare per la previsione dei prezzi delle abitazioni.

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

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a>Descrivere il modello con Permutation Feature Importance (PFI)

In ML.NET [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) utilizzare il metodo per la rispettiva attività.

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance =
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

Il risultato [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) dell'utilizzo nel [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) set di dati di training è un di oggetti. [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics)fornisce statistiche di riepilogo come media e [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) deviazione standard per più osservazioni `permutationCount` pari al numero di permutazioni specificato dal parametro.

L'importanza, o in questo caso, la diminuzione [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) media assoluta della metrica R al quadrato calcolata da può quindi essere ordinata dal più importante al meno importante.

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

La stampa dei valori di ogni funzionalità in `featureImportanceMetrics` genererà un output simile al seguente. Tenere presente che probabilmente verranno visualizzati risultati diversi poiché questi valori variano in base ai dati ricevuti.

| Funzionalità | Modifica in R quadrato |
|:--|:--:|
HighwayAccess       |   -0.042731
StudentTeacherRatio |   -0.012730
BusinessCenterDistance| -0.010491
TaxRate             |   -0.008545
AverageRoomNumber   |   -0.003949
CrimeRate           |   -0.003665
CommercialZones     |   0.002749
HomeAge             |   -0.002426
ResidentialZones    |   -0.002319
NearWater           |   0.000203
PercentPopulationLivingBelowPoverty|    0.000031
ToxicWasteLevels    |   -0.000019

Esaminando le cinque caratteristiche più importanti di questo set di dati, è possibile osservare che il prezzo di un'abitazione previsto da questo modello è influenzato dalla vicinanza alle autostrade, dal rapporto studenti-insegnanti nelle scuole della zona, dalla vicinanza ai maggiori centri di occupazione, dall'aliquota dell'imposta sugli immobili e dal numero medio di locali dell'abitazione.
