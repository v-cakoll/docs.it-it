---
title: Come scrivere convertitori personalizzati per la serializzazione JSON-.NET
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 0f8b89ec7d7b1677de085631958b888e154aa4fa
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116718"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="4ffca-102">Come scrivere convertitori personalizzati per la serializzazione JSON (marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="4ffca-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="4ffca-103">Questo articolo illustra come creare convertitori personalizzati per le classi di serializzazione JSON fornite nello spazio dei nomi <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="4ffca-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="4ffca-104">Per un'introduzione ai `System.Text.Json`, vedere [come serializzare e deserializzare JSON in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="4ffca-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="4ffca-105">Un *convertitore* è una classe che converte un oggetto o un valore in e da JSON.</span><span class="sxs-lookup"><span data-stu-id="4ffca-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="4ffca-106">Lo spazio dei nomi `System.Text.Json` dispone di convertitori predefiniti per la maggior parte dei tipi primitivi con mapping alle primitive JavaScript.</span><span class="sxs-lookup"><span data-stu-id="4ffca-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="4ffca-107">È possibile scrivere convertitori personalizzati:</span><span class="sxs-lookup"><span data-stu-id="4ffca-107">You can write custom converters:</span></span>

* <span data-ttu-id="4ffca-108">Per eseguire l'override del comportamento predefinito di un convertitore incorporato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="4ffca-109">È ad esempio possibile che si desideri che i valori `DateTime` siano rappresentati dal formato mm/gg/aaaa anziché dal formato ISO 8601-1:2019 predefinito.</span><span class="sxs-lookup"><span data-stu-id="4ffca-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="4ffca-110">Per supportare un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-110">To support a custom value type.</span></span> <span data-ttu-id="4ffca-111">Ad esempio, uno struct `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="4ffca-112">È anche possibile scrivere convertitori personalizzati per personalizzare o estendere `System.Text.Json` con funzionalità non incluse nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="4ffca-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="4ffca-113">Gli scenari seguenti sono trattati più avanti in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="4ffca-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="4ffca-114">[Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4ffca-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4ffca-115">[Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4ffca-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="4ffca-116">[Supporta la deserializzazione polimorfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4ffca-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="4ffca-117">Modelli di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="4ffca-117">Custom converter patterns</span></span>

<span data-ttu-id="4ffca-118">Per la creazione di un convertitore personalizzato sono disponibili due modelli: il modello di base e il modello di Factory.</span><span class="sxs-lookup"><span data-stu-id="4ffca-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="4ffca-119">Il modello Factory è per i convertitori che gestiscono il tipo `Enum` o i generics aperti.</span><span class="sxs-lookup"><span data-stu-id="4ffca-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="4ffca-120">Il modello di base è per i tipi generici non generici e chiusi.</span><span class="sxs-lookup"><span data-stu-id="4ffca-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="4ffca-121">I convertitori per i tipi seguenti, ad esempio, richiedono il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="4ffca-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="4ffca-122">Di seguito sono riportati alcuni esempi di tipi che possono essere gestiti tramite il modello di base:</span><span class="sxs-lookup"><span data-stu-id="4ffca-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="4ffca-123">Il modello di base crea una classe in grado di gestire un tipo.</span><span class="sxs-lookup"><span data-stu-id="4ffca-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="4ffca-124">Il modello factory crea una classe che determina in fase di esecuzione quale tipo specifico è obbligatorio e crea dinamicamente il convertitore appropriato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="4ffca-125">Convertitore di base di esempio</span><span class="sxs-lookup"><span data-stu-id="4ffca-125">Sample basic converter</span></span>

<span data-ttu-id="4ffca-126">L'esempio seguente è un convertitore che esegue l'override della serializzazione predefinita per un tipo di dati esistente.</span><span class="sxs-lookup"><span data-stu-id="4ffca-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="4ffca-127">Il convertitore usa il formato mm/gg/aaaa per le proprietà `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="4ffca-128">Convertitore di modelli Factory di esempio</span><span class="sxs-lookup"><span data-stu-id="4ffca-128">Sample factory pattern converter</span></span>

<span data-ttu-id="4ffca-129">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="4ffca-130">Il codice segue il modello Factory perché il primo parametro di tipo generico è `Enum` e il secondo è aperto.</span><span class="sxs-lookup"><span data-stu-id="4ffca-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="4ffca-131">Il metodo `CanConvert` restituisce `true` solo per un `Dictionary` con due parametri generici, il primo dei quali è un tipo `Enum`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="4ffca-132">Il convertitore interno ottiene un convertitore esistente per gestire qualsiasi tipo fornito in fase di esecuzione per `TValue`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="4ffca-133">Il codice precedente è identico a quello visualizzato nel [dizionario di supporto con chiave non stringa](#support-dictionary-with-non-string-key) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4ffca-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="4ffca-134">Passaggi per seguire il modello di base</span><span class="sxs-lookup"><span data-stu-id="4ffca-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="4ffca-135">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello di base:</span><span class="sxs-lookup"><span data-stu-id="4ffca-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="4ffca-136">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverter%601> dove `T` è il tipo da serializzare e deserializzare.</span><span class="sxs-lookup"><span data-stu-id="4ffca-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="4ffca-137">Eseguire l'override del metodo `Read` per deserializzare il codice JSON in ingresso e convertirlo nel tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="4ffca-138">Usare il <xref:System.Text.Json.Utf8JsonReader> passato al metodo per leggere il file JSON.</span><span class="sxs-lookup"><span data-stu-id="4ffca-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="4ffca-139">Eseguire l'override del metodo `Write` per serializzare l'oggetto in ingresso di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="4ffca-140">Usare il <xref:System.Text.Json.Utf8JsonWriter> passato al metodo per scrivere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="4ffca-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="4ffca-141">Eseguire l'override del metodo `CanConvert` solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="4ffca-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="4ffca-142">L'implementazione predefinita restituisce `true` quando il tipo da convertire è di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="4ffca-143">Pertanto, i convertitori che supportano solo il tipo `T` non devono eseguire l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4ffca-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="4ffca-144">Per un esempio di convertitore che deve eseguire l'override di questo metodo, vedere la sezione relativa alla [deserializzazione polimorfica](#support-polymorphic-deserialization) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4ffca-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="4ffca-145">È possibile fare riferimento al [codice sorgente dei convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) come implementazioni di riferimento per la scrittura di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4ffca-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="4ffca-146">Passaggi per seguire il modello Factory</span><span class="sxs-lookup"><span data-stu-id="4ffca-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="4ffca-147">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="4ffca-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="4ffca-148">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="4ffca-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="4ffca-149">Eseguire l'override del metodo `CanConvert` per restituire true quando il tipo da convertire è quello che può essere gestito dal convertitore.</span><span class="sxs-lookup"><span data-stu-id="4ffca-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="4ffca-150">Ad esempio, se il convertitore è per `List<T>` potrebbe gestire solo `List<int>`, `List<string>`e `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="4ffca-151">Eseguire l'override del metodo `CreateConverter` per restituire un'istanza di una classe Converter che gestirà il tipo da convertire fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ffca-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="4ffca-152">Creare la classe del convertitore di cui il metodo `CreateConverter` crea un'istanza.</span><span class="sxs-lookup"><span data-stu-id="4ffca-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="4ffca-153">Il modello Factory è obbligatorio per i generics aperti perché il codice per convertire un oggetto in e da una stringa non è lo stesso per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="4ffca-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="4ffca-154">Un convertitore per un tipo generico aperto (ad esempio`List<T>`) deve creare un convertitore per un tipo generico chiuso (ad esempio,`List<DateTime>`) dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4ffca-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="4ffca-155">Il codice deve essere scritto in modo da gestire ogni tipo generico chiuso che il convertitore è in grado di gestire.</span><span class="sxs-lookup"><span data-stu-id="4ffca-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="4ffca-156">Il tipo di `Enum` è simile a un tipo generico aperto: un convertitore per `Enum` deve creare un convertitore per un `Enum` specifico (ad esempio,`WeekdaysEnum`) dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4ffca-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="4ffca-157">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="4ffca-157">Error handling</span></span>

<span data-ttu-id="4ffca-158">Se è necessario generare un'eccezione nel codice di gestione degli errori, provare a generare un <xref:System.Text.Json.JsonException> senza un messaggio.</span><span class="sxs-lookup"><span data-stu-id="4ffca-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="4ffca-159">Questo tipo di eccezione crea automaticamente un messaggio che include il percorso della parte di JSON che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4ffca-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="4ffca-160">Ad esempio, l'istruzione `throw new JsonException();` genera un messaggio di errore simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4ffca-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="4ffca-161">Se si fornisce un messaggio, ad esempio `throw new JsonException("Error occurred")`, l'eccezione fornisce ancora il percorso nella proprietà <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="4ffca-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="4ffca-162">Registrare un convertitore personalizzato</span><span class="sxs-lookup"><span data-stu-id="4ffca-162">Register a custom converter</span></span>

<span data-ttu-id="4ffca-163">*Registrare* un convertitore personalizzato per fare in modo che i metodi `Serialize` e `Deserialize` lo usino.</span><span class="sxs-lookup"><span data-stu-id="4ffca-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="4ffca-164">Scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ffca-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="4ffca-165">Aggiungere un'istanza della classe Converter alla raccolta <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ffca-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="4ffca-166">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) alle proprietà che richiedono il convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="4ffca-167">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una classe o a uno struct che rappresenta un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="4ffca-168">Esempio di registrazione-raccolta Converters</span><span class="sxs-lookup"><span data-stu-id="4ffca-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="4ffca-169">Di seguito è riportato un esempio che rende il <xref:System.ComponentModel.DateTimeOffsetConverter> il valore predefinito per le proprietà di tipo <xref:System.DateTimeOffset>:</span><span class="sxs-lookup"><span data-stu-id="4ffca-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="4ffca-170">Si supponga di serializzare un'istanza del tipo seguente:</span><span class="sxs-lookup"><span data-stu-id="4ffca-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="4ffca-171">Di seguito è riportato un esempio di output JSON che mostra il convertitore personalizzato usato:</span><span class="sxs-lookup"><span data-stu-id="4ffca-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4ffca-172">Il codice seguente usa lo stesso approccio per deserializzare usando il convertitore di `DateTimeOffset` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4ffca-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="4ffca-173">Esempio di registrazione-[JsonConverter] in una proprietà</span><span class="sxs-lookup"><span data-stu-id="4ffca-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="4ffca-174">Il codice seguente consente di selezionare un convertitore personalizzato per la proprietà `Date`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="4ffca-175">Il codice per serializzare `WeatherForecastWithConverterAttribute` non richiede l'uso di `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="4ffca-176">Anche il codice da deserializzare non richiede l'uso di `Converters`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="4ffca-177">Esempio di registrazione-[JsonConverter] in un tipo</span><span class="sxs-lookup"><span data-stu-id="4ffca-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="4ffca-178">Di seguito è riportato il codice che consente di creare uno struct e di applicare l'attributo `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="4ffca-179">Ecco il convertitore personalizzato per lo struct precedente:</span><span class="sxs-lookup"><span data-stu-id="4ffca-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="4ffca-180">L'attributo `[JsonConvert]` nello struct registra il convertitore personalizzato come valore predefinito per le proprietà di tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="4ffca-181">Il convertitore viene usato automaticamente nella proprietà `TemperatureCelsius` del tipo seguente quando viene serializzato o deserializzato:</span><span class="sxs-lookup"><span data-stu-id="4ffca-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="4ffca-182">Precedenza di registrazione del convertitore</span><span class="sxs-lookup"><span data-stu-id="4ffca-182">Converter registration precedence</span></span>

<span data-ttu-id="4ffca-183">Durante la serializzazione o la deserializzazione, viene scelto un convertitore per ogni elemento JSON nell'ordine seguente, elencato dalla priorità più alta a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="4ffca-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="4ffca-184">`[JsonConverter]` applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ffca-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="4ffca-185">Convertitore aggiunto alla raccolta di `Converters`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="4ffca-186">`[JsonConverter]` applicato a un tipo di valore personalizzato o POCO.</span><span class="sxs-lookup"><span data-stu-id="4ffca-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="4ffca-187">Se nella raccolta `Converters` vengono registrati più convertitori personalizzati per un tipo, viene utilizzato il primo convertitore che restituisce true per `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="4ffca-188">Un convertitore predefinito viene scelto solo se non è registrato alcun convertitore personalizzato applicabile.</span><span class="sxs-lookup"><span data-stu-id="4ffca-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="4ffca-189">Esempi di convertitore per scenari comuni</span><span class="sxs-lookup"><span data-stu-id="4ffca-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="4ffca-190">Le sezioni seguenti forniscono esempi di convertitore che affrontano alcuni scenari comuni non gestiti dalla funzionalità incorporata.</span><span class="sxs-lookup"><span data-stu-id="4ffca-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="4ffca-191">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="4ffca-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="4ffca-192">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="4ffca-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="4ffca-193">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="4ffca-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="4ffca-194">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="4ffca-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="4ffca-195">Quando si esegue la deserializzazione in una proprietà di tipo `object`, viene creato un oggetto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="4ffca-196">Il motivo è che il deserializzatore non conosce il tipo CLR da creare e non tenta di indovinare.</span><span class="sxs-lookup"><span data-stu-id="4ffca-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="4ffca-197">Se, ad esempio, una proprietà JSON ha "true", il deserializzatore non deduce che il valore è un `Boolean`e se un elemento ha "01/01/2019", il deserializzatore non deduce che si tratta di un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="4ffca-198">L'inferenza del tipo può non essere corretta.</span><span class="sxs-lookup"><span data-stu-id="4ffca-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="4ffca-199">Se il deserializzatore analizza un numero JSON senza separatore decimale come `long`, ciò potrebbe causare problemi fuori intervallo se il valore è stato serializzato originariamente come `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="4ffca-200">L'analisi di un numero con un separatore decimale come `double` potrebbe perdere precisione se il numero è stato originariamente serializzato come `decimal`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="4ffca-201">Per gli scenari che richiedono l'inferenza del tipo, nel codice seguente viene illustrato un convertitore personalizzato per `object` proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ffca-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="4ffca-202">Il codice esegue la conversione:</span><span class="sxs-lookup"><span data-stu-id="4ffca-202">The code converts:</span></span>

* <span data-ttu-id="4ffca-203">`true` e `false` per `Boolean`</span><span class="sxs-lookup"><span data-stu-id="4ffca-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="4ffca-204">Numeri senza decimali da `long`</span><span class="sxs-lookup"><span data-stu-id="4ffca-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="4ffca-205">Numeri con un numero decimale da `double`</span><span class="sxs-lookup"><span data-stu-id="4ffca-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="4ffca-206">Data di `DateTime`</span><span class="sxs-lookup"><span data-stu-id="4ffca-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="4ffca-207">Stringhe da `string`</span><span class="sxs-lookup"><span data-stu-id="4ffca-207">Strings to `string`</span></span>
* <span data-ttu-id="4ffca-208">Tutti gli altri elementi da `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="4ffca-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="4ffca-209">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4ffca-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="4ffca-210">Di seguito è riportato un esempio di tipo con proprietà `object`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="4ffca-211">L'esempio seguente di JSON da deserializzare contiene valori che verranno deserializzati come `DateTime`, `long`e `string`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="4ffca-212">Senza il convertitore personalizzato, la deserializzazione inserisce una `JsonElement` in ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ffca-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="4ffca-213">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono la deserializzazione per `object` proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ffca-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="4ffca-214">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="4ffca-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="4ffca-215">Il supporto incorporato per le raccolte di dizionari è per `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4ffca-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="4ffca-216">Ovvero la chiave deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="4ffca-216">That is, the key must be a string.</span></span> <span data-ttu-id="4ffca-217">Per supportare un dizionario con un numero intero o un altro tipo come chiave, è necessario un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="4ffca-218">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="4ffca-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="4ffca-219">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4ffca-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="4ffca-220">Il convertitore è in grado di serializzare e deserializzare la proprietà `TemperatureRanges` della classe seguente che usa i `Enum`seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ffca-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="4ffca-221">L'output JSON dalla serializzazione è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4ffca-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="4ffca-222">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono dizionari non di stringa.</span><span class="sxs-lookup"><span data-stu-id="4ffca-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="4ffca-223">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="4ffca-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="4ffca-224">Le funzionalità predefinite forniscono una gamma limitata di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non supportano affatto la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4ffca-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="4ffca-225">La deserializzazione richiede un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="4ffca-226">Si supponga, ad esempio, di disporre di una classe di base astratta `Person`, con `Employee` e `Customer` classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4ffca-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="4ffca-227">La deserializzazione polimorfica significa che in fase di progettazione è possibile specificare `Person` come destinazione della deserializzazione e gli oggetti `Customer` e `Employee` nel file JSON vengono deserializzati correttamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ffca-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="4ffca-228">Durante la deserializzazione, è necessario trovare indizi che identifichino il tipo richiesto nel codice JSON.</span><span class="sxs-lookup"><span data-stu-id="4ffca-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="4ffca-229">I tipi di indizi disponibili variano in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="4ffca-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="4ffca-230">Ad esempio, una proprietà discriminatore potrebbe essere disponibile o potrebbe essere necessario basarsi sulla presenza o sull'assenza di una particolare proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ffca-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="4ffca-231">La versione corrente di `System.Text.Json` non fornisce attributi per specificare la modalità di gestione degli scenari di deserializzazione polimorfica, quindi i convertitori personalizzati sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4ffca-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="4ffca-232">Nel codice seguente viene illustrata una classe di base, due classi derivate e un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ffca-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="4ffca-233">Il convertitore usa una proprietà discriminatore per eseguire la deserializzazione polimorfica.</span><span class="sxs-lookup"><span data-stu-id="4ffca-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="4ffca-234">Il discriminatore di tipo non è incluso nelle definizioni di classe ma viene creato durante la serializzazione e viene letto durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4ffca-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="4ffca-235">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4ffca-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="4ffca-236">Il convertitore può deserializzare JSON creato con lo stesso convertitore da serializzare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4ffca-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="4ffca-237">Il codice del convertitore nell'esempio precedente legge e scrive ogni proprietà manualmente.</span><span class="sxs-lookup"><span data-stu-id="4ffca-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="4ffca-238">In alternativa, è possibile chiamare `Deserialize` o `Serialize` per eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="4ffca-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="4ffca-239">Per un esempio, vedere [questo post di StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="4ffca-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="4ffca-240">Altri esempi di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="4ffca-240">Other custom converter samples</span></span>

<span data-ttu-id="4ffca-241">L'articolo [migrate from Newtonsoft. JSON to System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md) contiene esempi aggiuntivi di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4ffca-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="4ffca-242">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nel codice sorgente `System.Text.Json.Serialization` include altri esempi di convertitore personalizzati, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4ffca-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* [<span data-ttu-id="4ffca-243">Convertitore Int32 che converte il valore null in 0 per la deserializzazione</span><span class="sxs-lookup"><span data-stu-id="4ffca-243">Int32 converter that converts null to 0 on deserialize</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [<span data-ttu-id="4ffca-244">Convertitore Int32 che consente di deserializzare sia i valori di stringa che di numeri</span><span class="sxs-lookup"><span data-stu-id="4ffca-244">Int32 converter that allows both string and number values on deserialize</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [<span data-ttu-id="4ffca-245">Convertitore enum</span><span class="sxs-lookup"><span data-stu-id="4ffca-245">Enum converter</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* [<span data-ttu-id="4ffca-246">Elenco\<convertitore di > T che accetta dati esterni</span><span class="sxs-lookup"><span data-stu-id="4ffca-246">List\<T> converter that accepts external data</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* <span data-ttu-id="4ffca-247">[Long [] Converter che funziona con un elenco delimitato da virgole di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="4ffca-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span> 

<span data-ttu-id="4ffca-248">Se è necessario creare un convertitore che modifichi il comportamento di un convertitore incorporato esistente, è possibile ottenere [il codice sorgente del convertitore esistente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) per fungere da punto di partenza per la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ffca-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ffca-249">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4ffca-249">Additional resources</span></span>

* [<span data-ttu-id="4ffca-250">Codice sorgente per convertitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="4ffca-250">Source code for built-in converters</span></span>](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [<span data-ttu-id="4ffca-251">Supporto di DateTime e DateTimeOffset in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4ffca-251">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="4ffca-252">Panoramica di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4ffca-252">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="4ffca-253">Come usare System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4ffca-253">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="4ffca-254">Come eseguire la migrazione da Newtonsoft. JSON</span><span class="sxs-lookup"><span data-stu-id="4ffca-254">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="4ffca-255">Informazioni di riferimento sull'API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4ffca-255">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="4ffca-256">Riferimento all'API System. Text. JSON. Serialization</span><span class="sxs-lookup"><span data-stu-id="4ffca-256">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
