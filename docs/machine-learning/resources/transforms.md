---
title: Trasformazioni dati
description: Esplorare le diverse trasformazioni dati supportate in ML.NET.
ms.date: 08/08/2018
author: jralexander
ms.author: johalex
ms.openlocfilehash: 3c483f4a263052eb15435775a47f514893eee049
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519395"
---
# <a name="data-transforms"></a>Trasformazioni dati

Le tabelle seguenti contengono informazioni su tutte le trasformazioni dati supportate in ML.NET (selezionare il tipo di trasformazione dati per passare alla tabella corrispondente):

* [Categorie](#categorical)
* [Combinatori e separatori](#combiners-and-segregators)
* [Selezione funzionalità](#feature-selection)
* [Algoritmi di estrazione funzionalità](#featurizers)
* [Analisi etichette](#label-parsing)
* [Valori mancanti](#missing-values)
* [Normalizzazione](#normalization)
* [Filtri di riga](#row-filters)
* [Schema](#schema)
* [Elaborazione testo ed estrazione funzionalità](#text-processing-and-featurization)
* [Varie](#miscellaneous)

> [!NOTE]
> ML.NET è attualmente in anteprima. Non tutte le trasformazioni dati sono attualmente supportate. Per inviare una richiesta per una determinata trasformazione, aprire un problema nel repository GitHub [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="categorical"></a>Categorie

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CategoricalHashOneHotVectorizer> | Codifica la variabile categorica con la codifica basata su hash. |
| <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer> | Codifica la variabile categorica con la codifica one-hot in base a un dizionario di termini. |

## <a name="combiners-and-segregators"></a>Combinatori e separatori

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CombinerByContiguousGroupId> | Raggruppa i valori di una colonna scalare in un vettore in base a un ID gruppo contiguo. |
| <xref:Microsoft.ML.Transforms.FeatureCombiner> | Combina tutte le funzionalità in una colonna funzionalità. |
| <xref:Microsoft.ML.Transforms.ManyHeterogeneousModelCombiner> | Combina una sequenza di oggetti TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |
| <xref:Microsoft.ML.Transforms.ModelCombiner> | Combina una sequenza di oggetti TransformModel in un singolo modello. |
| <xref:Microsoft.ML.Transforms.Segregator> | Separa le colonne vettore in sequenze di righe, operazione inversa del raggruppamento trasformazione. |
| <xref:Microsoft.ML.Transforms.TwoHeterogeneousModelCombiner> | Combina un oggetto TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |

## <a name="feature-selection"></a>Selezione funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByCount> | Seleziona gli slot per i quali il conteggio dei valori non predefiniti è maggiore o uguale a una determinata soglia. |
| <xref:Microsoft.ML.Transforms.FeatureSelectorByMutualInformation> | Seleziona gli slot top k in tutte le colonne specificate ordinate in base alle relative informazioni reciproche con la colonna etichetta. |

## <a name="featurizers"></a>Algoritmi di estrazione funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.HashConverter> | Converte i valori colonna in hash. Questa trasformazione accetta input numerici e di testo, sia con colonne singole che vettoriali. |
| <xref:Microsoft.ML.Transforms.TreeLeafFeaturizer> | Esegue il training di un ensemble di alberi o lo carica da un file, quindi esegue il mapping di un vettore delle caratteristiche numerico a tre output: 1. Un vettore che contiene i singoli output dell'albero dell'ensemble di alberi. 2. Un vettore che indica le foglie su cui si basa il vettore delle caratteristiche nell'ensemble di alberi. 3. Un vettore che indica i percorsi su cui si basa il vettore delle caratteristiche nell'ensemble di alberi. Se vengono specificati sia un file di modello che un algoritmo di training, il vettore userà il file di modello. Se non viene specificato alcun elemento, il vettore eseguirà il training di un modello FastTree predefinito. In questo modo è possibile gestire le etichette chiave eseguendo il training di un modello di regressione rispetto ai relativi indici permutati facoltativamente. |

## <a name="label-parsing"></a>Analisi etichette

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Dictionarizer> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |
| <xref:Microsoft.ML.Transforms.LabelColumnKeyBooleanConverter> | Trasforma l'etichetta in chiave o bool (se necessario) per renderla appropriata per la classificazione. |
| <xref:Microsoft.ML.Transforms.LabelIndicator> | Remapper di etichette usato da OVA. |
| <xref:Microsoft.ML.Transforms.LabelToFloatConverter> | Trasforma l'etichetta in float per renderla appropriata per la regressione. |
| <xref:Microsoft.ML.Transforms.PredictedLabelColumnOriginalValueConverter> | Trasforma una colonna etichetta stimata nei relativi valori originali, a meno che non sia di tipo bool. |

## <a name="missing-values"></a>Valori mancanti

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueHandler> | Consente di gestire i valori mancanti sostituendoli con il valore predefinito o con il valore medio/min/max (solo per le colonne non di testo). È possibile facoltativamente concatenare una colonna indicatore, se il tipo di colonna di input è numerico. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicator> | Consente di creare una colonna di output booleana con lo stesso numero di slot della colonna di input in cui il valore di output è true se manca il valore nella colonna di input. |
| <xref:Microsoft.ML.Transforms.MissingValuesDropper> | Rimuove le righe NA dalle colonne vettore. |
| <xref:Microsoft.ML.Transforms.MissingValuesRowDropper> | Esclude tramite filtro le righe contenenti valori mancanti. |
| <xref:Microsoft.ML.Transforms.MissingValueSubstitutor> | Consente di creare una colonna di output dello stesso tipo e dimensioni della colonna di input, in cui i valori mancanti vengono sostituiti con il valore predefinito o con il valore medio/min/max (solo per le colonne non di testo). |

## <a name="normalization"></a>Normalization

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BinNormalizer> | I valori vengono assegnati in bin di isodensità e viene eseguito il mapping di un valore ai relativi elementi bin_number/number_of_bins. |
| <xref:Microsoft.ML.Transforms.ConditionalNormalizer> | Normalizza le colonne solo se necessario. |
| <xref:Microsoft.ML.Transforms.GlobalContrastNormalizer> | Esegue una normalizzazione del contrasto globale nei valori di input: Y = (s * X - M) / D, dove s è una scala, M è la media e D è la norma L2 o la deviazione standard. | 
| <xref:Microsoft.ML.Transforms.LogMeanVarianceNormalizer> | Normalizza i dati in base alla media calcolata e alla varianza del logaritmo dei dati. |
| <xref:Microsoft.ML.Transforms.LpNormalizer> | Normalizza i vettori (righe) singolarmente ridimensionandoli in base a una norma unitaria (L2, L1 o LInf). Esegue l'operazione seguente su un vettore X: Y = (X - M) / D, in cui M è la media e D è la norma L2, la norma L1 o la norma LInf. |
| <xref:Microsoft.ML.Transforms.MeanVarianceNormalizer> | Normalizza i dati in base alla media calcolata e alla varianza dei dati. |
| <xref:Microsoft.ML.Transforms.MinMaxNormalizer> | Normalizza i dati in base ai valori minimo e massimo osservati dei dati. |
| <xref:Microsoft.ML.Transforms.SupervisedBinNormalizer> | Analogo a <xref:Microsoft.ML.Transforms.BinNormalizer>, ma calcola i bin in base alla correlazione con la colonna etichetta e non l'isodensità. Il nuovo valore è bin_number/number_of_bins. |

## <a name="row-filters"></a>Filtri di riga

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowRangeFilter> | Filtra una vista dati in una colonna di tipo Single, Double o Key (contigua). Mantiene i valori che sono compresi nell'intervallo min/max specificato. Le righe NaN vengono sempre escluse tramite filtro. Se l'input è di tipo Key, i valori min/max vengono considerati percentuali del numero di valori. |
| <xref:Microsoft.ML.Transforms.RowSkipAndTakeFilter> | Consente di limitare l'input a un subset di righe in un offset facoltativo. Può essere usato per implementare il paging dei dati. |
| <xref:Microsoft.ML.Transforms.RowSkipFilter> | Consente di limitare l'input a un subset di righe ignorando un numero di righe. |
| <xref:Microsoft.ML.Transforms.RowTakeFilter> | Consente di limitare l'input a un subset di righe accettando le prime N righe. |

## <a name="schema"></a>Schema

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnConcatenator> | Concatena due colonne dello stesso tipo di elemento. |
| <xref:Microsoft.ML.Transforms.ColumnCopier> | Duplica le colonne dal set di dati.|
| <xref:Microsoft.ML.Transforms.ColumnDropper> | Elimina le colonne dal set di dati. |
| <xref:Microsoft.ML.Transforms.ColumnSelector> | Seleziona un set di colonne, eliminando tutte le altre. |
| <xref:Microsoft.ML.Transforms.ColumnTypeConverter> | Converte una colonna in un tipo diverso, usando le conversioni standard. |
| <xref:Microsoft.ML.Transforms.KeyToTextConverter> | KeyToValueTransform utilizza i metadati KeyValues per eseguire il mapping degli indici di chiave ai valori corrispondenti nei metadati KeyValues. |
| <xref:Microsoft.ML.Transforms.NGramTranslator> | Produce un elenco di conteggi di n-grammi (sequenze di valori consecutivi di lunghezza 1-n) in un vettore specifico di chiavi. Tale operazione viene eseguita creando un dizionario di n-grammi e usando l'ID nel dizionario come indice nell'elenco. | 
| <xref:Microsoft.ML.Transforms.OptionalColumnCreator> | Se dopo la deserializzazione la colonna di origine non esiste, creare una colonna con il tipo corretto e i valori predefiniti. |

## <a name="text-processing-and-featurization"></a>Elaborazione testo ed estrazione funzionalità

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CharacterTokenizer> | Tokenizer orientato ai caratteri in cui il testo viene considerato una sequenza di caratteri. |
| <xref:Microsoft.ML.Transforms.TextFeaturizer> | Una trasformazione che converte una raccolta di documenti di testo in vettori delle caratteristiche numerici. I vettori delle caratteristiche sono conteggi normalizzati di n-grammi (parola e/o carattere) in un determinato testo in formato token. |
| <xref:Microsoft.ML.Transforms.TextToKeyConverter> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |
| <xref:Microsoft.ML.Transforms.WordEmbeddings> | Una trasformazione che converte i vettori di token di testo in vettori numerici usando un modello con pre-training. Per altre informazioni sulla tecnica, vedere la pagina di Wikipedia [Word embedding](https://en.wikipedia.org/wiki/Word_embedding). |
| <xref:Microsoft.ML.Transforms.WordTokenizer> | L'input per questa trasformazione è testo e l'output è un vettore di testo che contiene le parole (token) nel testo originale. Il separatore è uno spazio, ma è possibile specificare qualsiasi altro carattere (o più caratteri). |

## <a name="miscellaneous"></a>Varie

| Transform | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ApproximateBootstrapSampler> | Campionamento bootstrap approssimativo. |
| <xref:Microsoft.ML.Transforms.BinaryPredictionScoreColumnsRenamer> | Per la stima binaria rinomina le colonne PredictedLabel e Score per includere il nome della classe positiva.|
| <xref:Microsoft.ML.Transforms.DataCache> | Memorizza nella cache usando l'opzione cache specificata. |
| <xref:Microsoft.ML.Transforms.DatasetScorer> | Assegna un punteggio a un set di dati con un modello predittivo. |
| <xref:Microsoft.ML.Transforms.DatasetTransformScorer> | Assegna un punteggio a un set di dati con un modello di trasformazione. |
| <xref:Microsoft.ML.Transforms.NoOperation> | Non effettua alcuna operazione. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Aggiunge una colonna con una sequenza di numeri generata. |
| <xref:Microsoft.ML.Transforms.ScoreColumnSelector> | Seleziona solo le ultime colonne punteggio e le colonne aggiuntive specificate negli argomenti. |
| <xref:Microsoft.ML.Transforms.Scorer> | Trasforma il modello predittivo in un modello di trasformazione. |
| <xref:Microsoft.ML.Transforms.SentimentAnalyzer> | Usa un modello di sentiment con pre-training per assegnare un punteggio alle stringhe di input. |
| <xref:Microsoft.ML.Transforms.TrainTestDatasetSplitter> | Suddivide il set di dati in set di training e di test. |
