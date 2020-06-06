---
title: Come scrivere convertitori personalizzati per la serializzazione JSON-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: abda23ea538c2c0da6ada4f359ce745602dca45d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84279763"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="e9925-102">Come scrivere convertitori personalizzati per la serializzazione JSON (marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="e9925-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="e9925-103">Questo articolo illustra come creare convertitori personalizzati per le classi di serializzazione JSON fornite nello <xref:System.Text.Json> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e9925-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="e9925-104">Per un'introduzione a `System.Text.Json` , vedere [How to Serialize and Deserialize JSON in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="e9925-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="e9925-105">Un *convertitore* è una classe che converte un oggetto o un valore in e da JSON.</span><span class="sxs-lookup"><span data-stu-id="e9925-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="e9925-106">Lo `System.Text.Json` spazio dei nomi include convertitori predefiniti per la maggior parte dei tipi primitivi che vengono mappati alle primitive JavaScript.</span><span class="sxs-lookup"><span data-stu-id="e9925-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="e9925-107">È possibile scrivere convertitori personalizzati:</span><span class="sxs-lookup"><span data-stu-id="e9925-107">You can write custom converters:</span></span>

* <span data-ttu-id="e9925-108">Per eseguire l'override del comportamento predefinito di un convertitore incorporato.</span><span class="sxs-lookup"><span data-stu-id="e9925-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="e9925-109">È ad esempio possibile che `DateTime` i valori siano rappresentati dal formato mm/gg/aaaa anziché dal formato ISO 8601-1:2019 predefinito.</span><span class="sxs-lookup"><span data-stu-id="e9925-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="e9925-110">Per supportare un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-110">To support a custom value type.</span></span> <span data-ttu-id="e9925-111">Ad esempio, uno `PhoneNumber` struct.</span><span class="sxs-lookup"><span data-stu-id="e9925-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="e9925-112">È anche possibile scrivere convertitori personalizzati per personalizzare o estendere `System.Text.Json` con la funzionalità non inclusa nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="e9925-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="e9925-113">Gli scenari seguenti sono trattati più avanti in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="e9925-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="e9925-114">[Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="e9925-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="e9925-115">[Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="e9925-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="e9925-116">[Supporta la deserializzazione polimorfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="e9925-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="e9925-117">[Supporto del round trip per stack \<T> ](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="e9925-117">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="e9925-118">Modelli di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="e9925-118">Custom converter patterns</span></span>

<span data-ttu-id="e9925-119">Per la creazione di un convertitore personalizzato sono disponibili due modelli: il modello di base e il modello di Factory.</span><span class="sxs-lookup"><span data-stu-id="e9925-119">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="e9925-120">Il modello Factory è per i convertitori che gestiscono il tipo `Enum` o i generics aperti.</span><span class="sxs-lookup"><span data-stu-id="e9925-120">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="e9925-121">Il modello di base è per i tipi generici non generici e chiusi.</span><span class="sxs-lookup"><span data-stu-id="e9925-121">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="e9925-122">I convertitori per i tipi seguenti, ad esempio, richiedono il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="e9925-122">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="e9925-123">Di seguito sono riportati alcuni esempi di tipi che possono essere gestiti tramite il modello di base:</span><span class="sxs-lookup"><span data-stu-id="e9925-123">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="e9925-124">Il modello di base crea una classe in grado di gestire un tipo.</span><span class="sxs-lookup"><span data-stu-id="e9925-124">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="e9925-125">Il modello factory crea una classe che determina, in fase di esecuzione, il tipo specifico richiesto e crea dinamicamente il convertitore appropriato.</span><span class="sxs-lookup"><span data-stu-id="e9925-125">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="e9925-126">Convertitore di base di esempio</span><span class="sxs-lookup"><span data-stu-id="e9925-126">Sample basic converter</span></span>

<span data-ttu-id="e9925-127">L'esempio seguente è un convertitore che esegue l'override della serializzazione predefinita per un tipo di dati esistente.</span><span class="sxs-lookup"><span data-stu-id="e9925-127">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="e9925-128">Il convertitore usa il formato mm/gg/aaaa per le `DateTimeOffset` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-128">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="e9925-129">Convertitore di modelli Factory di esempio</span><span class="sxs-lookup"><span data-stu-id="e9925-129">Sample factory pattern converter</span></span>

<span data-ttu-id="e9925-130">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>` .</span><span class="sxs-lookup"><span data-stu-id="e9925-130">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="e9925-131">Il codice segue il modello Factory perché il primo parametro di tipo generico è `Enum` e il secondo è aperto.</span><span class="sxs-lookup"><span data-stu-id="e9925-131">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="e9925-132">Il `CanConvert` metodo restituisce `true` solo per un oggetto `Dictionary` con due parametri generici, il primo dei quali è un `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="e9925-132">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="e9925-133">Il convertitore interno ottiene un convertitore esistente per gestire qualsiasi tipo fornito in fase di esecuzione per `TValue` .</span><span class="sxs-lookup"><span data-stu-id="e9925-133">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="e9925-134">Il codice precedente è identico a quello visualizzato nel [dizionario di supporto con chiave non stringa](#support-dictionary-with-non-string-key) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e9925-134">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="e9925-135">Passaggi per seguire il modello di base</span><span class="sxs-lookup"><span data-stu-id="e9925-135">Steps to follow the basic pattern</span></span>

<span data-ttu-id="e9925-136">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello di base:</span><span class="sxs-lookup"><span data-stu-id="e9925-136">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="e9925-137">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverter%601> dove `T` è il tipo da serializzare e deserializzare.</span><span class="sxs-lookup"><span data-stu-id="e9925-137">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="e9925-138">Eseguire l'override del `Read` metodo per deserializzare il JSON in ingresso e convertirlo nel tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="e9925-138">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="e9925-139">Usare la <xref:System.Text.Json.Utf8JsonReader> che viene passata al metodo per leggere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="e9925-139">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="e9925-140">Eseguire l'override del `Write` metodo per serializzare l'oggetto in ingresso di tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="e9925-140">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="e9925-141">Usare la <xref:System.Text.Json.Utf8JsonWriter> che viene passata al metodo per scrivere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="e9925-141">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="e9925-142">Eseguire l'override del `CanConvert` metodo solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="e9925-142">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="e9925-143">L'implementazione predefinita restituisce `true` quando il tipo da convertire è di tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="e9925-143">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="e9925-144">Pertanto, i convertitori che supportano solo i tipi `T` non devono eseguire l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="e9925-144">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="e9925-145">Per un esempio di convertitore che deve eseguire l'override di questo metodo, vedere la sezione relativa alla [deserializzazione polimorfica](#support-polymorphic-deserialization) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e9925-145">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="e9925-146">È possibile fare riferimento al [codice sorgente dei convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) come implementazioni di riferimento per la scrittura di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e9925-146">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="e9925-147">Passaggi per seguire il modello Factory</span><span class="sxs-lookup"><span data-stu-id="e9925-147">Steps to follow the factory pattern</span></span>

<span data-ttu-id="e9925-148">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="e9925-148">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="e9925-149">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="e9925-149">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="e9925-150">Eseguire l'override del `CanConvert` metodo per restituire true quando il tipo da convertire è un oggetto che può essere gestito dal convertitore.</span><span class="sxs-lookup"><span data-stu-id="e9925-150">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="e9925-151">Se, ad esempio, il convertitore è per `List<T>` , può gestire solo `List<int>` , `List<string>` e `List<DateTime>` .</span><span class="sxs-lookup"><span data-stu-id="e9925-151">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="e9925-152">Eseguire l'override del `CreateConverter` metodo per restituire un'istanza di una classe Converter che gestirà il tipo da convertire fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9925-152">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="e9925-153">Creare la classe del convertitore di cui il `CreateConverter` metodo crea un'istanza.</span><span class="sxs-lookup"><span data-stu-id="e9925-153">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="e9925-154">Il modello Factory è obbligatorio per i generics aperti perché il codice per convertire un oggetto in e da una stringa non è lo stesso per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="e9925-154">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="e9925-155">Un convertitore per un tipo generico aperto ( `List<T>` ad esempio) deve creare un convertitore per un tipo generico chiuso `List<DateTime>` , ad esempio, dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="e9925-155">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="e9925-156">Il codice deve essere scritto in modo da gestire ogni tipo generico chiuso che il convertitore è in grado di gestire.</span><span class="sxs-lookup"><span data-stu-id="e9925-156">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="e9925-157">Il `Enum` tipo è simile a un tipo generico aperto: un convertitore per `Enum` deve creare un convertitore per uno specifico `Enum` `WeekdaysEnum` , ad esempio, dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="e9925-157">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="e9925-158">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="e9925-158">Error handling</span></span>

<span data-ttu-id="e9925-159">Se è necessario generare un'eccezione nel codice di gestione degli errori, provare a generare un oggetto <xref:System.Text.Json.JsonException> senza un messaggio.</span><span class="sxs-lookup"><span data-stu-id="e9925-159">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="e9925-160">Questo tipo di eccezione crea automaticamente un messaggio che include il percorso della parte di JSON che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="e9925-160">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="e9925-161">L'istruzione, ad esempio, `throw new JsonException();` genera un messaggio di errore simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e9925-161">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="e9925-162">Se si fornisce un messaggio, ad esempio, `throw new JsonException("Error occurred")` l'eccezione fornisce ancora il percorso nella <xref:System.Text.Json.JsonException.Path> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-162">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="e9925-163">Registrare un convertitore personalizzato</span><span class="sxs-lookup"><span data-stu-id="e9925-163">Register a custom converter</span></span>

<span data-ttu-id="e9925-164">*Registrare* un convertitore personalizzato per fare in modo `Serialize` che i metodi e lo `Deserialize` usino.</span><span class="sxs-lookup"><span data-stu-id="e9925-164">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="e9925-165">Scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9925-165">Choose one of the following approaches:</span></span>

* <span data-ttu-id="e9925-166">Aggiungere un'istanza della classe Converter alla <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> raccolta.</span><span class="sxs-lookup"><span data-stu-id="e9925-166">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="e9925-167">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) alle proprietà che richiedono il convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="e9925-168">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una classe o a uno struct che rappresenta un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-168">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="e9925-169">Esempio di registrazione-raccolta Converters</span><span class="sxs-lookup"><span data-stu-id="e9925-169">Registration sample - Converters collection</span></span>

<span data-ttu-id="e9925-170">Di seguito è riportato un esempio che rende il <xref:System.ComponentModel.DateTimeOffsetConverter> valore predefinito per le proprietà di tipo <xref:System.DateTimeOffset> :</span><span class="sxs-lookup"><span data-stu-id="e9925-170">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="e9925-171">Si supponga di serializzare un'istanza del tipo seguente:</span><span class="sxs-lookup"><span data-stu-id="e9925-171">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="e9925-172">Di seguito è riportato un esempio di output JSON che mostra il convertitore personalizzato usato:</span><span class="sxs-lookup"><span data-stu-id="e9925-172">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="e9925-173">Il codice seguente usa lo stesso approccio per deserializzare usando il `DateTimeOffset` convertitore personalizzato:</span><span class="sxs-lookup"><span data-stu-id="e9925-173">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="e9925-174">Esempio di registrazione-[JsonConverter] in una proprietà</span><span class="sxs-lookup"><span data-stu-id="e9925-174">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="e9925-175">Il codice seguente seleziona un convertitore personalizzato per la `Date` proprietà:</span><span class="sxs-lookup"><span data-stu-id="e9925-175">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="e9925-176">Il codice da serializzare `WeatherForecastWithConverterAttribute` non richiede l'uso di `JsonSerializeOptions.Converters` :</span><span class="sxs-lookup"><span data-stu-id="e9925-176">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="e9925-177">Anche il codice da deserializzare non richiede l'uso di `Converters` :</span><span class="sxs-lookup"><span data-stu-id="e9925-177">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="e9925-178">Esempio di registrazione-[JsonConverter] in un tipo</span><span class="sxs-lookup"><span data-stu-id="e9925-178">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="e9925-179">Di seguito è riportato il codice che consente di creare uno struct e di applicarvi l' `[JsonConverter]` attributo:</span><span class="sxs-lookup"><span data-stu-id="e9925-179">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Temperature.cs)]

<span data-ttu-id="e9925-180">Ecco il convertitore personalizzato per lo struct precedente:</span><span class="sxs-lookup"><span data-stu-id="e9925-180">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/TemperatureConverter.cs)]

<span data-ttu-id="e9925-181">L' `[JsonConvert]` attributo dello struct registra il convertitore personalizzato come valore predefinito per le proprietà di tipo `Temperature` .</span><span class="sxs-lookup"><span data-stu-id="e9925-181">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="e9925-182">Il convertitore viene usato automaticamente sulla `TemperatureCelsius` proprietà del tipo seguente quando viene serializzato o deserializzato:</span><span class="sxs-lookup"><span data-stu-id="e9925-182">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="e9925-183">Precedenza di registrazione del convertitore</span><span class="sxs-lookup"><span data-stu-id="e9925-183">Converter registration precedence</span></span>

<span data-ttu-id="e9925-184">Durante la serializzazione o la deserializzazione, viene scelto un convertitore per ogni elemento JSON nell'ordine seguente, elencato dalla priorità più alta a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="e9925-184">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="e9925-185">`[JsonConverter]`applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-185">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="e9925-186">Convertitore aggiunto alla `Converters` raccolta.</span><span class="sxs-lookup"><span data-stu-id="e9925-186">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="e9925-187">`[JsonConverter]`applicato a un tipo di valore personalizzato o POCO.</span><span class="sxs-lookup"><span data-stu-id="e9925-187">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="e9925-188">Se nella raccolta vengono registrati più convertitori personalizzati per un tipo `Converters` , viene utilizzato il primo convertitore che restituisce true per `CanConvert` .</span><span class="sxs-lookup"><span data-stu-id="e9925-188">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="e9925-189">Un convertitore predefinito viene scelto solo se non è registrato alcun convertitore personalizzato applicabile.</span><span class="sxs-lookup"><span data-stu-id="e9925-189">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="e9925-190">Esempi di convertitore per scenari comuni</span><span class="sxs-lookup"><span data-stu-id="e9925-190">Converter samples for common scenarios</span></span>

<span data-ttu-id="e9925-191">Le sezioni seguenti forniscono esempi di convertitore che affrontano alcuni scenari comuni non gestiti dalla funzionalità incorporata.</span><span class="sxs-lookup"><span data-stu-id="e9925-191">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="e9925-192">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="e9925-192">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="e9925-193">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="e9925-193">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="e9925-194">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="e9925-194">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)
* <span data-ttu-id="e9925-195">[Supporto del round trip per stack \<T> ](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="e9925-195">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="e9925-196">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="e9925-196">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="e9925-197">Quando si esegue la deserializzazione in una proprietà di tipo `object` , `JsonElement` viene creato un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e9925-197">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="e9925-198">Il motivo è che il deserializzatore non conosce il tipo CLR da creare e non tenta di indovinare.</span><span class="sxs-lookup"><span data-stu-id="e9925-198">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="e9925-199">Se, ad esempio, una proprietà JSON ha "true", il deserializzatore non deduce che il valore è un `Boolean` e se un elemento ha "01/01/2019", il deserializzatore non deduce che si tratta di un oggetto `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="e9925-199">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="e9925-200">L'inferenza del tipo può non essere corretta.</span><span class="sxs-lookup"><span data-stu-id="e9925-200">Type inference can be inaccurate.</span></span> <span data-ttu-id="e9925-201">Se il deserializzatore analizza un numero JSON senza separatore decimale come `long` , che potrebbe causare problemi fuori intervallo se il valore è stato originariamente serializzato come `ulong` o `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="e9925-201">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="e9925-202">L'analisi di un numero con un separatore decimale come `double` potrebbe perdere precisione se il numero è stato originariamente serializzato come `decimal` .</span><span class="sxs-lookup"><span data-stu-id="e9925-202">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="e9925-203">Per gli scenari che richiedono l'inferenza del tipo, nel codice seguente viene illustrato un convertitore personalizzato per le `object` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-203">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="e9925-204">Il codice esegue la conversione:</span><span class="sxs-lookup"><span data-stu-id="e9925-204">The code converts:</span></span>

* <span data-ttu-id="e9925-205">`true`e `false` a`Boolean`</span><span class="sxs-lookup"><span data-stu-id="e9925-205">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="e9925-206">Numeri senza decimali`long`</span><span class="sxs-lookup"><span data-stu-id="e9925-206">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="e9925-207">Numeri con un numero decimale a`double`</span><span class="sxs-lookup"><span data-stu-id="e9925-207">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="e9925-208">Data di`DateTime`</span><span class="sxs-lookup"><span data-stu-id="e9925-208">Dates to `DateTime`</span></span>
* <span data-ttu-id="e9925-209">Stringhe`string`</span><span class="sxs-lookup"><span data-stu-id="e9925-209">Strings to `string`</span></span>
* <span data-ttu-id="e9925-210">Tutti gli altri elementi`JsonElement`</span><span class="sxs-lookup"><span data-stu-id="e9925-210">Everything else to `JsonElement`</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="e9925-211">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="e9925-211">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="e9925-212">Di seguito è riportato un esempio di tipo con `object` proprietà:</span><span class="sxs-lookup"><span data-stu-id="e9925-212">Here's an example type with `object` properties:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="e9925-213">L'esempio seguente di JSON da deserializzare contiene valori che verranno deserializzati come `DateTime` , `long` e `string` :</span><span class="sxs-lookup"><span data-stu-id="e9925-213">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="e9925-214">Senza il convertitore personalizzato, la deserializzazione inserisce un oggetto `JsonElement` in ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-214">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="e9925-215">Nella [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello `System.Text.Json.Serialization` spazio dei nomi sono disponibili altri esempi di convertitori personalizzati che gestiscono la deserializzazione alle `object` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-215">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="e9925-216">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="e9925-216">Support Dictionary with non-string key</span></span>

<span data-ttu-id="e9925-217">Il supporto incorporato per le raccolte di dizionari è per `Dictionary<string, TValue>` .</span><span class="sxs-lookup"><span data-stu-id="e9925-217">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="e9925-218">Ovvero la chiave deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="e9925-218">That is, the key must be a string.</span></span> <span data-ttu-id="e9925-219">Per supportare un dizionario con un numero intero o un altro tipo come chiave, è necessario un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-219">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="e9925-220">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>` :</span><span class="sxs-lookup"><span data-stu-id="e9925-220">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="e9925-221">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="e9925-221">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="e9925-222">Il convertitore è in grado di serializzare e deserializzare la `TemperatureRanges` proprietà della classe seguente che utilizza gli elementi seguenti `Enum` :</span><span class="sxs-lookup"><span data-stu-id="e9925-222">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="e9925-223">L'output JSON dalla serializzazione è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e9925-223">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="e9925-224">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello `System.Text.Json.Serialization` spazio dei nomi contiene altri esempi di convertitori personalizzati che gestiscono dizionari non di stringa.</span><span class="sxs-lookup"><span data-stu-id="e9925-224">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="e9925-225">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="e9925-225">Support polymorphic deserialization</span></span>

<span data-ttu-id="e9925-226">Le funzionalità predefinite forniscono una gamma limitata di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non supportano affatto la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="e9925-226">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="e9925-227">La deserializzazione richiede un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-227">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="e9925-228">Si supponga, ad esempio, di disporre di una `Person` classe di base astratta, con `Employee` `Customer` classi derivate e.</span><span class="sxs-lookup"><span data-stu-id="e9925-228">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="e9925-229">La deserializzazione polimorfica significa che in fase di progettazione è possibile specificare `Person` come destinazione della deserializzazione e `Customer` `Employee` gli oggetti e in JSON vengono deserializzati correttamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9925-229">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="e9925-230">Durante la deserializzazione, è necessario trovare indizi che identifichino il tipo richiesto nel codice JSON.</span><span class="sxs-lookup"><span data-stu-id="e9925-230">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="e9925-231">I tipi di indizi disponibili variano in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="e9925-231">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="e9925-232">Ad esempio, una proprietà discriminatore potrebbe essere disponibile o potrebbe essere necessario basarsi sulla presenza o sull'assenza di una particolare proprietà.</span><span class="sxs-lookup"><span data-stu-id="e9925-232">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="e9925-233">La versione corrente di `System.Text.Json` non fornisce attributi per specificare come gestire gli scenari di deserializzazione polimorfica, quindi i convertitori personalizzati sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="e9925-233">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="e9925-234">Nel codice seguente viene illustrata una classe di base, due classi derivate e un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-234">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="e9925-235">Il convertitore usa una proprietà discriminatore per eseguire la deserializzazione polimorfica.</span><span class="sxs-lookup"><span data-stu-id="e9925-235">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="e9925-236">Il discriminatore di tipo non è incluso nelle definizioni di classe ma viene creato durante la serializzazione e viene letto durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="e9925-236">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="e9925-237">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="e9925-237">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="e9925-238">Il convertitore può deserializzare JSON creato con lo stesso convertitore da serializzare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9925-238">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="e9925-239">Il codice del convertitore nell'esempio precedente legge e scrive ogni proprietà manualmente.</span><span class="sxs-lookup"><span data-stu-id="e9925-239">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="e9925-240">In alternativa, è possibile chiamare `Deserialize` o `Serialize` per eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="e9925-240">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="e9925-241">Per un esempio, vedere [questo post di StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="e9925-241">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="e9925-242">Supporto del round trip per stack\<T></span><span class="sxs-lookup"><span data-stu-id="e9925-242">Support round-trip for Stack\<T></span></span>

<span data-ttu-id="e9925-243">Se si deserializza una stringa JSON in un <xref:System.Collections.Generic.Stack%601> oggetto e quindi si serializza tale oggetto, il contenuto dello stack è in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="e9925-243">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="e9925-244">Questo comportamento si applica ai tipi e all'interfaccia seguenti e ai tipi definiti dall'utente che derivano da essi:</span><span class="sxs-lookup"><span data-stu-id="e9925-244">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="e9925-245">Per supportare la serializzazione e la deserializzazione che mantiene l'ordine originale nello stack, è necessario un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9925-245">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="e9925-246">Il codice seguente illustra un convertitore personalizzato che consente di eseguire sequenze di andata e ritorno da e verso `Stack<T>` gli oggetti:</span><span class="sxs-lookup"><span data-stu-id="e9925-246">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs)]

<span data-ttu-id="e9925-247">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="e9925-247">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs?name=SnippetRegister)]

## <a name="other-custom-converter-samples"></a><span data-ttu-id="e9925-248">Altri esempi di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="e9925-248">Other custom converter samples</span></span>

<span data-ttu-id="e9925-249">L'articolo [eseguire la migrazione da Newtonsoft.Json System.Text.Json a](system-text-json-migrate-from-newtonsoft-how-to.md) contiene esempi aggiuntivi di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e9925-249">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="e9925-250">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nel `System.Text.Json.Serialization` codice sorgente include altri esempi di convertitore personalizzati, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9925-250">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="e9925-251">[Convertitore Int32 che converte il valore null in 0 per la deserializzazione](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="e9925-251">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="e9925-252">[Convertitore Int32 che consente di deserializzare sia i valori di stringa che di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="e9925-252">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="e9925-253">[Convertitore enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="e9925-253">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="e9925-254">[\<T>Convertitore di elenchi che accetta dati esterni](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="e9925-254">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="e9925-255">[Long [] Converter che funziona con un elenco delimitato da virgole di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="e9925-255">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="e9925-256">Se è necessario creare un convertitore che modifichi il comportamento di un convertitore incorporato esistente, è possibile ottenere [il codice sorgente del convertitore esistente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) per fungere da punto di partenza per la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9925-256">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9925-257">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e9925-257">Additional resources</span></span>

* <span data-ttu-id="e9925-258">[Codice sorgente per convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="e9925-258">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="e9925-259">[Supporto di DateTime e DateTimeOffset inSystem.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="e9925-259">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="e9925-260">[System.Text.JsonPanoramica](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e9925-260">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="e9925-261">[Come usareSystem.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="e9925-261">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="e9925-262">[Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="e9925-262">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="e9925-263">[System.Text.JsonRiferimento API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e9925-263">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="e9925-264">[System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="e9925-264">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
