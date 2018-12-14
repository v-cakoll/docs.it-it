---
title: Trasformazioni dati in ML.NET
description: Esplorare le diverse trasformazioni dati supportate in ML.NET.
author: JRAlexander
ms.date: 10/16/2018
ms.openlocfilehash: c169319937dac13747935e451952bd75d4cc174d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143948"
---
# <a name="data-transforms-in-mlnet"></a>Trasformazioni dati in ML.NET

Le tabelle seguenti contengono informazioni su tutte le trasformazioni dati supportate in ML.NET (selezionare il tipo di trasformazione dati per passare alla tabella corrispondente):

* [Categorie](#categorical)
* [Combinatori e separatori](#combiners-and-segregators)
* [Selezione delle caratteristiche](#feature-selection)
* [Algoritmi di estrazione delle caratteristiche](#featurizers)
* [Analisi etichette](#label-parsing)
* [Valori mancanti](#missing-values)
* [Normalizzazione](#normalization)
* [Filtri di riga](#row-filters)
* [Schema](#schema)
* [Elaborazione di testo ed estrazione delle caratteristiche](#text-processing-and-featurization)
* [Varie](#miscellaneous)

> [!NOTE]
> ML.NET è attualmente in anteprima. Non tutte le trasformazioni dati sono attualmente supportate. Per inviare una richiesta per una determinata trasformazione, aprire un problema nel repository GitHub [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="categorical"></a>Categorie

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.CategoricalHashOneHotVectorizer> | Codifica la variabile categorica con la codifica basata su hash. |
| <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer> | Codifica la variabile categorica con la codifica one-hot in base a un dizionario di termini. |

## <a name="combiners-and-segregators"></a>Combinatori e separatori

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.CombinerByContiguousGroupId> | Raggruppa i valori di una colonna scalare in un vettore in base a un ID gruppo contiguo. |
| <xref:Microsoft.ML.Legacy.Transforms.FeatureCombiner> | Combina tutte le caratteristiche in una colonna. |
| <xref:Microsoft.ML.Legacy.Transforms.ManyHeterogeneousModelCombiner> | Combina una sequenza di oggetti TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |
| <xref:Microsoft.ML.Legacy.Transforms.ModelCombiner> | Combina una sequenza di oggetti TransformModel in un singolo modello. |
| <xref:Microsoft.ML.Legacy.Transforms.Segregator> | Separa le colonne vettore in sequenze di righe, operazione inversa del raggruppamento trasformazione. |
| <xref:Microsoft.ML.Legacy.Transforms.TwoHeterogeneousModelCombiner> | Combina un oggetto TransformModel e un oggetto PredictorModel in un singolo oggetto PredictorModel. |

## <a name="feature-selection"></a>Selezione delle caratteristiche

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.FeatureSelectorByCount> | Seleziona gli slot per i quali il conteggio dei valori non predefiniti è maggiore o uguale a una determinata soglia. |
| <xref:Microsoft.ML.Legacy.Transforms.FeatureSelectorByMutualInformation> | Seleziona gli slot top k in tutte le colonne specificate ordinate in base alle relative informazioni reciproche con la colonna etichetta. |

## <a name="featurizers"></a>Algoritmi di estrazione delle caratteristiche

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.HashConverter> | Converte i valori colonna in hash. Questa trasformazione accetta input numerici e di testo, sia con colonne singole che vettoriali. |
| <xref:Microsoft.ML.Legacy.Transforms.TreeLeafFeaturizer> | Esegue il training di un ensemble di alberi o lo carica da un file, quindi esegue il mapping di un vettore delle caratteristiche numerico a tre output: 1. Un vettore che contiene i singoli output dell'albero dell'ensemble di alberi. 2. Un vettore che indica le foglie su cui si basa il vettore delle caratteristiche nell'ensemble di alberi. 3. Un vettore che indica i percorsi su cui si basa il vettore delle caratteristiche nell'ensemble di alberi. Se vengono specificati sia un file di modello che un algoritmo di training, il vettore userà il file di modello. Se non viene specificato alcun elemento, il vettore eseguirà il training di un modello FastTree predefinito. In questo modo è possibile gestire le etichette chiave eseguendo il training di un modello di regressione rispetto ai relativi indici permutati facoltativamente. |

## <a name="label-parsing"></a>Analisi etichette

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.Dictionarizer> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |
| <xref:Microsoft.ML.Legacy.Transforms.LabelColumnKeyBooleanConverter> | Trasforma l'etichetta in chiave o bool (se necessario) per renderla appropriata per la classificazione. |
| <xref:Microsoft.ML.Legacy.Transforms.LabelIndicator> | Remapper di etichette usato da OVA. |
| <xref:Microsoft.ML.Legacy.Transforms.LabelToFloatConverter> | Trasforma l'etichetta in float per renderla appropriata per la regressione. |
| <xref:Microsoft.ML.Legacy.Transforms.PredictedLabelColumnOriginalValueConverter> | Trasforma una colonna etichetta stimata nei relativi valori originali, a meno che non sia di tipo bool. |

## <a name="missing-values"></a>Valori mancanti

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.MissingValueHandler> | Consente di gestire i valori mancanti sostituendoli con il valore predefinito o con il valore medio/min/max (solo per le colonne non di testo). È possibile facoltativamente concatenare una colonna indicatore, se il tipo di colonna di input è numerico. |
| <xref:Microsoft.ML.Legacy.Transforms.MissingValueIndicator> | Consente di creare una colonna di output booleana con lo stesso numero di slot della colonna di input in cui il valore di output è true se manca il valore nella colonna di input. |
| <xref:Microsoft.ML.Legacy.Transforms.MissingValuesDropper> | Rimuove le righe NA dalle colonne vettore. |
| <xref:Microsoft.ML.Legacy.Transforms.MissingValuesRowDropper> | Esclude tramite filtro le righe contenenti valori mancanti. |
| <xref:Microsoft.ML.Legacy.Transforms.MissingValueSubstitutor> | Consente di creare una colonna di output dello stesso tipo e dimensioni della colonna di input, in cui i valori mancanti vengono sostituiti con il valore predefinito o con il valore medio/min/max (solo per le colonne non di testo). |

## <a name="normalization"></a>Normalization

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.BinNormalizer> | I valori vengono assegnati in bin di isodensità e viene eseguito il mapping di un valore ai relativi elementi bin_number/number_of_bins. |
| <xref:Microsoft.ML.Legacy.Transforms.ConditionalNormalizer> | Normalizza le colonne solo se necessario. |
| <xref:Microsoft.ML.Legacy.Transforms.GlobalContrastNormalizer> | Esegue una normalizzazione del contrasto globale nei valori di input: Y = (s * X - M) / D, dove s è una scala, M è la media e D è la norma L2 o la deviazione standard. | 
| <xref:Microsoft.ML.Legacy.Transforms.LogMeanVarianceNormalizer> | Normalizza i dati in base alla media calcolata e alla varianza del logaritmo dei dati. |
| <xref:Microsoft.ML.Legacy.Transforms.LpNormalizer> | Normalizza i vettori (righe) singolarmente ridimensionandoli in base a una norma unitaria (L2, L1 o LInf). Esegue l'operazione seguente su un vettore X: Y = (X - M) / D, in cui M è la media e D è la norma L2, la norma L1 o la norma LInf. |
| <xref:Microsoft.ML.Legacy.Transforms.MeanVarianceNormalizer> | Normalizza i dati in base alla media calcolata e alla varianza dei dati. |
| <xref:Microsoft.ML.Legacy.Transforms.MinMaxNormalizer> | Normalizza i dati in base ai valori minimo e massimo osservati dei dati. |

## <a name="row-filters"></a>Filtri di riga

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.RowRangeFilter> | Filtra una vista dati in una colonna di tipo Single, Double o Key (contigua). Mantiene i valori che sono compresi nell'intervallo min/max specificato. Le righe NaN vengono sempre escluse tramite filtro. Se l'input è di tipo Key, i valori min/max vengono considerati percentuali del numero di valori. |
| <xref:Microsoft.ML.Legacy.Transforms.RowSkipAndTakeFilter> | Consente di limitare l'input a un subset di righe in un offset facoltativo. Può essere usato per implementare il paging dei dati. |
| <xref:Microsoft.ML.Legacy.Transforms.RowSkipFilter> | Consente di limitare l'input a un subset di righe ignorando un numero di righe. |
| <xref:Microsoft.ML.Legacy.Transforms.RowTakeFilter> | Consente di limitare l'input a un subset di righe accettando le prime N righe. |

## <a name="schema"></a>Schema

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> | Concatena due colonne dello stesso tipo di elemento. |
| <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier> | Duplica le colonne dal set di dati.|
| <xref:Microsoft.ML.Legacy.Transforms.ColumnDropper> | Elimina le colonne dal set di dati. |
| <xref:Microsoft.ML.Legacy.Transforms.ColumnSelector> | Seleziona un set di colonne, eliminando tutte le altre. |
| <xref:Microsoft.ML.Legacy.Transforms.ColumnTypeConverter> | Converte una colonna in un tipo diverso, usando le conversioni standard. |
| <xref:Microsoft.ML.Legacy.Transforms.KeyToTextConverter> | KeyToValueTransform utilizza i metadati KeyValues per eseguire il mapping degli indici di chiave ai valori corrispondenti nei metadati KeyValues. |
| <xref:Microsoft.ML.Legacy.Transforms.NGramTranslator> | Produce un elenco di conteggi di n-grammi (sequenze di valori consecutivi di lunghezza 1-n) in un vettore specifico di chiavi. Tale operazione viene eseguita creando un dizionario di n-grammi e usando l'ID nel dizionario come indice nell'elenco. | 
| <xref:Microsoft.ML.Legacy.Transforms.OptionalColumnCreator> | Se dopo la deserializzazione la colonna di origine non esiste, creare una colonna con il tipo corretto e i valori predefiniti. |

## <a name="text-processing-and-featurization"></a>Elaborazione di testo ed estrazione delle caratteristiche

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.CharacterTokenizer> | Tokenizer orientato ai caratteri in cui il testo viene considerato una sequenza di caratteri. |
| <xref:Microsoft.ML.Legacy.Transforms.TextFeaturizer> | Una trasformazione che converte una raccolta di documenti di testo in vettori delle caratteristiche numerici. I vettori delle caratteristiche sono conteggi normalizzati di n-grammi (parola e/o carattere) in un determinato testo in formato token. |
| <xref:Microsoft.ML.Legacy.Transforms.TextToKeyConverter> | Converte i valori di input (parole, numeri e così via) da indicizzare in un dizionario. |
| <xref:Microsoft.ML.Legacy.Transforms.WordEmbeddings> | Una trasformazione che converte i vettori di token di testo in vettori numerici usando un modello con pre-training. Per altre informazioni sulla tecnica, vedere la pagina di Wikipedia [Word embedding](https://en.wikipedia.org/wiki/Word_embedding). |
| <xref:Microsoft.ML.Legacy.Transforms.WordTokenizer> | L'input per questa trasformazione è testo e l'output è un vettore di testo che contiene le parole (token) nel testo originale. Il separatore è uno spazio, ma è possibile specificare qualsiasi altro carattere (o più caratteri). |

## <a name="miscellaneous"></a>Varie

| Trasformazione | Definizione |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.ApproximateBootstrapSampler> | Campionamento bootstrap approssimativo. |
| <xref:Microsoft.ML.Legacy.Transforms.BinaryPredictionScoreColumnsRenamer> | Per la stima binaria rinomina le colonne PredictedLabel e Score per includere il nome della classe positiva.|
| <xref:Microsoft.ML.Legacy.Transforms.DataCache> | Memorizza nella cache usando l'opzione cache specificata. |
| <xref:Microsoft.ML.Legacy.Transforms.DatasetScorer> | Assegna un punteggio a un set di dati con un modello predittivo. |
| <xref:Microsoft.ML.Legacy.Transforms.DatasetTransformScorer> | Assegna un punteggio a un set di dati con un modello di trasformazione. |
| <xref:Microsoft.ML.Legacy.Transforms.NoOperation> | Non effettua alcuna operazione. |
| <xref:Microsoft.ML.Legacy.Transforms.RandomNumberGenerator> | Aggiunge una colonna con una sequenza di numeri generata. |
| <xref:Microsoft.ML.Legacy.Transforms.ScoreColumnSelector> | Seleziona solo le ultime colonne punteggio e le colonne aggiuntive specificate negli argomenti. |
| <xref:Microsoft.ML.Legacy.Transforms.Scorer> | Trasforma il modello predittivo in un modello di trasformazione. |
| <xref:Microsoft.ML.Legacy.Transforms.SentimentAnalyzer> | Usa un modello di sentiment con pre-training per assegnare un punteggio alle stringhe di input. |
| <xref:Microsoft.ML.Legacy.Transforms.TrainTestDatasetSplitter> | Suddivide il set di dati in set di training e di test. |
