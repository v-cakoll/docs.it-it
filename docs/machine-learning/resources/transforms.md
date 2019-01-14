---
title: Trasformazioni dati di apprendimento automatico - ML.NET
description: Esplorare i componenti di progettazione delle funzionalità supportati in ML.NET.
author: JRAlexander
ms.custom: seodec18
ms.date: 12/14/2018
ms.openlocfilehash: c311aa59426b716ffcd2c53e890d2e3e380360a7
ms.sourcegitcommit: 81bd16c7435a8c9183d2a7e878a2a5eff7d04584
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2019
ms.locfileid: "54249125"
---
# <a name="machine-learning-data-transforms---mlnet"></a>Trasformazioni dati di apprendimento automatico - ML.NET

Le tabelle seguenti contengono informazioni su tutte le trasformazioni dati supportate in ML.NET.

> [!NOTE]
> ML.NET è attualmente in anteprima. Non tutte le trasformazioni dati sono attualmente supportate. Per inviare una richiesta per una determinata trasformazione, aprire un problema nel repository GitHub [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="combiners-and-segregators"></a>Combinatori e separatori

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | Raggruppa i valori di una colonna scalare in un vettore in base a un ID gruppo contiguo. |
| <xref:Microsoft.ML.Legacy.Transforms.FeatureCombiner> | Combina tutte le funzionalità in una colonna funzionalità. |
| <xref:Microsoft.ML.Legacy.Transforms.ManyHeterogeneousModelCombiner> | Combina una sequenza di oggetti TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |
| <xref:Microsoft.ML.Legacy.Transforms.ModelCombiner> | Combina una sequenza di oggetti TransformModel in un singolo modello. |
| <xref:Microsoft.ML.Legacy.Transforms.Segregator> | Separa le colonne vettore in sequenze di righe, operazione inversa del raggruppamento trasformazione. |
| <xref:Microsoft.ML.Legacy.Transforms.TwoHeterogeneousModelCombiner> | Combina un oggetto TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | Separa le colonne vettore in sequenze di righe, operazione inversa della trasformazione di raggruppamento. |

## <a name="conversions"></a>Conversioni 

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | Esegue l'hashing di colonne a valore singolo o colonne vettore. Per le colonne vettore, esegue l'hashing di ogni slot separatamente. È in grado di eseguire l'hashing di valori di testo o valori di chiave. |
| <xref:Microsoft.ML.Legacy.Transforms.HashConverter> | Converte i valori colonna in hash. Questa trasformazione accetta input numerici e di testo, sia con colonne singole che vettoriali. |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | Converte i valori di più colonne in hash. Questa trasformazione accetta input numerici e di testo, sia con colonne singole che vettoriali. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | Converte una chiave in una colonna vettore binaria. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | Usa i metadati KeyValues per eseguire il mapping degli indici di chiave ai valori corrispondenti nei metadati KeyValues. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | Converte una chiave in una colonna vettore. |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | Modifica il tipo di colonna sottostante a condizione che il tipo possa essere convertito. |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |


## <a name="deep-learning"></a>Deep Learning

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Specifica i dati per un modello ONNX esistente e restituisce il punteggio (stima). |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | È in grado di assegnare il punteggio usando un modello TensorFlow con pre-training o di ripetere il training del modello TensorFlow. |

## <a name="feature-extraction"></a>Estrazione delle funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | Rimuove l'elenco specificato di parole non significative confrontando i singoli token (confronto senza distinzione tra maiuscole e minuscole) con le parole non significative.| 
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageGrayscaleTransform> | Accetta una o più colonne ImageType e le converte in una rappresentazione in scala di grigi della stessa immagine.|
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageLoaderTransform> | Accetta una o più colonne ReadOnlyMemory e le carica come ImageType. |
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImagePixelExtractorTransform> | Accetta una o più colonne ImageType e le converte in una rappresentazione di vettore.|
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageResizerTransform> | Accetta una o più colonne ImageType e le ridimensiona in base all'altezza e alla larghezza specificate.|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | Implementa LightLDA, un'implementazione all'avanguardia dell'allocazione latente di Dirichlet.|
| <xref:Microsoft.ML.Transforms.LoadTransform> | Carica trasformazioni specifiche dal file di modello specificato. Consente trasformazioni di tipo "cherry-pick" da una catena serializzata o l'applicazione di una trasformazione con pre-training a una visualizzazione dati diversa, ma comunque compatibile. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | Produce un elenco di conteggi di n-grammi (sequenze di valori consecutivi di lunghezza 1-n) in un vettore specifico di chiavi. Tale operazione viene eseguita creando un dizionario di n-grammi e usando l'ID nel dizionario come indice nell'elenco. | 
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | Trasforma una raccolta di testo in formato token (vettore di ReadOnlyMemory) o vettori di chiavi in vettori di funzionalità numerici. I vettori di funzionalità sono conteggi di n-grammi (sequenze di token consecutivi, parole o chiavi, di lunghezza 1-n). | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | Trasforma una raccolta di testo in formato token (vettore di ReadOnlyMemory) in vettori di funzionalità numerici usando hash. | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | Produce un elenco di conteggi di n-grammi (sequenze di parole consecutive di lunghezza 1-n) in un testo specifico. | 
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | Converte il valore di categoria in una matrice di indicatori compilando un dizionario di categorie basato sui dati e usando l'ID presente nel dizionario come indice nella matrice |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | Calcola la proiezione del vettore di funzionalità in un sottospazio a bassa priorità. |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | Usa un modello di sentiment con pre-training per assegnare un punteggio alle stringhe di input. |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | Rimuove l'elenco specifico della lingua di parole non significative (parole più comuni) confrontando i singoli token (confronto senza distinzione tra maiuscole e minuscole) con le parole non significative. |
| <xref:Microsoft.ML.Transforms.Categorical.TermLookupTransformer> | Esegue il mapping delle colonne con valori di testo alle nuove colonne usando un set di dati di mapping specificato tramite gli argomenti. |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | Produce un elenco di conteggi di n-grammi (sequenze di parole consecutive) in un testo specifico. Tale operazione viene eseguita creando un dizionario di n-grammi e usando l'ID nel dizionario come indice nell'elenco. |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | Produce un elenco di conteggi di n-grammi (sequenze di parole consecutive di lunghezza 1-n) in un testo specifico. A tale scopo, esegue l'hashing di ogni n-grammo e usa il valore hash come indice nell'elenco. |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | Divide il testo in parole usando il carattere separatore. |


## <a name="image-model-featurizers"></a>Algoritmi di estrazione delle funzionalità del modello di immagine

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | Metodo di estensione da usare con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> per poter usare un modello [AlexNet](https://en.wikipedia.org/wiki/AlexNet) con pre-training. Il pacchetto NuGet contenente questa estensione include anche il file di modello binario. | 
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | Metodo di estensione da usare con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> per poter usare un modello ResNet18 con pre-training. Il pacchetto NuGet contenente questa estensione include anche il file di modello binario. |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | Metodo di estensione da usare con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> per poter usare un modello ResNet50 con pre-training. Il pacchetto NuGet contenente questa estensione include anche il file di modello binario. |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | Metodo di estensione da usare con <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator> per poter usare un modello ResNet101 con pre-training. Il pacchetto NuGet contenente questa estensione include anche il file di modello binario. |

## <a name="label-parsing"></a>Analisi etichette

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.Dictionarizer> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |
| <xref:Microsoft.ML.Legacy.Transforms.LabelColumnKeyBooleanConverter> | Trasforma l'etichetta in chiave o bool (se necessario) per renderla appropriata per la classificazione. |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  Converte le etichette. |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | Esegue un nuovo mapping delle etichette multiclasse su etichette True, False binarie, principalmente per l'uso con OVA.|
| <xref:Microsoft.ML.Legacy.Transforms.LabelToFloatConverter> | Trasforma l'etichetta in float per renderla appropriata per la regressione. |
| <xref:Microsoft.ML.Legacy.Transforms.PredictedLabelColumnOriginalValueConverter> | Trasforma una colonna etichetta stimata nei relativi valori originali, a meno che non sia di tipo bool. |

## <a name="missing-values"></a>Valori mancanti

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | Elimina i valori mancanti dalle colonne. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | Crea una colonna di output booleana con lo stesso numero di slot della colonna di input in cui il valore di output è true se manca il valore nella colonna di input. |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | Consente di gestire i valori mancanti sostituendoli con il valore predefinito o con il valore medio/min/max (solo per le colonne non di testo). |

## <a name="normalization"></a>Normalization

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | Trasformazione di normalizzazione Lp-Norm (a livello di vettore/riga). |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | Calcola la media e la varianza per una colonna con valori vettoriali. Tiene traccia della media corrente e del valore M2 (somma dei quadrati delle differenze dei valori rispetto al valore medio), del numero di valori diversi da numeri e del numero di elementi diversi da zero. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | Calcola la media e la varianza per una colonna con valori vettoriali. Tiene traccia della media corrente e del valore M2 (somma dei quadrati delle differenze dei valori rispetto al valore medio), del numero di valori diversi da numeri e del numero di elementi diversi da zero. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | Tiene traccia dei valori minimo, massimo, del numero di valori di tipo non sparse (vCount) e del numero di chiamate ProcessValue() (trainCount) per una colonna con valori vettoriali. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxSngAggregator> | Tiene traccia dei valori minimo, massimo, del numero di valori di tipo non sparse (vCount) e del numero di chiamate ProcessValue() (trainCount) per una colonna con valori vettoriali. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | Standardizza gli intervalli di funzionalità. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |Standardizza gli intervalli di funzionalità. |

## <a name="onnx"></a>Onnx

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Assegna punteggi ai modelli ONNX con pre-training che usano lo standard ONNX v1.2 |

## <a name="preprocessing"></a>Pre-elaborazione
| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | Approssima il campionamento bootstrap usando il campionamento Poisson. |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | Produce una RFF (Random Fourier Feature). |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Tokenizer orientato ai caratteri in cui il testo viene considerato una sequenza di caratteri. |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | Semplifica l'ottimizzazione per favorire l'identificazione dei pesi. |

## <a name="row-filters"></a>Filtri di riga

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | Seleziona in ordine casuale il tentativo casuale di esecuzione di un cursore usando un pool di un determinato numero di righe.  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | Consente di limitare l'input a un subset di righe ignorando un numero di righe. |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | Consente di limitare l'input a un subset di righe in un offset facoltativo. Può essere usato per implementare il paging dei dati. Quando viene creato con SkipTakeFilter.SkipArguments si comporta come `SkipFilter`.
| <xref:Microsoft.ML.Transforms.TakeFilter> | Consente di limitare l'input a un subset di righe accettando le prime N righe. |


## <a name="schema"></a>Schema

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | Duplica le colonne dal set di dati.|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | Seleziona un set di colonne da eliminare o mantenere in un determinato input. |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | Elimina gli slot dalle colonne.|
| <xref:Microsoft.ML.Legacy.Transforms.KeyToTextConverter> | KeyToValueTransform utilizza i metadati KeyValues per eseguire il mapping degli indici di chiave ai valori corrispondenti nei metadati KeyValues. |
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | Crea una nuova colonna con il tipo e i valori predefiniti specificati. |
| <xref:Microsoft.ML.Transforms.RangeFilter> | Filtra una vista dati in una colonna di tipo Single, Double o Key (contigua). Mantiene i valori che sono compresi nell'intervallo min/max specificato. Le righe NaN vengono sempre escluse tramite filtro. Se l'input è di tipo Key, i valori min/max vengono considerati percentuali del numero di valori. |

## <a name="tensorflow"></a>TensorFlow

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Assegna il punteggio usando un modello TensorFlow con pre-training o ripete il training del modello TensorFlow. |

## <a name="text-processing-and-featurization"></a>Elaborazione testo ed estrazione funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | Trasformazione di normalizzazione del testo che consente la normalizzazione delle maiuscole/minuscole, la rimozione di segni diacritici, segni di punteggiatura e/o numeri. La trasformazione opera sull'input di testo e sul vettore di token/testo (vettore di ReadOnlyMemory). |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Tokenizer orientato ai caratteri in cui il testo viene considerato una sequenza di caratteri. |

## <a name="time-series"></a>Serie temporale

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.ExponentialAverageTransform> | Accetta una media ponderata dei valori: ExpAvg(y_t) = a * y_t + (1-a) * ExpAvg(y_(t-1)). |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.IidChangePointDetector> | Implementa la trasformazione di rilevamento del punto di modifica per una sequenza i.i.d. (campione casuale) in base alla stima kernel di densità adattiva e alle martingale. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.IidSpikeDetector> | Implementa la trasformazione di rilevamento del picco per una sequenza i.i.d. (campione casuale) in base alla stima kernel di densità adattiva. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.MovingAverageTransform> | Offre una media ponderata dei valori della finestra temporale scorrevole. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.PercentileThresholdTransform> | Determina se il valore corrente della serie temporale appartiene al percentile dei valori massimi della finestra temporale scorrevole. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.PValueTransform> | Calcola il livello di significatività empirico del valore corrente della serie in base agli altri valori presenti nella finestra temporale scorrevole. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SlidingWindowTransform> | Restituisce una finestra temporale scorrevole in una serie temporale di tipo Single. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SsaChangePointDetector> | Implementa la trasformazione di rilevamento del punto di modifica in base alla modellazione Singular Spectrum della serie temporale. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SsaSpikeDetector> | Implementa la trasformazione di rilevamento del picco in base alla modellazione Singular Spectrum della serie temporale. |

## <a name="miscellaneous"></a>Varie

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | Crea una trasformazione dati composita. |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | Genera colonne aggiuntive all'elemento `IDataView` specificato. Non modifica il numero di righe e può essere vista come un risultato dell'applicazione della funzione dell'utente a ogni riga dei dati di input.|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | Aggiunge una colonna con una sequenza di numeri generata. |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | Produce una colonna con l'ID del cursore come colonna. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Genera un numero casuale. |
| <xref:Microsoft.ML.Transforms.ScoringTransformer> | Combina le informazioni provenienti da più modelli predittivi per generare un nuovo modello nella pipeline usando i punteggi restituiti da un modello già sottoposto a training. |
