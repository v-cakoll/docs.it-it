---
title: Concetti di base per il training dei modelli in ML.NET
description: Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET. Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.
ms.date: 11/06/2018
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: cff833b45583bc752bb42616820a95ca6c5c6b12
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "55252440"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="d6cc6-104">Concetti di base per il training dei modelli in ML.NET</span><span class="sxs-lookup"><span data-stu-id="d6cc6-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="d6cc6-105">Questo articolo illustra i concetti di base relativi agli scenari di *training dei modelli* in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="d6cc6-106">Non tutti i concetti sono rilevanti per lo scenario più semplice di *stima con un modello esistente*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-106">Not all concepts are relevant to the more simple scenario of *prediction with existing model*.</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="d6cc6-107">Concetti relativi al training dei modelli</span><span class="sxs-lookup"><span data-stu-id="d6cc6-107">Model training concepts</span></span>

<span data-ttu-id="d6cc6-108">Questo documento illustra i concetti seguenti relativi al training dei modelli in ML.NET:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-108">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="d6cc6-109">[*Dati* ](#data) rappresentati come interfaccia `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-109">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="d6cc6-110">In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita (lazy), non modificabile, con supporto dei cursori, eterogeneo e schematizzato.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-110">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="d6cc6-111">Un documento eccellente sull'interfaccia dati è [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md) (Principi di progettazione per IDataView).</span><span class="sxs-lookup"><span data-stu-id="d6cc6-111">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="d6cc6-112">[*Trasformatore*](#transformer) rappresentato come interfaccia `ITransformer`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-112">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="d6cc6-113">Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-113">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="d6cc6-114">Ad esempio, è possibile considerare un modello di Machine Learning come un trasformatore che accetta caratteristiche e restituisce previsioni.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-114">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="d6cc6-115">Un altro esempio è un tokenizer di testo che accetta una singola colonna di testo e restituisce una colonna vettore con singole parole estratte dal testo.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-115">Another example, text tokenizer takes a single text column and output a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="d6cc6-116">[*Lettore dati* ](#data-reader) rappresentato come interfaccia `IDataReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-116">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="d6cc6-117">Il lettore dati è un componente ML.NET per creare i dati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-117">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="d6cc6-118">Richiede un'istanza di `T` e restituisce dati da tale istanza.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-118">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="d6cc6-119">Ad esempio, un *TextLoader* è un `IDataReader<FileSource>`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-119">For example, a *TextLoader* is an `IDataReader<FileSource>`.</span></span> <span data-ttu-id="d6cc6-120">Accetta l'origine file e produce dati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-120">It takes the file source and produces data.</span></span> 
- <span data-ttu-id="d6cc6-121">[*Strumento di stima*](#estimator) rappresentato come interfaccia `IEstimator<T>`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-121">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="d6cc6-122">Si tratta di un oggetto che apprende dai dati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-122">This is an object that learns from data.</span></span> <span data-ttu-id="d6cc6-123">Il risultato dell'apprendimento è un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-123">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="d6cc6-124">È possibile considerare un *algoritmo* di Machine Learning come uno strumento di stima che apprende dai dati e produce un *modello* di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-124">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="d6cc6-125">[*Funzione di stima* ](#prediction-function) rappresentata come classe `PredictionFunction<TSrc, TDst>`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-125">[*Prediction function*](#prediction-function) represented as a `PredictionFunction<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="d6cc6-126">La funzione di stima può essere considerata come una macchina che applica un trasformatore a una riga, come in fase di stima.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-126">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="d6cc6-127">Dati</span><span class="sxs-lookup"><span data-stu-id="d6cc6-127">Data</span></span>

<span data-ttu-id="d6cc6-128">In ML.NET i dati sono simili a una vista SQL: si tratta di un set di dati a valutazione differita, con supporto dei cursori, eterogeneo e schematizzato.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-128">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="d6cc6-129">I dati hanno uno *schema* (un'istanza di un'interfaccia `ISchema`) che contiene le informazioni sulle colonne della vista dati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-129">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="d6cc6-130">A ogni colonna sono associati *nome*, *tipo* e un set arbitrario di *metadati*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-130">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="d6cc6-131">I *metadati* della colonna contengono informazioni quali i nomi degli slot di una colonna vettore e simili.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-131">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="d6cc6-132">I metadati stessi vengono rappresentati come altri *dati* su riga singola univoci per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-132">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="d6cc6-133">La vista dei dati è un'origine di *cursori*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-133">The data view is a source of *cursors*.</span></span> <span data-ttu-id="d6cc6-134">Si pensi ai cursori SQL: un cursore è un oggetto che esegue l'iterazione dei dati, una riga alla volta e presenta i dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-134">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="d6cc6-135">Naturalmente, per i dati possono esistere molti cursori attivi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-135">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="d6cc6-136">Dato che i dati stessi non sono modificabili, i cursori sono effettivamente indipendenti.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-136">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="d6cc6-137">I cursori in genere accedono solo a un subset di colonne: Per motivi di efficienza, ML.NET calcola solo i valori delle colonne necessari per il cursore.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-137">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="d6cc6-138">Trasformatore</span><span class="sxs-lookup"><span data-stu-id="d6cc6-138">Transformer</span></span>

<span data-ttu-id="d6cc6-139">Un trasformatore è un componente che accetta i dati, esegue alcune operazioni su di essi e restituisce nuovi dati trasformati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-139">A transformer is a component that takes data, does some work on it, and return new transformed data.</span></span>

<span data-ttu-id="d6cc6-140">La maggior parte dei trasformatori in ML.NET tende a operare su una *colonna di input* alla volta e produce la *colonna di output*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-140">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="d6cc6-141">Ad esempio, un `new HashTransformer("foo", "bar")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li inserisce nella colonna "bar".</span><span class="sxs-lookup"><span data-stu-id="d6cc6-141">For example, a `new HashTransformer("foo", "bar")` takes the values from column "foo", hash them, and put them into column "bar".</span></span> 

<span data-ttu-id="d6cc6-142">È anche comune che i nomi delle colonne di input e output siano uguali.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-142">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="d6cc6-143">In questo caso, la colonna precedente viene sostituita con quella nuova.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-143">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="d6cc6-144">Ad esempio, un `new HashTransformer("foo")` accetta i valori dalla colonna "foo", li sottopone ad hashing e li reinserisce in "foo".</span><span class="sxs-lookup"><span data-stu-id="d6cc6-144">For example, a `new HashTransformer("foo")` takes the values from column "foo", hash them, and put them back into "foo".</span></span> 

<span data-ttu-id="d6cc6-145">Qualsiasi trasformatore, naturalmente, produce un nuova vista dati quando si chiama `Transform`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-145">Any transformer, of course, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="d6cc6-146">Tenere presente che le viste dati non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-146">Remember, data views are immutable.</span></span>

<span data-ttu-id="d6cc6-147">Un'altra importante considerazione è che, poiché i dati vengono valutati in modo differito (lazy), anche i *trasformatori sono lazy*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-147">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="d6cc6-148">In pratica, dopo aver chiamato</span><span class="sxs-lookup"><span data-stu-id="d6cc6-148">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="d6cc6-149">non viene eseguito alcun calcolo effettivo.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-149">no actual computation happens.</span></span> <span data-ttu-id="d6cc6-150">Solo dopo avere ottenuto un cursore da `newData` e aver iniziato a utilizzare il valore, per `newData` viene richiamata la logica di trasformazione `transformer` (e inoltre, solo se il `transformer` in questione è necessario per produrre le colonne richieste).</span><span class="sxs-lookup"><span data-stu-id="d6cc6-150">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even that only if `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="d6cc6-151">Catene di trasformatori</span><span class="sxs-lookup"><span data-stu-id="d6cc6-151">Transformer chains</span></span>

<span data-ttu-id="d6cc6-152">Una proprietà utile di un trasformatore è la *possibilità di formulare un'applicazione sequenziale di trasformatori come un altro trasformatore*:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-152">A useful property of a transformer is that *you can phrase a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="d6cc6-153">Questa proprietà viene usata comunemente in ML.NET: in genere, il modello ML.NET sottoposto a training è una catena di trasformatori, che è, a tutti gli effetti, un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-153">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span> 

## <a name="data-reader"></a><span data-ttu-id="d6cc6-154">Lettore dati</span><span class="sxs-lookup"><span data-stu-id="d6cc6-154">Data reader</span></span>

<span data-ttu-id="d6cc6-155">Il lettore dati è il componente di ML.NET per la creazione dei dati: accetta un'istanza di `T` e restituisce i dati da tale istanza.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-155">The data reader is ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="d6cc6-156">Una proprietà interessante da notare è la possibilità di creare un lettore dati associando un trasformatore a un lettore dati esistente.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-156">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="d6cc6-157">In questo modo è possibile effettuare il bake del comportamento di trasformazione in un lettore:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-157">This way you can have a reader with transformation behavior baked in:</span></span>

```c#
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="d6cc6-158">Un'altra somiglianza con i trasformatori è che, considerata la valutazione differita dei dati, i *lettori sono lazy*: non vengono eseguite letture effettive (oppure solo in minima parte) quando si chiama `dataReader.Read()`. Solo quando viene richiesto un cursore sui dati risultanti il lettore inizia a lavorare.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-158">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `dataReader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="d6cc6-159">Strumento di stima</span><span class="sxs-lookup"><span data-stu-id="d6cc6-159">Estimator</span></span>

<span data-ttu-id="d6cc6-160">Lo *strumento di stima* è un oggetto che apprende dai dati.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-160">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="d6cc6-161">Il risultato dell'apprendimento è un *trasformatore*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-161">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="d6cc6-162">In ML.NET, usare questa proprietà per creare pipeline di apprendimento che concatenano strumenti di stima diversi:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-162">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = new CopyColumnsEstimator(mlContext, "FareAmount", "Label")
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "VendorId"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "RateCode"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "PaymentType"))
.Append(new ColumnConcatenatingEstimator(mlContext, "Features", "VendorId", "RateCode", "PassengerCount", "TripTime", "TripDistance", "PaymentType"))
.Append(mlContext.Regression.Trainers.FastTree("Label", "Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="d6cc6-163">Un'importante proprietà degli strumenti di stima è che *sono eager e non lazy*: ogni chiamata di `Fit` causa l'esecuzione dell'apprendimento, che è un'operazione che richiede potenzialmente molto tempo.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-163">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="d6cc6-164">Funzione di stima</span><span class="sxs-lookup"><span data-stu-id="d6cc6-164">Prediction function</span></span>

<span data-ttu-id="d6cc6-165">La funzione di stima può essere considerata come una macchina che applica un trasformatore a una sola riga.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-165">The prediction function can be seen as a machine that applies a transformer to one row.</span></span>

<span data-ttu-id="d6cc6-166">Dopo aver ottenuto il modello (un *trasformatore* sottoposto a training tramite `Fit()` o caricato da altre posizioni), è possibile usarlo per eseguire stime usando le normali chiamate a `model.Transform(data)`.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-166">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="d6cc6-167">Tuttavia, quando si usa questo modello in uno scenario reale, spesso non sono disponibili molti esempi su cui basare la stima.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-167">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="d6cc6-168">Sarà invece disponibile un esempio alla volta e necessario eseguire stime tempestive e immediate su tale esempio.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-168">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="d6cc6-169">Naturalmente, è possibile ricorrere alla stima batch:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-169">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="d6cc6-170">Creare una vista dati con esattamente una riga.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-170">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="d6cc6-171">Chiamare `model.Transform(data)` per ottenere la vista dati stimata.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-171">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="d6cc6-172">Ottenere un cursore sui dati risultanti.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-172">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="d6cc6-173">Fare avanzare il cursore di un passaggio per passare alla prima (e unica) riga.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-173">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="d6cc6-174">Estrarre i valori stimati da tale riga.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-174">Extract the predicted values out of it.</span></span>

<span data-ttu-id="d6cc6-175">L'algoritmo precedente può essere implementato tramite la [comprensione dello schema](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), con due oggetti definiti dall'utente `InputExample` e `OutputPrediction` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-175">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```c#
var inputData = env.CreateDataView(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = outputData.AsDynamic.AsEnumerable<OutputPrediction>(env, reuseRowObject: false).Single();
```

<span data-ttu-id="d6cc6-176">Si tratta di una soluzione complicata con potenziali costi a livello di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-176">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="d6cc6-177">Un oggetto funzione di stima esegue invece le stesse operazioni, ma in modo più veloce e pratico, tramite un metodo di estensione `MakePredictionFunction`:</span><span class="sxs-lookup"><span data-stu-id="d6cc6-177">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `MakePredictionFunction`:</span></span>

```c#
var predictionFunc = model.MakePredictionFunction<InputExample, OutputPrediction>(env);
var output = predictionFunc.Predict(example);
```

<span data-ttu-id="d6cc6-178">La funzione di stima è *non rientrante e thread-safe*.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-178">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="d6cc6-179">Se si voglio eseguire stime contemporaneamente con più thread, è necessario disporre di una funzione di stima per ogni thread.</span><span class="sxs-lookup"><span data-stu-id="d6cc6-179">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
