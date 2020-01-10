---
title: Trasformazioni dati
description: Esplorare i componenti di progettazione delle funzionalità supportati in ML.NET.
ms.date: 04/02/2019
ms.openlocfilehash: ca410b475c556db5ad4c3862fb79755b455d6830
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739595"
---
# <a name="data-transformations"></a>Trasformazioni dati

Le trasformazioni dati vengono usate per:

- Preparare i dati per il training del modello
- Applicare un modello importato in formato TensorFlow o ONNX
- Eseguire la post-elaborazione dei dati dopo il passaggio attraverso un modello

Le trasformazioni in questa guida restituiscono classi che implementano l'interfaccia [IEstimator](xref:Microsoft.ML.IEstimator%601). Le trasformazioni dati possono essere concatenate. Ogni trasformazione prevede e produce dati di determinati tipi e formati, che vengono specificati nella documentazione di riferimento collegata.

Alcune trasformazioni dati richiedono dati di training per calcolare i relativi parametri. Ad esempio, il trasformatore <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> calcola la media e la varianza dei dati di training durante l'operazione `Fit()` e usa tali parametri nell'operazione `Transform()`.

Altre trasformazioni dati non richiedono dati di training. Ad esempio, la trasformazione <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> può eseguire l'operazione `Transform()` senza la necessità di dati di training durante l'operazione `Fit()`.

## <a name="column-mapping-and-grouping"></a>Mapping e raggruppamento di colonne

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | Concatenare una o più colonne di input in una nuova colonna di output |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | Copiare e rinominare una o più colonne di input |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | Eliminare una o più colonne di input |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | Selezionare una o più colonne da mantenere dai dati di input |

## <a name="normalization-and-scaling"></a>Normalizzazione e ridimensionamento

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | Sottrarre la media (dei dati di training) e dividere per la varianza (dei dati di training) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | Normalizzare in base al logaritmo dei dati di training |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | Ridimensionare i vettori di input in base al relativo valore [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), dove p è 1, 2 o infinito. L'impostazione predefinita è l2-norm (distanza euclidea) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | Ridimensionare ogni valore in una riga sottraendo la media dei dati di riga e dividere per la deviazione standard o l2-norm (della riga di dati) e moltiplicare per un fattore di scala configurabile (valore predefinito 2) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | Assegnare il valore di input a un indice bin e dividere per il numero di bin per produrre un valore float compreso tra 0 e 1. I limiti di bin sono calcolati per distribuire uniformemente i dati di training tra bin |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | Assegnare il valore di input a un bin in base alla relativa correlazione con la colonna etichetta |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | Ridimensionare l'input in base alla differenza tra i valori minimo e massimo nei dati di training |

## <a name="conversions-between-data-types"></a>Conversioni tra tipi di dati

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | Convertire il tipo di una colonna di input in un nuovo tipo |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue%2A> | Eseguire il mapping dei valori alle chiavi (categorie) in base al dizionario dei mapping fornito |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> | Eseguire il mapping dei valori alle chiavi (categorie) creando il mapping dai dati di input |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A> | Convertire le chiavi ai valori originali |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector%2A> | Convertire le chiavi ai vettori dei valori originali |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector%2A> | Convertire le chiavi a un vettore binario dei valori originali |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A> | Eseguire l'hashing del valore nella colonna di input |

## <a name="text-transformations"></a>Trasformazioni di testo

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText%2A> | Trasformare una colonna di testo in una matrice float di conteggi normalizzati di n-grammi e char-grammi |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A> | Suddividere una o più colonne di testo in singole parole |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys%2A> | Suddividere una o più colonne di testo in float di caratteri singoli in un set di argomenti |
| <xref:Microsoft.ML.TextCatalog.NormalizeText%2A> | Cambiare l'uso di maiuscole/minuscole, rimuovere segni diacritici, segni di punteggiatura e numeri |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams%2A> | Trasformare una colonna di testo in un elenco di conteggi di n-grammi (sequenze di parole consecutive)|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags%2A> | Trasformare una colonna di testo in un elenco di conteggi del vettore di n-grammi |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams%2A> | Trasformare una colonna di testo in un vettore di conteggi di n-grammi con hash |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags%2A> | Trasformare una colonna di testo in un elenco di conteggi di n-grammi con hash |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords%2A>  | Rimuovere parole non significative predefinite per la lingua specificata dalle colonne di input |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords%2A> | Rimuovere parole non significative specifiche dalle colonne di input |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation%2A> | Trasformare un documento (rappresentato come vettore di float) in un vettore di float in un set di argomenti |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding%2A> | Convertire i vettori di token di testo in vettori di frase usando un modello con training preliminare |

## <a name="image-transformations"></a>Trasformazioni di immagini

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> | Convertire un'immagine in gradazioni di grigio |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage%2A> | Convertire un vettore di pixel in <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A> | Convertire pixel dall'immagine di input in un vettore di numeri |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A> | Caricare immagini da una cartella in memoria |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A> | Ridimensionamento delle immagini |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage%2A> | Applicare un modello di rete neurale profonda sottoposto a training preliminare per trasformare un'immagine di input in un vettore di caratteristiche |

## <a name="categorical-data-transformations"></a>Trasformazioni dati categoriche

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A> | Convertire una o più colonne di testo in vettori con codifica [one-hot](https://en.wikipedia.org/wiki/One-hot) |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding%2A> | Convertire una o più colonne di testo in vettori con codifica one-hot basati su hash |

## <a name="time-series-data-transformations"></a>Trasformazioni dati di serie temporali

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn%2A> | Rilevare anomalie nei dati delle serie temporali di input usando l'algoritmo SR (Spectral Residual) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa%2A> | Rilevare punti di modifica nei dati delle serie temporali usando l'analisi SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint%2A> | Rilevare punti di modifica nei dati delle serie temporali indipendenti e identicamente distribuite (IID) usando stime kernel di densità adattive e punteggi basati su martingala |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A> | Prevedere i dati delle serie temporali usando l'analisi SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa%2A> | Rilevare picchi nei dati delle serie temporali usando l'analisi SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike%2A> | Rilevare picchi nei dati delle serie temporali indipendenti e identicamente distribuite (IID) usando stime kernel di densità adattive e punteggi basati su martingala |

## <a name="missing-values"></a>Valori mancanti

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues%2A> | Creare una nuova colonna di output booleana, il cui valore è true quando manca il valore nella colonna di input |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A> | Creare una nuova colonna di output, il cui valore è impostato su un valore predefinito se manca il valore dalla colonna di input, e il valore di input in caso contrario |

## <a name="feature-selection"></a>Selezione funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount%2A> | Selezionare le caratteristiche i cui valori non predefiniti sono superiori a una soglia |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation%2A> | Selezionare le caratteristiche da cui i dati nella colonna etichetta dipendono maggiormente |

## <a name="feature-transformations"></a>Trasformazioni di caratteristiche

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap%2A> | Eseguire il mapping di ogni vettore di input a uno spazio di caratteristiche dimensionali inferiore, dove i prodotti interni approssimano una funzione kernel, in modo che le caratteristiche possano essere usate come input per gli algoritmi lineari |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents%2A> | Ridurre le dimensioni del vettore di caratteristiche di input applicando l'algoritmo PCA (Principal Component Analysis) |

## <a name="explainability-transformations"></a>Trasformazioni di interpretabilità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution%2A> | Calcolare i punteggi dei contributi per ogni elemento di un vettore di caratteristiche |

## <a name="calibration-transformations"></a>Trasformazioni di calibrazione

| Transform | Definizione |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | Trasformare un punteggio non elaborato di un classificatore binario in una probabilità di classe usando la regressione logistica con parametri stimati in base ai dati di training |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | Trasformare un punteggio non elaborato di un classificatore binario in una probabilità di classe usando la regressione logistica con parametri fissi |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive%2A> | Trasformare un punteggio non elaborato di un classificatore binario in una probabilità di classe assegnando punteggi ai bin e calcolando la probabilità in base alla distribuzione tra i bin |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic%2A> | Trasformare un punteggio non elaborato di un classificatore binario in una probabilità di classe assegnando punteggi ai bin, dove la posizione dei limiti e le dimensioni dei bin sono stimate in base ai dati di training  |

## <a name="deep-learning-transformations"></a>Trasformazioni di Deep Learning

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A> | Trasformare i dati di input con un modello ONNX importato |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel%2A> | Trasformare i dati di input con un modello TensorFlow importato |

## <a name="custom-transformations"></a>Trasformazioni personalizzate

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping%2A> | Trasformare le colonne esistenti in colonne nuove con un mapping definito dall'utente |
