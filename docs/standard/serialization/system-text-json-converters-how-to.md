---
title: Come scrivere convertitori personalizzati per la serializzazione JSON-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 361818a0bda8863f8878b86e5fb377dc0faf5246
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73741892"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="4108b-102">Come scrivere convertitori personalizzati per la serializzazione JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="4108b-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="4108b-103">Questo articolo illustra come creare convertitori personalizzati per le classi di serializzazione JSON fornite nello spazio dei nomi <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="4108b-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="4108b-104">Per un'introduzione ai `System.Text.Json`, vedere [come serializzare e deserializzare JSON in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="4108b-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="4108b-105">Un *convertitore* è una classe che converte un oggetto o un valore in e da JSON.</span><span class="sxs-lookup"><span data-stu-id="4108b-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="4108b-106">Lo spazio dei nomi `System.Text.Json` dispone di convertitori predefiniti per la maggior parte dei tipi primitivi con mapping alle primitive JavaScript.</span><span class="sxs-lookup"><span data-stu-id="4108b-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="4108b-107">È possibile scrivere convertitori personalizzati:</span><span class="sxs-lookup"><span data-stu-id="4108b-107">You can write custom converters:</span></span>

* <span data-ttu-id="4108b-108">Per eseguire l'override del comportamento predefinito di un convertitore incorporato.</span><span class="sxs-lookup"><span data-stu-id="4108b-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="4108b-109">È ad esempio possibile che si desideri che i valori `DateTime` siano rappresentati dal formato mm/gg/aaaa anziché dal formato ISO 8601-1:2019 predefinito.</span><span class="sxs-lookup"><span data-stu-id="4108b-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="4108b-110">Per supportare un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-110">To support a custom value type.</span></span> <span data-ttu-id="4108b-111">Ad esempio, uno struct `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="4108b-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="4108b-112">È anche possibile scrivere convertitori personalizzati per estendere `System.Text.Json` con funzionalità non incluse nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="4108b-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="4108b-113">Gli scenari seguenti sono trattati più avanti in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="4108b-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="4108b-114">[Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4108b-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4108b-115">[Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4108b-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="4108b-116">[Supporta la deserializzazione polimorfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4108b-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="4108b-117">Modelli di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="4108b-117">Custom converter patterns</span></span>

<span data-ttu-id="4108b-118">Per la creazione di un convertitore personalizzato sono disponibili due modelli: il modello di base e il modello di Factory.</span><span class="sxs-lookup"><span data-stu-id="4108b-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="4108b-119">Il modello Factory è per i convertitori che gestiscono il tipo `Enum` o i generics aperti.</span><span class="sxs-lookup"><span data-stu-id="4108b-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="4108b-120">Il modello di base è per i tipi generici non generici e chiusi.</span><span class="sxs-lookup"><span data-stu-id="4108b-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="4108b-121">I convertitori per i tipi seguenti, ad esempio, richiedono il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="4108b-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="4108b-122">Di seguito sono riportati alcuni esempi di tipi che possono essere gestiti tramite il modello di base:</span><span class="sxs-lookup"><span data-stu-id="4108b-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="4108b-123">Il modello di base crea una classe in grado di gestire un tipo.</span><span class="sxs-lookup"><span data-stu-id="4108b-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="4108b-124">Il modello factory crea una classe che determina in fase di esecuzione quale tipo specifico è obbligatorio e crea dinamicamente il convertitore appropriato.</span><span class="sxs-lookup"><span data-stu-id="4108b-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="4108b-125">Convertitore di base di esempio</span><span class="sxs-lookup"><span data-stu-id="4108b-125">Sample basic converter</span></span>

<span data-ttu-id="4108b-126">L'esempio seguente è un convertitore che esegue l'override della serializzazione predefinita per un tipo di dati esistente.</span><span class="sxs-lookup"><span data-stu-id="4108b-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="4108b-127">Il convertitore usa il formato mm/gg/aaaa per le proprietà `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="4108b-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

```csharp
private class ExampleDateTimeOffsetConverter : JsonConverter<DateTimeOffset>
{
    public override DateTimeOffset Read(
        ref Utf8JsonReader reader, 
        Type typeToConvert, 
        JsonSerializerOptions options)
    {
        return DateTimeOffset.ParseExact(reader.GetString(), 
            "MM/dd/yyyy", CultureInfo.InvariantCulture);
    }

    public override void Write(
        Utf8JsonWriter writer, 
        DateTimeOffset value, 
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString(
            "MM/dd/yyyy", CultureInfo.InvariantCulture));
    }
}
```

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="4108b-128">Convertitore di modelli Factory di esempio</span><span class="sxs-lookup"><span data-stu-id="4108b-128">Sample factory pattern converter</span></span>

<span data-ttu-id="4108b-129">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4108b-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="4108b-130">Il codice segue il modello Factory perché il primo parametro di tipo generico è `Enum` e il secondo è aperto.</span><span class="sxs-lookup"><span data-stu-id="4108b-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="4108b-131">Il metodo `CanConvert` restituisce `true` solo per un `Dictionary` con due parametri generici, il primo dei quali è un tipo `Enum`.</span><span class="sxs-lookup"><span data-stu-id="4108b-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="4108b-132">Il convertitore interno ottiene un convertitore esistente per gestire qualsiasi tipo fornito in fase di esecuzione per `TValue`.</span><span class="sxs-lookup"><span data-stu-id="4108b-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

<span data-ttu-id="4108b-133">Il codice precedente è identico a quello visualizzato nel [dizionario di supporto con chiave non stringa](#support-dictionary-with-non-string-key) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4108b-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="4108b-134">Passaggi per seguire il modello di base</span><span class="sxs-lookup"><span data-stu-id="4108b-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="4108b-135">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello di base:</span><span class="sxs-lookup"><span data-stu-id="4108b-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="4108b-136">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverter%601> dove `T` è il tipo da serializzare e deserializzare.</span><span class="sxs-lookup"><span data-stu-id="4108b-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="4108b-137">Eseguire l'override del metodo `Read` per deserializzare il codice JSON in ingresso e convertirlo nel tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4108b-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="4108b-138">Usare il <xref:System.Text.Json.Utf8JsonReader> passato al metodo per leggere il file JSON.</span><span class="sxs-lookup"><span data-stu-id="4108b-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="4108b-139">Eseguire l'override del metodo `Write` per serializzare l'oggetto in ingresso di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4108b-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="4108b-140">Usare il <xref:System.Text.Json.Utf8JsonWriter> passato al metodo per scrivere il codice JSON.</span><span class="sxs-lookup"><span data-stu-id="4108b-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="4108b-141">Eseguire l'override del metodo `CanConvert` solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="4108b-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="4108b-142">L'implementazione predefinita restituisce `true` quando il tipo da convertire è di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="4108b-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="4108b-143">Pertanto, i convertitori che supportano solo il tipo `T` non devono eseguire l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4108b-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="4108b-144">Per un esempio di convertitore che deve eseguire l'override di questo metodo, vedere la sezione relativa alla [deserializzazione polimorfica](#support-polymorphic-deserialization) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4108b-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="4108b-145">È possibile fare riferimento al [codice sorgente dei convertitori predefiniti](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) come implementazioni di riferimento per la scrittura di convertitori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4108b-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="4108b-146">Passaggi per seguire il modello Factory</span><span class="sxs-lookup"><span data-stu-id="4108b-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="4108b-147">Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello Factory:</span><span class="sxs-lookup"><span data-stu-id="4108b-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="4108b-148">Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="4108b-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="4108b-149">Eseguire l'override del metodo `CanConvert` per restituire true quando il tipo da convertire è quello che può essere gestito dal convertitore.</span><span class="sxs-lookup"><span data-stu-id="4108b-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="4108b-150">Ad esempio, se il convertitore è per `List<T>` potrebbe gestire solo `List<int>`, `List<string>`e `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="4108b-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="4108b-151">Eseguire l'override del metodo `CreateConverter` per restituire un'istanza di una classe Converter che gestirà il tipo da convertire fornito in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4108b-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="4108b-152">Creare la classe del convertitore di cui il metodo `CreateConverter` crea un'istanza.</span><span class="sxs-lookup"><span data-stu-id="4108b-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="4108b-153">Il modello Factory è obbligatorio per i generics aperti perché il codice per convertire un oggetto in e da una stringa non è lo stesso per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="4108b-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="4108b-154">Un convertitore per un tipo generico aperto (ad esempio`List<T>`) deve creare un convertitore per un tipo generico chiuso (ad esempio,`List<DateTime>`) dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4108b-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="4108b-155">Il codice deve essere scritto in modo da gestire ogni tipo generico chiuso che il convertitore è in grado di gestire.</span><span class="sxs-lookup"><span data-stu-id="4108b-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="4108b-156">Il tipo di `Enum` è simile a un tipo generico aperto: un convertitore per `Enum` deve creare un convertitore per un `Enum` specifico (ad esempio,`WeekdaysEnum`) dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4108b-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="4108b-157">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="4108b-157">Error handling</span></span>

<span data-ttu-id="4108b-158">Se è necessario generare un'eccezione nel codice di gestione degli errori, provare a generare un <xref:System.Text.Json.JsonException> senza un messaggio.</span><span class="sxs-lookup"><span data-stu-id="4108b-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="4108b-159">Questo tipo di eccezione crea automaticamente un messaggio che include il percorso della parte di JSON che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4108b-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="4108b-160">Ad esempio, l'istruzione `throw new JsonException();` genera un messaggio di errore simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4108b-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="4108b-161">Se si fornisce un messaggio, ad esempio `throw new JsonException("Error occurred)`, l'eccezione fornisce ancora il percorso nella proprietà <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="4108b-161">If you do provide a message (for example, `throw new JsonException("Error occurred)`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="4108b-162">Registrare un convertitore personalizzato</span><span class="sxs-lookup"><span data-stu-id="4108b-162">Register a custom converter</span></span>

<span data-ttu-id="4108b-163">*Registrare* un convertitore personalizzato per fare in modo che i metodi `Serialize` e `Deserialize` lo usino.</span><span class="sxs-lookup"><span data-stu-id="4108b-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="4108b-164">Scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="4108b-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="4108b-165">Aggiungere un'istanza della classe Converter alla raccolta <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4108b-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="4108b-166">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) alle proprietà che richiedono il convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="4108b-167">Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una classe o a uno struct che rappresenta un tipo di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="4108b-168">Esempio di registrazione-raccolta Converters</span><span class="sxs-lookup"><span data-stu-id="4108b-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="4108b-169">Di seguito è riportato un esempio che rende il `ExampleDateTimeOffsetConverter` il valore predefinito per le proprietà di tipo `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="4108b-169">Here's an example that makes the `ExampleDateTimeOffsetConverter` the default for properties of type `DateTimeOffset`:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4108b-170">Si supponga di serializzare il tipo seguente:</span><span class="sxs-lookup"><span data-stu-id="4108b-170">Suppose you serialize the following type:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="4108b-171">Di seguito è riportato un esempio di output JSON che mostra il convertitore personalizzato usato:</span><span class="sxs-lookup"><span data-stu-id="4108b-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4108b-172">Il codice seguente usa lo stesso approccio per deserializzare usando il convertitore di `DateTimeOffset` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="4108b-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="4108b-173">Esempio di registrazione-[JsonConverter] in una proprietà</span><span class="sxs-lookup"><span data-stu-id="4108b-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="4108b-174">Il codice seguente consente di selezionare un convertitore personalizzato per la proprietà `Date`:</span><span class="sxs-lookup"><span data-stu-id="4108b-174">The following code selects a custom converter for the `Date` property:</span></span>

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="4108b-175">Il codice per serializzare e deserializzare `WeatherForecastWithConverter` non richiede l'uso di `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="4108b-175">The code to serialize and deserialize `WeatherForecastWithConverter` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="4108b-176">Esempio di registrazione-[JsonConverter] in un tipo</span><span class="sxs-lookup"><span data-stu-id="4108b-176">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="4108b-177">Di seguito è riportato il codice che consente di creare uno struct e di applicare l'attributo `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="4108b-177">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

```csharp
[JsonConverter(typeof(TemperatureConverter))]
public struct Temperature
{
    public Temperature(int degrees, bool celsius)
    {
        _degrees = degrees;
        _isCelsius = celsius;
    }
    private bool _isCelsius;
    private int _degrees;
    public int Degrees => _degrees;
    public bool IsCelsius => _isCelsius; 
    public bool IsFahrenheit => !_isCelsius;
    public override string ToString() =>
        $"{_degrees.ToString()}{(_isCelsius ? "C" : "F")}";
    public static Temperature Parse(string input)
    {
        int degrees = int.Parse(input.Substring(0, input.Length - 1));
        bool celsius = (input.Substring(input.Length - 1) == "C");
        return new Temperature(degrees, celsius);
    }
}
```

<span data-ttu-id="4108b-178">Ecco il convertitore personalizzato per lo struct precedente:</span><span class="sxs-lookup"><span data-stu-id="4108b-178">Here's the custom converter for the preceding struct:</span></span>

```csharp
public class TemperatureConverter : JsonConverter<Temperature>
{
    public override Temperature Read(
        ref Utf8JsonReader reader,
        Type typeToConvert,
        JsonSerializerOptions options)
    {
        Debug.Assert(typeToConvert == typeof(Temperature));
        return Temperature.Parse(reader.GetString());
    }

    public override void Write(
        Utf8JsonWriter writer,
        Temperature value,
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString());
    }
}
```

<span data-ttu-id="4108b-179">L'attributo `[JsonConvert]` nello struct registra il convertitore personalizzato come valore predefinito per le proprietà di tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="4108b-179">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="4108b-180">Il convertitore viene usato automaticamente nella proprietà `TemperatureC` del tipo seguente quando viene serializzato o deserializzato:</span><span class="sxs-lookup"><span data-stu-id="4108b-180">The converter is automatically used on the `TemperatureC` property of the following type when you serialize or deserialize it:</span></span>

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a><span data-ttu-id="4108b-181">Precedenza di registrazione del convertitore</span><span class="sxs-lookup"><span data-stu-id="4108b-181">Converter registration precedence</span></span>

<span data-ttu-id="4108b-182">Durante la serializzazione o la deserializzazione, viene scelto un convertitore per ogni elemento JSON nell'ordine seguente, elencato dalla priorità più alta a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="4108b-182">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="4108b-183">`[JsonConverter]` applicato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="4108b-183">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="4108b-184">Convertitore aggiunto alla raccolta di `Converters`.</span><span class="sxs-lookup"><span data-stu-id="4108b-184">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="4108b-185">`[JsonConverter]` applicato a un tipo di valore personalizzato o POCO.</span><span class="sxs-lookup"><span data-stu-id="4108b-185">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="4108b-186">Se nella raccolta `Converters` vengono registrati più convertitori personalizzati per un tipo, viene utilizzato il primo convertitore che restituisce true per `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="4108b-186">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="4108b-187">Un convertitore predefinito viene scelto solo se non è registrato alcun convertitore personalizzato applicabile.</span><span class="sxs-lookup"><span data-stu-id="4108b-187">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="4108b-188">Esempi di convertitore per scenari comuni</span><span class="sxs-lookup"><span data-stu-id="4108b-188">Converter samples for common scenarios</span></span>

<span data-ttu-id="4108b-189">Le sezioni seguenti forniscono esempi di convertitore che affrontano alcuni scenari comuni non gestiti dalla funzionalità incorporata.</span><span class="sxs-lookup"><span data-stu-id="4108b-189">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="4108b-190">Deserializzare i tipi dedotti nelle proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="4108b-190">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="4108b-191">Quando si esegue la deserializzazione in una proprietà di tipo `Object`, viene creato un oggetto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="4108b-191">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="4108b-192">Il motivo è che il deserializzatore non conosce il tipo CLR da creare e non tenta di indovinare.</span><span class="sxs-lookup"><span data-stu-id="4108b-192">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="4108b-193">Se, ad esempio, una proprietà JSON ha "true", il deserializzatore non deduce che il valore è un `Boolean`e se un elemento ha "01/01/2019", il deserializzatore non deduce che si tratta di un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="4108b-193">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="4108b-194">L'inferenza del tipo può non essere corretta.</span><span class="sxs-lookup"><span data-stu-id="4108b-194">Type inference can be inaccurate.</span></span> <span data-ttu-id="4108b-195">Se il deserializzatore analizza un numero JSON senza separatore decimale come `long`, ciò potrebbe causare problemi fuori intervallo se il valore è stato serializzato originariamente come `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="4108b-195">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="4108b-196">L'analisi di un numero con un separatore decimale come `double` potrebbe perdere precisione se il numero è stato originariamente serializzato come `decimal`.</span><span class="sxs-lookup"><span data-stu-id="4108b-196">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="4108b-197">Per gli scenari che richiedono l'inferenza del tipo, nel codice seguente viene illustrato un convertitore personalizzato per `Object` proprietà.</span><span class="sxs-lookup"><span data-stu-id="4108b-197">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="4108b-198">Il codice esegue la conversione:</span><span class="sxs-lookup"><span data-stu-id="4108b-198">The code converts:</span></span>

* <span data-ttu-id="4108b-199">`true` e `false` per `Boolean`</span><span class="sxs-lookup"><span data-stu-id="4108b-199">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="4108b-200">Numeri da `long` o `double`</span><span class="sxs-lookup"><span data-stu-id="4108b-200">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="4108b-201">Data di `DateTime`</span><span class="sxs-lookup"><span data-stu-id="4108b-201">Dates to `DateTime`</span></span>
* <span data-ttu-id="4108b-202">Stringhe da `string`</span><span class="sxs-lookup"><span data-stu-id="4108b-202">Strings to `string`</span></span>
* <span data-ttu-id="4108b-203">Tutti gli altri elementi da `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="4108b-203">Everything else to `JsonElement`</span></span>

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ObjectToInferredTypesConverter
        : JsonConverter<object>
    {
        public override object Read(
            ref Utf8JsonReader reader,
            Type typeToConvert,
            JsonSerializerOptions options)
        {
            if (reader.TokenType == JsonTokenType.True)
            {
                return true;
            }

            if (reader.TokenType == JsonTokenType.False)
            {
                return false;
            }

            if (reader.TokenType == JsonTokenType.Number)
            {
                if (reader.TryGetInt64(out long l))
                {
                    return l;
                }

                return reader.GetDouble();
            }

            if (reader.TokenType == JsonTokenType.String)
            {
                if (reader.TryGetDateTime(out DateTime datetime))
                {
                    return datetime;
                }

                return reader.GetString();
            }

            // Use JsonElement as fallback.
            // Newtonsoft uses JArray or JObject.
            using (JsonDocument document = JsonDocument.ParseValue(ref reader))
            {
                return document.RootElement.Clone();
            }
        }

        public override void Write(
            Utf8JsonWriter writer,
            object value,
            JsonSerializerOptions options)
        {
            throw new InvalidOperationException("Should not get here.");
        }
    }
}
```

<span data-ttu-id="4108b-204">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4108b-204">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

<span data-ttu-id="4108b-205">Di seguito è riportato un esempio di tipo con una proprietà dell'oggetto:</span><span class="sxs-lookup"><span data-stu-id="4108b-205">Here's an example type with an Object property:</span></span>

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

<span data-ttu-id="4108b-206">L'esempio seguente di JSON da deserializzare contiene valori che verranno deserializzati come `DateTime`, `long`e `string`:</span><span class="sxs-lookup"><span data-stu-id="4108b-206">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="4108b-207">Senza il convertitore personalizzato, la deserializzazione inserisce una `JsonElement` in ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="4108b-207">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="4108b-208">La [cartella unit test](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono la deserializzazione nelle proprietà degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="4108b-208">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="4108b-209">Dizionario di supporto con chiave non di stringa</span><span class="sxs-lookup"><span data-stu-id="4108b-209">Support Dictionary with non-string key</span></span>

<span data-ttu-id="4108b-210">Il supporto incorporato per le raccolte di dizionari è per `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4108b-210">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="4108b-211">Ovvero la chiave deve essere una stringa.</span><span class="sxs-lookup"><span data-stu-id="4108b-211">That is, the key must be a string.</span></span> <span data-ttu-id="4108b-212">Per supportare un dizionario con un numero intero o un altro tipo come chiave, è necessario un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-212">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="4108b-213">Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="4108b-213">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

<span data-ttu-id="4108b-214">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4108b-214">The following code registers the converter:</span></span>

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

<span data-ttu-id="4108b-215">Il convertitore è in grado di serializzare e deserializzare la proprietà `TemperatureRanges` della classe seguente che usa i `Enum`seguenti:</span><span class="sxs-lookup"><span data-stu-id="4108b-215">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

```csharp
public class WeatherForecastWithEnumDictionary
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public Dictionary<SummaryWordsEnum, int> TemperatureRanges { get; set; }
}

public enum SummaryWordsEnum
{
    Cold, Hot
}
```

<span data-ttu-id="4108b-216">L'output JSON dalla serializzazione è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4108b-216">The JSON output from serialization looks like the following example:</span></span>

```json
{

  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="4108b-217">La [cartella unit test](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono dizionari non di stringa.</span><span class="sxs-lookup"><span data-stu-id="4108b-217">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="4108b-218">Supportare la deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="4108b-218">Support polymorphic deserialization</span></span>

<span data-ttu-id="4108b-219">La [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) non richiede un convertitore personalizzato, ma la deserializzazione richiede un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-219">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="4108b-220">Si supponga, ad esempio, di disporre di una classe di base astratta `Person`, con `Employee` e `Customer` classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4108b-220">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="4108b-221">La deserializzazione polimorfica significa che in fase di progettazione è possibile specificare `Person` come destinazione della deserializzazione e gli oggetti `Customer` e `Employee` nel file JSON vengono deserializzati correttamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4108b-221">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="4108b-222">Durante la deserializzazione, è necessario trovare indizi che identifichino il tipo richiesto nel codice JSON.</span><span class="sxs-lookup"><span data-stu-id="4108b-222">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="4108b-223">I tipi di indizi disponibili variano in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="4108b-223">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="4108b-224">Ad esempio, una proprietà discriminatore potrebbe essere disponibile o potrebbe essere necessario basarsi sulla presenza o sull'assenza di una particolare proprietà.</span><span class="sxs-lookup"><span data-stu-id="4108b-224">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="4108b-225">La versione corrente di `System.Text.Json` non fornisce attributi per specificare la modalità di gestione degli scenari di deserializzazione polimorfica, quindi i convertitori personalizzati sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4108b-225">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="4108b-226">Nel codice seguente viene illustrata una classe di base, due classi derivate e un convertitore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4108b-226">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="4108b-227">Il convertitore usa una proprietà discriminatore per eseguire la deserializzazione polimorfica.</span><span class="sxs-lookup"><span data-stu-id="4108b-227">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="4108b-228">Il discriminatore di tipo non è incluso nelle definizioni di classe ma viene creato durante la serializzazione e viene letto durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4108b-228">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

```csharp
public class Person
{
    public string Name { get; set; }
}

public class Customer : Person
{
    public decimal CreditLimit { get; set; }
}

public class Employee : Person
{
    public string OfficeNumber { get; set; }
}
```

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class PersonConverterWithTypeDiscriminator : JsonConverter<Person>
    {
        enum TypeDiscriminator
        {
            Customer = 1,
            Employee = 2
        }

        public override bool CanConvert(Type typeToConvert)
        {
            return typeof(Person).IsAssignableFrom(typeToConvert);
        }

        public override Person Read(ref Utf8JsonReader reader, Type typeToConvert, JsonSerializerOptions options)
        {
            if (reader.TokenType != JsonTokenType.StartObject)
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.PropertyName)
            {
                throw new JsonException();
            }

            string propertyName = reader.GetString();
            if (propertyName != "TypeDiscriminator")
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.Number)
            {
                throw new JsonException();
            }

            Person value;
            TypeDiscriminator typeDiscriminator = (TypeDiscriminator)reader.GetInt32();
            switch (typeDiscriminator)
            {
                case TypeDiscriminator.Customer:
                    value = new Customer();
                    break;

                case TypeDiscriminator.Employee:
                    value = new Employee();
                    break;

                default:
                    throw new JsonException();
            }

            while (reader.Read())
            {
                if (reader.TokenType == JsonTokenType.EndObject)
                {
                    return value;
                }

                if (reader.TokenType == JsonTokenType.PropertyName)
                {
                    propertyName = reader.GetString();
                    reader.Read();
                    switch (propertyName)
                    {
                        case "CreditLimit":
                            decimal creditLimit = reader.GetDecimal();
                            ((Customer)value).CreditLimit = creditLimit;
                            break;
                        case "OfficeNumber":
                            string officeNumber = reader.GetString();
                            ((Employee)value).OfficeNumber = officeNumber;
                            break;
                        case "Name":
                            string name = reader.GetString();
                            value.Name = name;
                            break;
                    }
                }
            }

            throw new JsonException();
        }

        public override void Write(Utf8JsonWriter writer, Person value, JsonSerializerOptions options)
        {
            writer.WriteStartObject();

            if (value is Customer customer)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Customer);
                writer.WriteNumber("CreditLimit", customer.CreditLimit);
            }
            else if (value is Employee employee)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Employee);
                writer.WriteString("OfficeNumber", employee.OfficeNumber);
            }

            writer.WriteString("Name", value.Name);

            writer.WriteEndObject();
        }
    }
}
```

<span data-ttu-id="4108b-229">Il codice seguente registra il convertitore:</span><span class="sxs-lookup"><span data-stu-id="4108b-229">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

<span data-ttu-id="4108b-230">Il convertitore può deserializzare JSON creato con lo stesso convertitore da serializzare, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4108b-230">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="4108b-231">Altri esempi di convertitore personalizzati</span><span class="sxs-lookup"><span data-stu-id="4108b-231">Other custom converter samples</span></span>

<span data-ttu-id="4108b-232">La [cartella unit test](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) nel codice sorgente `System.Text.Json.Serialization` include altri esempi di convertitore personalizzati, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4108b-232">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="4108b-233">`Int32` Converter che converte il valore null in 0 durante la deserializzazione</span><span class="sxs-lookup"><span data-stu-id="4108b-233">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="4108b-234">`Int32` Converter che consente di deserializzare sia i valori di stringa che di numeri</span><span class="sxs-lookup"><span data-stu-id="4108b-234">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="4108b-235">convertitore di `Enum`</span><span class="sxs-lookup"><span data-stu-id="4108b-235">`Enum` converter</span></span>
* <span data-ttu-id="4108b-236">convertitore `List<T>` che accetta dati esterni</span><span class="sxs-lookup"><span data-stu-id="4108b-236">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="4108b-237">`Long[]` convertitore che funziona con un elenco delimitato da virgole di numeri</span><span class="sxs-lookup"><span data-stu-id="4108b-237">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="4108b-238">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4108b-238">Additional resources</span></span>

* [<span data-ttu-id="4108b-239">Panoramica di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4108b-239">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="4108b-240">Informazioni di riferimento sull'API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4108b-240">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="4108b-241">Come usare System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4108b-241">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="4108b-242">Codice sorgente per convertitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="4108b-242">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="4108b-243">Problemi di GitHub correlati a convertitori personalizzati per `System.Text.Json`</span><span class="sxs-lookup"><span data-stu-id="4108b-243">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="4108b-244">36639 Introduzione ai convertitori personalizzati</span><span class="sxs-lookup"><span data-stu-id="4108b-244">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="4108b-245">38713 informazioni sulla deserializzazione nell'oggetto</span><span class="sxs-lookup"><span data-stu-id="4108b-245">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="4108b-246">40120 informazioni sui dizionari non di stringa</span><span class="sxs-lookup"><span data-stu-id="4108b-246">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="4108b-247">37787 informazioni sulla deserializzazione polimorfica</span><span class="sxs-lookup"><span data-stu-id="4108b-247">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
