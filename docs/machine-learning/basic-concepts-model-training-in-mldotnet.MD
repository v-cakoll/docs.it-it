---
title: Concetti di base per il training dei modelli in ML.NET
description: Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET. Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.
ms.date: 03/05/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 78554cfd1dfdb3dba82a325d47245aeb313bb6fe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675563"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="c1e7c-104">Concetti di base per il training dei modelli in ML.NET</span><span class="sxs-lookup"><span data-stu-id="c1e7c-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="c1e7c-105">Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="c1e7c-106">Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

<span data-ttu-id="c1e7c-107">Questo articolo e l'esempio correlato usano attualmente **ML.NET versione 0.10**.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-107">This article and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="c1e7c-108">Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="c1e7c-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="c1e7c-109">Concetti relativi al training dei modelli</span><span class="sxs-lookup"><span data-stu-id="c1e7c-109">Model training concepts</span></span>

<span data-ttu-id="c1e7c-110">Questo documento illustra i concetti seguenti relativi al training dei modelli in ML.NET:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-110">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="c1e7c-111">[*Dati* ](#data) rappresentati come interfaccia `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-111">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="c1e7c-112">In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita (lazy), non modificabile, con supporto dei cursori, eterogeneo e schematizzato.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-112">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="c1e7c-113">Un documento eccellente sull'interfaccia dati è [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principi di progettazione per IDataView).</span><span class="sxs-lookup"><span data-stu-id="c1e7c-113">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="c1e7c-114">[*Trasformatore*](#transformer) rappresentato come interfaccia `ITransformer`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-114">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="c1e7c-115">Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-115">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="c1e7c-116">Ad esempio, è possibile considerare un modello di Machine Learning come un trasformatore che accetta caratteristiche e restituisce previsioni.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-116">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="c1e7c-117">Un altro esempio è un tokenizer di testo che accetta una singola colonna di testo e restituisce una colonna vettore con singole parole estratte dal testo.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-117">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="c1e7c-118">[*Lettore dati* ](#data-reader) rappresentato come interfaccia `IDataReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-118">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="c1e7c-119">Il lettore dati è un componente ML.NET per creare i dati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-119">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="c1e7c-120">Richiede un'istanza di `T` e restituisce dati da tale istanza.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-120">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="c1e7c-121">Ad esempio, un *TextLoader* è un `IDataReader<IMultiStreamSource>`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-121">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="c1e7c-122">Accetta l'origine e produce dati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-122">It takes the source and produces data.</span></span> 
- <span data-ttu-id="c1e7c-123">[*Strumento di stima*](#estimator) rappresentato come interfaccia `IEstimator<T>`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-123">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="c1e7c-124">Si tratta di un oggetto che apprende dai dati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-124">This is an object that learns from data.</span></span> <span data-ttu-id="c1e7c-125">Il risultato dell'apprendimento è un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-125">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="c1e7c-126">È possibile considerare un *algoritmo* di Machine Learning come uno strumento di stima che apprende dai dati e produce un *modello* di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-126">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="c1e7c-127">[*Funzione di stima* ](#prediction-function) rappresentata come classe `PredictionEngine<TSrc, TDst>`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-127">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="c1e7c-128">La funzione di stima può essere considerata come una macchina che applica un trasformatore a una riga, come in fase di stima.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-128">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="c1e7c-129">Dati</span><span class="sxs-lookup"><span data-stu-id="c1e7c-129">Data</span></span>

<span data-ttu-id="c1e7c-130">In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita, con supporto dei cursori, eterogeneo e schematizzato.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-130">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="c1e7c-131">I dati hanno uno *schema* (un'istanza di un'interfaccia `ISchema`) che contiene le informazioni sulle colonne della vista dati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-131">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="c1e7c-132">A ogni colonna sono associati *nome*, *tipo* e un set arbitrario di *metadati*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-132">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="c1e7c-133">I *metadati* della colonna contengono informazioni quali i nomi degli slot di una colonna vettore e simili.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-133">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="c1e7c-134">I metadati stessi vengono rappresentati come altri *dati* su riga singola univoci per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-134">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="c1e7c-135">La vista dei dati è un'origine di *cursori*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-135">The data view is a source of *cursors*.</span></span> <span data-ttu-id="c1e7c-136">Si pensi ai cursori SQL: un cursore è un oggetto che esegue l'iterazione dei dati, una riga alla volta e presenta i dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-136">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="c1e7c-137">Naturalmente, per i dati possono esistere molti cursori attivi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-137">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="c1e7c-138">Dato che i dati stessi non sono modificabili, i cursori sono effettivamente indipendenti.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-138">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="c1e7c-139">I cursori in genere accedono solo a un subset di colonne: Per motivi di efficienza, ML.NET calcola solo i valori delle colonne necessari per il cursore.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-139">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="c1e7c-140">Trasformatore</span><span class="sxs-lookup"><span data-stu-id="c1e7c-140">Transformer</span></span>

<span data-ttu-id="c1e7c-141">Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-141">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="c1e7c-142">La maggior parte dei trasformatori in ML.NET tende a operare su una *colonna di input* alla volta e produce la *colonna di output*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-142">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="c1e7c-143">Ad esempio, un `new HashTransformer("bar", "foo")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li inserisce nella colonna "bar".</span><span class="sxs-lookup"><span data-stu-id="c1e7c-143">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="c1e7c-144">È anche comune che i nomi delle colonne di input e output siano uguali.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-144">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="c1e7c-145">In questo caso, la colonna precedente viene sostituita con quella nuova.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-145">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="c1e7c-146">Ad esempio, un `new HashTransformer("foo")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li reinserisce in "foo".</span><span class="sxs-lookup"><span data-stu-id="c1e7c-146">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="c1e7c-147">Qualsiasi trasformatore produce una nuova vista dati quando si chiama `Transform`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-147">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="c1e7c-148">Tenere presente che le viste dati non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-148">Remember, data views are immutable.</span></span>

<span data-ttu-id="c1e7c-149">Un'altra importante considerazione è che, poiché i dati vengono valutati in modo differito (lazy), anche i *trasformatori sono lazy*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-149">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="c1e7c-150">In pratica, dopo aver chiamato</span><span class="sxs-lookup"><span data-stu-id="c1e7c-150">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="c1e7c-151">non viene eseguito alcun calcolo effettivo.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-151">no actual computation happens.</span></span> <span data-ttu-id="c1e7c-152">Solo dopo avere ottenuto un cursore da `newData` e aver iniziato a usare il valore `newData` chiama la logica di trasformazione `transformer` (e anche in questo caso, solo se il `transformer` in questione è necessario per produrre le colonne richieste).</span><span class="sxs-lookup"><span data-stu-id="c1e7c-152">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="c1e7c-153">Catene di trasformatori</span><span class="sxs-lookup"><span data-stu-id="c1e7c-153">Transformer chains</span></span>

<span data-ttu-id="c1e7c-154">Una proprietà utile di un trasformatore è la *possibilità di compilare un'applicazione sequenziale di trasformatori come un altro trasformatore*:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-154">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="c1e7c-155">Questa proprietà viene usata comunemente in ML.NET: in genere, il modello ML.NET sottoposto a training è una catena di trasformatori, che è, a tutti gli effetti, un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-155">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="c1e7c-156">Lettore dati</span><span class="sxs-lookup"><span data-stu-id="c1e7c-156">Data reader</span></span>

<span data-ttu-id="c1e7c-157">Il lettore dati è un componente di ML.NET per la creazione dei dati: accetta un'istanza di `T` e restituisce i dati da tale istanza.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-157">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="c1e7c-158">Una proprietà interessante da notare è la possibilità di creare un lettore dati associando un trasformatore a un lettore dati esistente.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-158">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="c1e7c-159">In questo modo è possibile effettuare il bake del comportamento di trasformazione in un lettore:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-159">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="c1e7c-160">Un'altra somiglianza con i trasformatori è che, considerata la valutazione differita dei dati, i *lettori sono lazy*: non vengono eseguite letture effettive (oppure solo in minima parte) quando si chiama `reader.Read()`. Solo quando viene richiesto un cursore sui dati risultanti il lettore inizia a lavorare.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-160">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="c1e7c-161">Strumento di stima</span><span class="sxs-lookup"><span data-stu-id="c1e7c-161">Estimator</span></span>

<span data-ttu-id="c1e7c-162">Lo *strumento di stima* è un oggetto che apprende dai dati.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-162">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="c1e7c-163">Il risultato dell'apprendimento è un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-163">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="c1e7c-164">In ML.NET, usare questa proprietà per creare pipeline di apprendimento che concatenano strumenti di stima diversi:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-164">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

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

<span data-ttu-id="c1e7c-165">Un'importante proprietà degli strumenti di stima è che *sono eager e non lazy*: ogni chiamata di `Fit` causa l'esecuzione dell'apprendimento, che è un'operazione che richiede potenzialmente molto tempo.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-165">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="c1e7c-166">Funzione di stima</span><span class="sxs-lookup"><span data-stu-id="c1e7c-166">Prediction function</span></span>

<span data-ttu-id="c1e7c-167">La funzione di stima può essere considerata come un componente che applica un trasformatore a una sola riga.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-167">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="c1e7c-168">Dopo aver ottenuto il modello (un *trasformatore* sottoposto a training tramite `Fit()` o caricato da altre posizioni), è possibile usarlo per eseguire stime usando le normali chiamate a `model.Transform(data)`.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-168">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="c1e7c-169">Tuttavia, quando si usa questo modello in uno scenario reale, spesso non sono disponibili molti esempi su cui basare la stima.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-169">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="c1e7c-170">Sarà invece disponibile un esempio alla volta e necessario eseguire stime tempestive e immediate su tale esempio.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-170">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="c1e7c-171">Naturalmente, è possibile ricorrere alla stima batch:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-171">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="c1e7c-172">Creare una vista dati con esattamente una riga.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-172">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="c1e7c-173">Chiamare `model.Transform(data)` per ottenere la vista dati stimata.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-173">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="c1e7c-174">Ottenere un cursore sui dati risultanti.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-174">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="c1e7c-175">Fare avanzare il cursore di un passaggio per passare alla prima (e unica) riga.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-175">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="c1e7c-176">Estrarre i valori stimati da tale riga.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-176">Extract the predicted values out of it.</span></span>

<span data-ttu-id="c1e7c-177">L'algoritmo precedente può essere implementato tramite la [comprensione dello schema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con due oggetti definiti dall'utente `InputExample` e `OutputPrediction` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-177">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="c1e7c-178">Si tratta di una soluzione complicata con potenziali costi a livello di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-178">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="c1e7c-179">Un oggetto funzione di stima esegue invece le stesse operazioni, ma in modo più veloce e pratico, tramite un metodo di estensione `CreatePredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="c1e7c-179">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="c1e7c-180">La funzione di stima è *non rientrante e thread-safe*.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-180">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="c1e7c-181">Se si voglio eseguire stime contemporaneamente con più thread, è necessario disporre di una funzione di stima per ogni thread.</span><span class="sxs-lookup"><span data-stu-id="c1e7c-181">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
