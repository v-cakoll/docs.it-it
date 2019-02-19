---
title: Concetti di base per il training dei modelli in ML.NET
description: Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET. Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.
ms.date: 02/13/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c47d5832527dca1416abfc55756dca48f1daf493
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303660"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a>Concetti di base per il training dei modelli in ML.NET

Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET. Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.

## <a name="model-training-concepts"></a>Concetti relativi al training dei modelli

Questo documento illustra i concetti seguenti relativi al training dei modelli in ML.NET:

- [*Dati* ](#data) rappresentati come interfaccia `IDataView`.
  - In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita (lazy), non modificabile, con supporto dei cursori, eterogeneo e schematizzato. 
  - Un documento eccellente sull'interfaccia dati è [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principi di progettazione per IDataView).
- [*Trasformatore*](#transformer) rappresentato come interfaccia `ITransformer`.
  - Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.
  - Ad esempio, è possibile considerare un modello di Machine Learning come un trasformatore che accetta caratteristiche e restituisce previsioni.
  - Un altro esempio è un tokenizer di testo che accetta una singola colonna di testo e restituisce una colonna vettore con singole parole estratte dal testo.
- [*Lettore dati* ](#data-reader) rappresentato come interfaccia `IDataReader<T>`.
  - Il lettore dati è un componente ML.NET per creare i dati. Richiede un'istanza di `T` e restituisce dati da tale istanza. 
  - Ad esempio, un *TextLoader* è un `IDataReader<IMultiStreamSource>`. Accetta l'origine e produce dati. 
- [*Strumento di stima*](#estimator) rappresentato come interfaccia `IEstimator<T>`.
  - Si tratta di un oggetto che apprende dai dati. Il risultato dell'apprendimento è un *trasformatore*.
  - È possibile considerare un *algoritmo* di Machine Learning come uno strumento di stima che apprende dai dati e produce un *modello* di Machine Learning.
- [*Funzione di stima* ](#prediction-function) rappresentata come classe `PredictionEngine<TSrc, TDst>`.
  - La funzione di stima può essere considerata come una macchina che applica un trasformatore a una riga, come in fase di stima.

## <a name="data"></a>Dati

In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita, con supporto dei cursori, eterogeneo e schematizzato.

- I dati hanno uno *schema* (un'istanza di un'interfaccia `ISchema`) che contiene le informazioni sulle colonne della vista dati.
  - A ogni colonna sono associati *nome*, *tipo* e un set arbitrario di *metadati*.
  - I *metadati* della colonna contengono informazioni quali i nomi degli slot di una colonna vettore e simili. I metadati stessi vengono rappresentati come altri *dati* su riga singola univoci per ogni colonna.
  - La vista dei dati è un'origine di *cursori*. Si pensi ai cursori SQL: un cursore è un oggetto che esegue l'iterazione dei dati, una riga alla volta e presenta i dati disponibili.
  - Naturalmente, per i dati possono esistere molti cursori attivi in base alle esigenze. Dato che i dati stessi non sono modificabili, i cursori sono effettivamente indipendenti.
  - I cursori in genere accedono solo a un subset di colonne: Per motivi di efficienza, ML.NET calcola solo i valori delle colonne necessari per il cursore.

## <a name="transformer"></a>Trasformatore

Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.

La maggior parte dei trasformatori in ML.NET tende a operare su una *colonna di input* alla volta e produce la *colonna di output*. Ad esempio, un `new HashTransformer("bar", "foo")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li inserisce nella colonna "bar". 

È anche comune che i nomi delle colonne di input e output siano uguali. In questo caso, la colonna precedente viene sostituita con quella nuova. Ad esempio, un `new HashTransformer("foo")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li reinserisce in "foo". 

Qualsiasi trasformatore produce una nuova vista dati quando si chiama `Transform`. Tenere presente che le viste dati non sono modificabili.

Un'altra importante considerazione è che, poiché i dati vengono valutati in modo differito (lazy), anche i *trasformatori sono lazy*. In pratica, dopo aver chiamato

```csharp
var newData = transformer.Transform(oldData)
```

non viene eseguito alcun calcolo effettivo. Solo dopo avere ottenuto un cursore da `newData` e aver iniziato a usare il valore `newData` chiama la logica di trasformazione `transformer` (e anche in questo caso, solo se il `transformer` in questione è necessario per produrre le colonne richieste).

### <a name="transformer-chains"></a>Catene di trasformatori

Una proprietà utile di un trasformatore è la *possibilità di compilare un'applicazione sequenziale di trasformatori come un altro trasformatore*:

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

Questa proprietà viene usata comunemente in ML.NET: in genere, il modello ML.NET sottoposto a training è una catena di trasformatori, che è, a tutti gli effetti, un *trasformatore*.

## <a name="data-reader"></a>Lettore dati

Il lettore dati è un componente di ML.NET per la creazione dei dati: accetta un'istanza di `T` e restituisce i dati da tale istanza.

Una proprietà interessante da notare è la possibilità di creare un lettore dati associando un trasformatore a un lettore dati esistente. In questo modo è possibile effettuare il bake del comportamento di trasformazione in un lettore:

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

Un'altra somiglianza con i trasformatori è che, considerata la valutazione differita dei dati, i *lettori sono lazy*: non vengono eseguite letture effettive (oppure solo in minima parte) quando si chiama `reader.Read()`. Solo quando viene richiesto un cursore sui dati risultanti il lettore inizia a lavorare.

## <a name="estimator"></a>Strumento di stima

Lo *strumento di stima* è un oggetto che apprende dai dati. Il risultato dell'apprendimento è un *trasformatore*.

In ML.NET, usare questa proprietà per creare pipeline di apprendimento che concatenano strumenti di stima diversi:

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

Un'importante proprietà degli strumenti di stima è che *sono eager e non lazy*: ogni chiamata di `Fit` causa l'esecuzione dell'apprendimento, che è un'operazione che richiede potenzialmente molto tempo.

## <a name="prediction-function"></a>Funzione di stima

La funzione di stima può essere considerata come un componente che applica un trasformatore a una sola riga.

Dopo aver ottenuto il modello (un *trasformatore* sottoposto a training tramite `Fit()` o caricato da altre posizioni), è possibile usarlo per eseguire stime usando le normali chiamate a `model.Transform(data)`. Tuttavia, quando si usa questo modello in uno scenario reale, spesso non sono disponibili molti esempi su cui basare la stima. Sarà invece disponibile un esempio alla volta e necessario eseguire stime tempestive e immediate su tale esempio.

Naturalmente, è possibile ricorrere alla stima batch:

- Creare una vista dati con esattamente una riga.
- Chiamare `model.Transform(data)` per ottenere la vista dati stimata.
- Ottenere un cursore sui dati risultanti.
- Fare avanzare il cursore di un passaggio per passare alla prima (e unica) riga.
- Estrarre i valori stimati da tale riga.

L'algoritmo precedente può essere implementato tramite la [comprensione dello schema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con due oggetti definiti dall'utente `InputExample` e `OutputPrediction` come indicato di seguito:

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

Si tratta di una soluzione complicata con potenziali costi a livello di prestazioni. Un oggetto funzione di stima esegue invece le stesse operazioni, ma in modo più veloce e pratico, tramite un metodo di estensione `CreatePredictionEngine`:

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

La funzione di stima è *non rientrante e thread-safe*. Se si voglio eseguire stime contemporaneamente con più thread, è necessario disporre di una funzione di stima per ogni thread.
