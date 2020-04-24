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
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159572"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="1e608-102">Come scrivere convertitori personalizzati per la serializzazione JSON (marshalling) in .NET</span><span class="sxs-lookup"><span data-stu-id="1e608-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="1e608-103">Questo articolo illustra come creare convertitori personalizzati per le classi di serializzazione JSON fornite nello <xref:[!OP.NO-LOC(System.Text.Json)]> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1e608-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="1e608-104">Per un'introduzione a `[!OP.NO-LOC(System.Text.Json)]`, vedere [How to Serialize and Deserialize JSON in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="1e608-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="1e608-105">Un *convertitore* è una classe che converte un oggetto o un valore in e da JSON.</span><span class="sxs-lookup"><span data-stu-id="1e608-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="1e608-106">Lo `[!OP.NO-LOC(System.Text.Json)]` spazio dei nomi include convertitori predefiniti per la maggior parte dei tipi primitivi che vengono mappati alle primitive JavaScript.</span><span class="sxs-lookup"><span data-stu-id="1e608-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="1e608-107">È possibile scrivere convertitori personalizzati:</span><span class="sxs-lookup"><span data-stu-id="1e608-107">You can write custom converters:</span></span>

* <span data-ttu-id="1e608-108">Per eseguire l'override del comportamento predefinito di un convertitore incorporato.</span><span class="sxs-lookup"><span data-stu-id="1e608-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="1e608-109">È ad esempio possibile che `DateTime` i valori siano rappresentati dal formato mm/gg/aaaa anziché dal formato ISO 8601-1:2019 predefinito.</span><span class="sxs-lookup"><span data-stu-id="1e608-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="1e608-110">Per supportare un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-110">To support a custom value type.</span></span> <span data-ttu-id="1e608-111">Ad esempio, uno `PhoneNumber` struct.</span><span class="sxs-lookup"><span data-stu-id="1e608-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="1e608-112">È anche possibile scrivere convertitori personalizzati per personalizzare o estendere `[!OP.NO-LOC(System.Text.Json)]` con la funzionalità non inclusa nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="1e608-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="1e608-113">Gli scenari seguenti sono trattati più avanti in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="1e608-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="1e608-114">[Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="1e608-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="1e608-115">[Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="1e608-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="1e608-116">[Supporta la deserializzazione polimorfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="1e608-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="1e608-117">Modelli di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="1e608-117">Custom converter patterns</span></span>

<span data-ttu-id="1e608-118">Per la creazione di un convertitore personalizzato sono disponibili due modelli: il modello di base e il modello di Factory.</span><span class="sxs-lookup"><span data-stu-id="1e608-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="1e608-119">Il modello Factory è per i convertitori che gestiscono il tipo `Enum` o i generics aperti.</span><span class="sxs-lookup"><span data-stu-id="1e608-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="1e608-120">Il modello di base è per i tipi generici non generici e chiusi.</span><span class="sxs-lookup"><span data-stu-id="1e608-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="1e608-121">I convertitori per i tipi seguenti, ad esempio, richiedono il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="1e608-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="1e608-122">Di seguito sono riportati alcuni esempi di tipi che possono essere gestiti tramite il modello di base:</span><span class="sxs-lookup"><span data-stu-id="1e608-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="1e608-123">Il modello di base crea una classe in grado di gestire un tipo.</span><span class="sxs-lookup"><span data-stu-id="1e608-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="1e608-124">Il modello factory crea una classe che determina in fase di esecuzione quale tipo specifico è obbligatorio e crea dinamicamente il convertitore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1e608-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="1e608-125">Convertitore di base di esempio</span><span class="sxs-lookup"><span data-stu-id="1e608-125">Sample basic converter</span></span>

<span data-ttu-id="1e608-126">L'esempio seguente è un convertitore che esegue l'override della serializzazione predefinita per un tipo di dati esistente.</span><span class="sxs-lookup"><span data-stu-id="1e608-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="1e608-127">Il convertitore usa il formato mm/gg/aaaa `DateTimeOffset` per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="1e608-128">Convertitore di modelli Factory di esempio</span><span class="sxs-lookup"><span data-stu-id="1e608-128">Sample factory pattern converter</span></span>

<span data-ttu-id="1e608-129">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="1e608-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="1e608-130">Il codice segue il modello Factory perché il primo parametro di tipo generico `Enum` è e il secondo è aperto.</span><span class="sxs-lookup"><span data-stu-id="1e608-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="1e608-131">Il `CanConvert` metodo restituisce `true` solo per un `Dictionary` oggetto con due parametri generici, il primo dei quali `Enum` è un tipo.</span><span class="sxs-lookup"><span data-stu-id="1e608-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="1e608-132">Il convertitore interno ottiene un convertitore esistente per gestire qualsiasi tipo fornito in fase di esecuzione `TValue`per.</span><span class="sxs-lookup"><span data-stu-id="1e608-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="1e608-133">Il codice precedente è identico a quello visualizzato nel [dizionario di supporto con chiave non stringa](#support-dictionary-with-non-string-key) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1e608-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="1e608-134">Passaggi per seguire il modello di base</span><span class="sxs-lookup"><span data-stu-id="1e608-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="1e608-135">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello di base:</span><span class="sxs-lookup"><span data-stu-id="1e608-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="1e608-136">Creare una classe che deriva da <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> dove `T` è il tipo da serializzare e deserializzare.</span><span class="sxs-lookup"><span data-stu-id="1e608-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="1e608-137">Eseguire l' `Read` override del metodo per deserializzare il JSON in ingresso e convertirlo `T`nel tipo.</span><span class="sxs-lookup"><span data-stu-id="1e608-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="1e608-138">Usare la <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> che viene passata al metodo per leggere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="1e608-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="1e608-139">Eseguire l' `Write` override del metodo per serializzare l'oggetto in `T`ingresso di tipo.</span><span class="sxs-lookup"><span data-stu-id="1e608-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="1e608-140">Usare la <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> che viene passata al metodo per scrivere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="1e608-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="1e608-141">Eseguire l' `CanConvert` override del metodo solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="1e608-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="1e608-142">L'implementazione predefinita restituisce `true` quando il tipo da convertire è di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="1e608-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="1e608-143">Pertanto, i convertitori che supportano solo `T` i tipi non devono eseguire l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="1e608-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="1e608-144">Per un esempio di convertitore che deve eseguire l'override di questo metodo, vedere la sezione relativa alla [deserializzazione polimorfica](#support-polymorphic-deserialization) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1e608-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="1e608-145">È possibile fare riferimento al [codice sorgente dei convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) come implementazioni di riferimento per la scrittura di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1e608-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="1e608-146">Passaggi per seguire il modello Factory</span><span class="sxs-lookup"><span data-stu-id="1e608-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="1e608-147">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="1e608-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="1e608-148">Creare una classe che deriva da <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="1e608-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="1e608-149">Eseguire l' `CanConvert` override del metodo per restituire true quando il tipo da convertire è un oggetto che può essere gestito dal convertitore.</span><span class="sxs-lookup"><span data-stu-id="1e608-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="1e608-150">Se, ad esempio, il convertitore è `List<T>` per, può gestire `List<int>`solo `List<string>`, e `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="1e608-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="1e608-151">Eseguire l' `CreateConverter` override del metodo per restituire un'istanza di una classe Converter che gestirà il tipo da convertire fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e608-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="1e608-152">Creare la classe del convertitore di `CreateConverter` cui il metodo crea un'istanza.</span><span class="sxs-lookup"><span data-stu-id="1e608-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="1e608-153">Il modello Factory è obbligatorio per i generics aperti perché il codice per convertire un oggetto in e da una stringa non è lo stesso per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="1e608-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="1e608-154">Un convertitore per un tipo generico aperto (`List<T>`ad esempio) deve creare un convertitore per un tipo generico chiuso`List<DateTime>`, ad esempio, dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="1e608-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="1e608-155">Il codice deve essere scritto in modo da gestire ogni tipo generico chiuso che il convertitore è in grado di gestire.</span><span class="sxs-lookup"><span data-stu-id="1e608-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="1e608-156">Il `Enum` tipo è simile a un tipo generico aperto: un convertitore per `Enum` deve creare un convertitore per uno specifico `Enum` `WeekdaysEnum`, ad esempio, dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="1e608-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="1e608-157">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="1e608-157">Error handling</span></span>

<span data-ttu-id="1e608-158">Se è necessario generare un'eccezione nel codice di gestione degli errori, provare a generare <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> un oggetto senza un messaggio.</span><span class="sxs-lookup"><span data-stu-id="1e608-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="1e608-159">Questo tipo di eccezione crea automaticamente un messaggio che include il percorso della parte di JSON che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="1e608-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="1e608-160">L'istruzione `throw new JsonException();` , ad esempio, genera un messaggio di errore simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e608-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="1e608-161">Se si fornisce un messaggio, ad esempio `throw new JsonException("Error occurred")`, l'eccezione fornisce ancora il percorso nella <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="1e608-162">Registrare un convertitore personalizzato</span><span class="sxs-lookup"><span data-stu-id="1e608-162">Register a custom converter</span></span>

<span data-ttu-id="1e608-163">*Registrare* un convertitore personalizzato per fare in `Serialize` modo `Deserialize` che i metodi e lo usino.</span><span class="sxs-lookup"><span data-stu-id="1e608-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="1e608-164">Scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e608-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="1e608-165">Aggiungere un'istanza della classe Converter alla <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> raccolta.</span><span class="sxs-lookup"><span data-stu-id="1e608-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="1e608-166">Applicare l'attributo [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) alle proprietà che richiedono il convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="1e608-167">Applicare l'attributo [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) a una classe o a uno struct che rappresenta un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="1e608-168">Esempio di registrazione-raccolta Converters</span><span class="sxs-lookup"><span data-stu-id="1e608-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="1e608-169">Di seguito è riportato un esempio che <xref:System.ComponentModel.DateTimeOffsetConverter> rende il valore predefinito per le <xref:System.DateTimeOffset>proprietà di tipo:</span><span class="sxs-lookup"><span data-stu-id="1e608-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="1e608-170">Si supponga di serializzare un'istanza del tipo seguente:</span><span class="sxs-lookup"><span data-stu-id="1e608-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="1e608-171">Di seguito è riportato un esempio di output JSON che mostra il convertitore personalizzato usato:</span><span class="sxs-lookup"><span data-stu-id="1e608-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1e608-172">Il codice seguente usa lo stesso approccio per deserializzare usando il convertitore `DateTimeOffset` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="1e608-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="1e608-173">Esempio di registrazione-[JsonConverter] in una proprietà</span><span class="sxs-lookup"><span data-stu-id="1e608-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="1e608-174">Il codice seguente seleziona un convertitore personalizzato per la `Date` proprietà:</span><span class="sxs-lookup"><span data-stu-id="1e608-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="1e608-175">Il codice da serializzare `WeatherForecastWithConverterAttribute` non richiede l'uso `JsonSerializeOptions.Converters`di:</span><span class="sxs-lookup"><span data-stu-id="1e608-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="1e608-176">Anche il codice da deserializzare non richiede l'uso di `Converters`:</span><span class="sxs-lookup"><span data-stu-id="1e608-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="1e608-177">Esempio di registrazione-[JsonConverter] in un tipo</span><span class="sxs-lookup"><span data-stu-id="1e608-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="1e608-178">Di seguito è riportato il codice che consente di creare `[JsonConverter]` uno struct e di applicarvi l'attributo:</span><span class="sxs-lookup"><span data-stu-id="1e608-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="1e608-179">Ecco il convertitore personalizzato per lo struct precedente:</span><span class="sxs-lookup"><span data-stu-id="1e608-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="1e608-180">L' `[JsonConvert]` attributo dello struct registra il convertitore personalizzato come valore predefinito per le proprietà di tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="1e608-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="1e608-181">Il convertitore viene usato automaticamente sulla `TemperatureCelsius` proprietà del tipo seguente quando viene serializzato o deserializzato:</span><span class="sxs-lookup"><span data-stu-id="1e608-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="1e608-182">Precedenza di registrazione del convertitore</span><span class="sxs-lookup"><span data-stu-id="1e608-182">Converter registration precedence</span></span>

<span data-ttu-id="1e608-183">Durante la serializzazione o la deserializzazione, viene scelto un convertitore per ogni elemento JSON nell'ordine seguente, elencato dalla priorità più alta a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="1e608-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="1e608-184">`[JsonConverter]`applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="1e608-185">Convertitore aggiunto alla `Converters` raccolta.</span><span class="sxs-lookup"><span data-stu-id="1e608-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="1e608-186">`[JsonConverter]`applicato a un tipo di valore personalizzato o POCO.</span><span class="sxs-lookup"><span data-stu-id="1e608-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="1e608-187">Se nella `Converters` raccolta vengono registrati più convertitori personalizzati per un tipo, viene utilizzato il primo convertitore che restituisce true `CanConvert` per.</span><span class="sxs-lookup"><span data-stu-id="1e608-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="1e608-188">Un convertitore predefinito viene scelto solo se non è registrato alcun convertitore personalizzato applicabile.</span><span class="sxs-lookup"><span data-stu-id="1e608-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="1e608-189">Esempi di convertitore per scenari comuni</span><span class="sxs-lookup"><span data-stu-id="1e608-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="1e608-190">Le sezioni seguenti forniscono esempi di convertitore che affrontano alcuni scenari comuni non gestiti dalla funzionalità incorporata.</span><span class="sxs-lookup"><span data-stu-id="1e608-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="1e608-191">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="1e608-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="1e608-192">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="1e608-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="1e608-193">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="1e608-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="1e608-194">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="1e608-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="1e608-195">Quando si esegue la deserializzazione in una `object`proprietà di `JsonElement` tipo, viene creato un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1e608-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="1e608-196">Il motivo è che il deserializzatore non conosce il tipo CLR da creare e non tenta di indovinare.</span><span class="sxs-lookup"><span data-stu-id="1e608-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="1e608-197">Se, ad esempio, una proprietà JSON ha "true", il deserializzatore non deduce che il valore è `Boolean`un e se un elemento ha "01/01/2019", il deserializzatore non deduce che si tratta di `DateTime`un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1e608-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="1e608-198">L'inferenza del tipo può non essere corretta.</span><span class="sxs-lookup"><span data-stu-id="1e608-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="1e608-199">Se il deserializzatore analizza un numero JSON senza separatore decimale come `long`, che potrebbe causare problemi fuori intervallo se il valore è stato originariamente serializzato come `ulong` o. `BigInteger`</span><span class="sxs-lookup"><span data-stu-id="1e608-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="1e608-200">L'analisi di un numero con un separatore decimale come `double` potrebbe perdere precisione se il numero è stato originariamente serializzato come. `decimal`</span><span class="sxs-lookup"><span data-stu-id="1e608-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="1e608-201">Per gli scenari che richiedono l'inferenza del tipo, nel codice seguente viene `object` illustrato un convertitore personalizzato per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="1e608-202">Il codice esegue la conversione:</span><span class="sxs-lookup"><span data-stu-id="1e608-202">The code converts:</span></span>

* <span data-ttu-id="1e608-203">`true`e `false` a`Boolean`</span><span class="sxs-lookup"><span data-stu-id="1e608-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="1e608-204">Numeri senza decimali`long`</span><span class="sxs-lookup"><span data-stu-id="1e608-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="1e608-205">Numeri con un numero decimale a`double`</span><span class="sxs-lookup"><span data-stu-id="1e608-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="1e608-206">Data di`DateTime`</span><span class="sxs-lookup"><span data-stu-id="1e608-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="1e608-207">Stringhe`string`</span><span class="sxs-lookup"><span data-stu-id="1e608-207">Strings to `string`</span></span>
* <span data-ttu-id="1e608-208">Tutti gli altri elementi`JsonElement`</span><span class="sxs-lookup"><span data-stu-id="1e608-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="1e608-209">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="1e608-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="1e608-210">Di seguito è riportato un esempio `object` di tipo con proprietà:</span><span class="sxs-lookup"><span data-stu-id="1e608-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="1e608-211">L'esempio seguente di JSON da deserializzare contiene valori che verranno deserializzati come `DateTime`, `long`e: `string`</span><span class="sxs-lookup"><span data-stu-id="1e608-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="1e608-212">Senza il convertitore personalizzato, la deserializzazione inserisce `JsonElement` un oggetto in ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="1e608-213">Nella [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello `System.Text.Json.Serialization` spazio dei nomi sono disponibili altri esempi di convertitori personalizzati che gestiscono la `object` deserializzazione alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="1e608-214">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="1e608-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="1e608-215">Il supporto incorporato per le raccolte di dizionari è per `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="1e608-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="1e608-216">Ovvero la chiave deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="1e608-216">That is, the key must be a string.</span></span> <span data-ttu-id="1e608-217">Per supportare un dizionario con un numero intero o un altro tipo come chiave, è necessario un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="1e608-218">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="1e608-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="1e608-219">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="1e608-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="1e608-220">Il convertitore è in grado di serializzare e `TemperatureRanges` deserializzare la proprietà della classe seguente che `Enum`utilizza gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e608-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="1e608-221">L'output JSON dalla serializzazione è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e608-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="1e608-222">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello `System.Text.Json.Serialization` spazio dei nomi contiene altri esempi di convertitori personalizzati che gestiscono dizionari non di stringa.</span><span class="sxs-lookup"><span data-stu-id="1e608-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="1e608-223">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="1e608-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="1e608-224">Le funzionalità predefinite forniscono una gamma limitata di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non supportano affatto la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="1e608-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="1e608-225">La deserializzazione richiede un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="1e608-226">Si supponga, ad esempio, di disporre `Person` di una classe di base `Employee` astratta `Customer` , con classi derivate e.</span><span class="sxs-lookup"><span data-stu-id="1e608-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="1e608-227">La deserializzazione polimorfica significa che in fase di progettazione è possibile `Person` specificare come destinazione della deserializzazione e `Customer` gli `Employee` oggetti e in JSON vengono deserializzati correttamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e608-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="1e608-228">Durante la deserializzazione, è necessario trovare indizi che identifichino il tipo richiesto nel codice JSON.</span><span class="sxs-lookup"><span data-stu-id="1e608-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="1e608-229">I tipi di indizi disponibili variano in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="1e608-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="1e608-230">Ad esempio, una proprietà discriminatore potrebbe essere disponibile o potrebbe essere necessario basarsi sulla presenza o sull'assenza di una particolare proprietà.</span><span class="sxs-lookup"><span data-stu-id="1e608-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="1e608-231">La versione corrente di `System.Text.Json` non fornisce attributi per specificare come gestire gli scenari di deserializzazione polimorfica, quindi i convertitori personalizzati sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="1e608-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="1e608-232">Nel codice seguente viene illustrata una classe di base, due classi derivate e un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e608-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="1e608-233">Il convertitore usa una proprietà discriminatore per eseguire la deserializzazione polimorfica.</span><span class="sxs-lookup"><span data-stu-id="1e608-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="1e608-234">Il discriminatore di tipo non è incluso nelle definizioni di classe ma viene creato durante la serializzazione e viene letto durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="1e608-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="1e608-235">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="1e608-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="1e608-236">Il convertitore può deserializzare JSON creato con lo stesso convertitore da serializzare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e608-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="1e608-237">Il codice del convertitore nell'esempio precedente legge e scrive ogni proprietà manualmente.</span><span class="sxs-lookup"><span data-stu-id="1e608-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="1e608-238">In alternativa, è possibile `Deserialize` chiamare `Serialize` o per eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="1e608-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="1e608-239">Per un esempio, vedere [questo post di StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="1e608-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="1e608-240">Altri esempi di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="1e608-240">Other custom converter samples</span></span>

<span data-ttu-id="1e608-241">L'articolo [eseguire Newtonsoft.Json la System.Text.Json migrazione da a](system-text-json-migrate-from-newtonsoft-how-to.md) contiene esempi aggiuntivi di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1e608-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="1e608-242">La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nel codice `System.Text.Json.Serialization` sorgente include altri esempi di convertitore personalizzati, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e608-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="1e608-243">[Convertitore Int32 che converte il valore null in 0 per la deserializzazione](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="1e608-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="1e608-244">[Convertitore Int32 che consente di deserializzare sia i valori di stringa che di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="1e608-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="1e608-245">[Convertitore enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="1e608-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="1e608-246">[Elenco\<T> Converter che accetta dati esterni](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="1e608-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="1e608-247">[Long [] Converter che funziona con un elenco delimitato da virgole di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="1e608-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="1e608-248">Se è necessario creare un convertitore che modifichi il comportamento di un convertitore incorporato esistente, è possibile ottenere [il codice sorgente del convertitore esistente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) per fungere da punto di partenza per la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="1e608-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e608-249">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1e608-249">Additional resources</span></span>

* <span data-ttu-id="1e608-250">[Codice sorgente per convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="1e608-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="1e608-251">[Supporto di DateTime e DateTimeOffset inSystem.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="1e608-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="1e608-252">[System.Text.JsonPanoramica](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1e608-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="1e608-253">[Come usareSystem.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="1e608-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="1e608-254">[Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="1e608-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="1e608-255">[System.Text.JsonRiferimento API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1e608-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="1e608-256">[System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="1e608-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
