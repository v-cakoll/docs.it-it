---
title: Supporto di DateTime e DateTimeOffset in System.Text.Json
description: Panoramica della modalità di supporto dei tipi DateTime e DateTimeOffset nella libreria System. Text. JSON.
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 5bff01b10b2bdea4fdcfee86e348c47f44d50103
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374481"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a><span data-ttu-id="e2b92-103">Supporto di DateTime e DateTimeOffset in System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="e2b92-103">DateTime and DateTimeOffset support in System.Text.Json</span></span>

<span data-ttu-id="e2b92-104">La libreria System. Text. JSON analizza e scrive <xref:System.DateTime> i valori e <xref:System.DateTimeOffset> in base al profilo esteso ISO 8601:-2019.</span><span class="sxs-lookup"><span data-stu-id="e2b92-104">The System.Text.Json library parses and writes <xref:System.DateTime> and <xref:System.DateTimeOffset> values according to the ISO 8601:-2019 extended profile.</span></span>
<span data-ttu-id="e2b92-105">I [convertitori](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) forniscono supporto personalizzato per la serializzazione e la deserializzazione con <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e2b92-105">[Converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) provide custom support for serializing and deserializing with <xref:System.Text.Json.JsonSerializer>.</span></span>

## <a name="support-for-the-iso-8601-12019-format"></a><span data-ttu-id="e2b92-106">Supporto per il formato ISO 8601-1:2019</span><span class="sxs-lookup"><span data-stu-id="e2b92-106">Support for the ISO 8601-1:2019 format</span></span>

<span data-ttu-id="e2b92-107">I <xref:System.Text.Json.JsonSerializer>tipi <xref:System.Text.Json.Utf8JsonReader>, ,<xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> e <xref:System.Text.Json.JsonElement> analizzano e scrivono<xref:System.DateTimeOffset> le rappresentazioni di testo in base al profilo esteso del formato ISO 8601-1:2019, ad esempio 2019-07-26T16 : 59:57-05:00.</span><span class="sxs-lookup"><span data-stu-id="e2b92-107">The <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>, and <xref:System.Text.Json.JsonElement> types parse and write <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations according to the extended profile of the ISO 8601-1:2019 format; for example, 2019-07-26T16:59:57-05:00.</span></span>

<span data-ttu-id="e2b92-108"><xref:System.DateTime>i <xref:System.DateTimeOffset> dati e possono essere serializzati <xref:System.Text.Json.JsonSerializer>con:</span><span class="sxs-lookup"><span data-stu-id="e2b92-108"><xref:System.DateTime> and <xref:System.DateTimeOffset> data can be serialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

<span data-ttu-id="e2b92-109">Possono anche essere deserializzati con <xref:System.Text.Json.JsonSerializer>:</span><span class="sxs-lookup"><span data-stu-id="e2b92-109">They can also be deserialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

<span data-ttu-id="e2b92-110">Con le opzioni predefinite, <xref:System.DateTime> le <xref:System.DateTimeOffset> rappresentazioni di input e testo devono essere conformi al profilo ISO 8601-1:2019 esteso.</span><span class="sxs-lookup"><span data-stu-id="e2b92-110">With default options, input <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations must conform to the extended ISO 8601-1:2019 profile.</span></span>
<span data-ttu-id="e2b92-111">Il tentativo di deserializzare le rappresentazioni che non sono conformi <xref:System.Text.Json.JsonSerializer> al profilo causerà la generazione di un' <xref:System.Text.Json.JsonException>operazione:</span><span class="sxs-lookup"><span data-stu-id="e2b92-111">Attempting to deserialize representations that don't conform to the profile will cause <xref:System.Text.Json.JsonSerializer> to throw a <xref:System.Text.Json.JsonException>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

<span data-ttu-id="e2b92-112">Fornisce accesso strutturato al contenuto di un payload JSON, incluse <xref:System.DateTime> le rappresentazioni e <xref:System.DateTimeOffset>. <xref:System.Text.Json.JsonDocument></span><span class="sxs-lookup"><span data-stu-id="e2b92-112">The <xref:System.Text.Json.JsonDocument> provides structured access to the contents of a JSON payload, including <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span> <span data-ttu-id="e2b92-113">Nell'esempio seguente viene illustrato come, quando viene fornita una raccolta di temperature, è possibile calcolare la temperatura media del lunedì:</span><span class="sxs-lookup"><span data-stu-id="e2b92-113">The example below shows how, when given a collection of temperatures, the average temperature on Mondays can be calculated:</span></span>

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

<span data-ttu-id="e2b92-114">Il tentativo di calcolare la temperatura media in base a un payload con rappresentazioni non <xref:System.DateTime> conformi <xref:System.Text.Json.JsonDocument> causerà la <xref:System.FormatException>generazione di un'operazione:</span><span class="sxs-lookup"><span data-stu-id="e2b92-114">Attempting to compute the average temperature given a payload with non-compliant <xref:System.DateTime> representations will cause <xref:System.Text.Json.JsonDocument> to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

<span data-ttu-id="e2b92-115">I dati e <xref:System.Text.Json.Utf8JsonWriter> le <xref:System.DateTime> scritture di <xref:System.DateTimeOffset> livello inferiore:</span><span class="sxs-lookup"><span data-stu-id="e2b92-115">The lower level <xref:System.Text.Json.Utf8JsonWriter> writes <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<span data-ttu-id="e2b92-116"><xref:System.Text.Json.Utf8JsonReader><xref:System.DateTime> analizza e<xref:System.DateTimeOffset> dati:</span><span class="sxs-lookup"><span data-stu-id="e2b92-116"><xref:System.Text.Json.Utf8JsonReader> parses <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

<span data-ttu-id="e2b92-117">Il tentativo di leggere formati non conformi con <xref:System.Text.Json.Utf8JsonReader> comporterà la generazione di <xref:System.FormatException>un'operazione:</span><span class="sxs-lookup"><span data-stu-id="e2b92-117">Attempting to read non-compliant formats with <xref:System.Text.Json.Utf8JsonReader> will cause it to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a><span data-ttu-id="e2b92-118">Supporto personalizzato per <xref:System.DateTime> e <xref:System.DateTimeOffset> in<xref:System.Text.Json.JsonSerializer></span><span class="sxs-lookup"><span data-stu-id="e2b92-118">Custom support for <xref:System.DateTime> and <xref:System.DateTimeOffset> in <xref:System.Text.Json.JsonSerializer></span></span>

<span data-ttu-id="e2b92-119">Se si desidera che il serializzatore esegua l'analisi o la formattazione personalizzata, è possibile implementare [convertitori personalizzati](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="e2b92-119">If you want the serializer to perform custom parsing or formatting, you can implement [custom converters](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).</span></span>
<span data-ttu-id="e2b92-120">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="e2b92-120">Here are a few examples:</span></span>

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a><span data-ttu-id="e2b92-121">Con `DateTime(Offset).Parse` e`DateTime(Offset).ToString`</span><span class="sxs-lookup"><span data-stu-id="e2b92-121">Using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`</span></span>

<span data-ttu-id="e2b92-122">Se non è possibile determinare i formati delle rappresentazioni <xref:System.DateTimeOffset> di input <xref:System.DateTime> o testo, è possibile `DateTime(Offset).Parse` usare il metodo nella logica di lettura del convertitore.</span><span class="sxs-lookup"><span data-stu-id="e2b92-122">If you can't determine the formats of your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations, you can use the `DateTime(Offset).Parse` method in your converter read logic.</span></span> <span data-ttu-id="e2b92-123">In questo modo è possibile utilizzare. Supporto completo di NET per l'analisi di <xref:System.DateTime> vari <xref:System.DateTimeOffset> formati di testo, incluse le stringhe non ISO 8601 e i formati ISO 8601 che non sono conformi al profilo ISO 8601-1:2019 esteso.</span><span class="sxs-lookup"><span data-stu-id="e2b92-123">This allows you to use .NET's extensive support for parsing various <xref:System.DateTime> and <xref:System.DateTimeOffset> text formats, including non-ISO 8601 strings and ISO 8601 formats that don't conform to the extended ISO 8601-1:2019 profile.</span></span> <span data-ttu-id="e2b92-124">Questo approccio è significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.</span><span class="sxs-lookup"><span data-stu-id="e2b92-124">This approach is significantly less performant than using the serializer's native implementation.</span></span>

<span data-ttu-id="e2b92-125">Per la serializzazione, è possibile usare `DateTime(Offset).ToString` il metodo nella logica di scrittura del convertitore.</span><span class="sxs-lookup"><span data-stu-id="e2b92-125">For serializing, you can use the `DateTime(Offset).ToString` method in your converter write logic.</span></span> <span data-ttu-id="e2b92-126">In questo modo è possibile <xref:System.DateTime> scrivere <xref:System.DateTimeOffset> valori e utilizzando uno dei [formati di data e ora standard](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)e i [formati di data e ora personalizzati](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="e2b92-126">This allows you to write <xref:System.DateTime> and <xref:System.DateTimeOffset> values using any of the [standard date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), and the [custom date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>
<span data-ttu-id="e2b92-127">Questo è anche significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.</span><span class="sxs-lookup"><span data-stu-id="e2b92-127">This is also significantly less performant than using the serializer's native implementation.</span></span>

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> <span data-ttu-id="e2b92-128">Quando si <xref:System.Text.Json.Serialization.JsonConverter%601>implementa e `T` è <xref:System.DateTime>, il `typeToConvert` parametro sarà sempre `typeof(DateTime)`.</span><span class="sxs-lookup"><span data-stu-id="e2b92-128">When implementing <xref:System.Text.Json.Serialization.JsonConverter%601>, and `T` is <xref:System.DateTime>, the `typeToConvert` parameter will always be `typeof(DateTime)`.</span></span>
<span data-ttu-id="e2b92-129">Il parametro è utile per gestire i casi polimorfici e quando si usano i generics `typeof(T)` per ottenere un modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e2b92-129">The parameter is useful for handling polymorphic cases and when using generics to get `typeof(T)` in a performant way.</span></span>

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a><span data-ttu-id="e2b92-130">Con <xref:System.Buffers.Text.Utf8Parser> e<xref:System.Buffers.Text.Utf8Formatter></span><span class="sxs-lookup"><span data-stu-id="e2b92-130">Using <xref:System.Buffers.Text.Utf8Parser> and <xref:System.Buffers.Text.Utf8Formatter></span></span>

<span data-ttu-id="e2b92-131">È possibile usare i metodi rapidi di analisi e formattazione basati su UTF-8 nella logica del convertitore se <xref:System.DateTime> le <xref:System.DateTimeOffset> rappresentazioni di input o testo sono conformi a una delle [stringhe di formato di data e ora standard](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)"R", "l", "o" o "G" oppure si vuole scrivere in base a uno di questi formati.</span><span class="sxs-lookup"><span data-stu-id="e2b92-131">You can use fast UTF-8-based parsing and formatting methods in your converter logic if your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations are compliant with one of the "R", "l", "O", or "G" [standard date and time format Strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), or you want to write according to one of these formats.</span></span> <span data-ttu-id="e2b92-132">Questa operazione è molto più veloce `DateTime(Offset).Parse` rispetto `DateTime(Offset).ToString`all'utilizzo di e.</span><span class="sxs-lookup"><span data-stu-id="e2b92-132">This is much faster than using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`.</span></span>

<span data-ttu-id="e2b92-133">Questo esempio mostra un convertitore personalizzato che serializza e <xref:System.DateTime> deserializza i valori in base al [formato standard "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span><span class="sxs-lookup"><span data-stu-id="e2b92-133">This example shows a custom converter that serializes and deserializes <xref:System.DateTime> values according to [the "R" standard format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span></span>

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> <span data-ttu-id="e2b92-134">Il formato standard "R" sarà sempre lungo 29 caratteri.</span><span class="sxs-lookup"><span data-stu-id="e2b92-134">The "R" standard format will always be 29 characters long.</span></span>

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a><span data-ttu-id="e2b92-135">Utilizzo `DateTime(Offset).Parse` di come fallback per l'analisi nativa del serializzatore</span><span class="sxs-lookup"><span data-stu-id="e2b92-135">Using `DateTime(Offset).Parse` as a fallback to the serializer's native parsing</span></span>

<span data-ttu-id="e2b92-136">Se in genere si prevede che <xref:System.DateTime> l' <xref:System.DateTimeOffset> input o i dati siano conformi al profilo ISO 8601-1:2019 esteso, è possibile usare la logica di analisi nativa del serializzatore.</span><span class="sxs-lookup"><span data-stu-id="e2b92-136">If you generally expect your input <xref:System.DateTime> or <xref:System.DateTimeOffset> data to conform to the extended ISO 8601-1:2019 profile, you can use the serializer's native parsing logic.</span></span> <span data-ttu-id="e2b92-137">È anche possibile implementare un meccanismo di fallback solo nel caso.</span><span class="sxs-lookup"><span data-stu-id="e2b92-137">You can also implement a fallback mechanism just in case.</span></span>
<span data-ttu-id="e2b92-138">Questo esempio mostra che, dopo aver eseguito l'analisi <xref:System.DateTime> di una rappresentazione <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>di testo usando, il convertitore analizza correttamente i <xref:System.DateTime.Parse(System.String)>dati usando.</span><span class="sxs-lookup"><span data-stu-id="e2b92-138">This example shows that, after failing to parse a <xref:System.DateTime> text representation using <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, the converter successfully parses the data using <xref:System.DateTime.Parse(System.String)>.</span></span>

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a><span data-ttu-id="e2b92-139">Profilo ISO 8601-1:2019 esteso in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e2b92-139">The extended ISO 8601-1:2019 profile in System.Text.Json</span></span>

### <a name="date-and-time-components"></a><span data-ttu-id="e2b92-140">Componenti di data e ora</span><span class="sxs-lookup"><span data-stu-id="e2b92-140">Date and time components</span></span>

<span data-ttu-id="e2b92-141">Il profilo ISO 8601-1:2019 esteso implementato in <xref:System.Text.Json> definisce i componenti seguenti per le rappresentazioni di data e ora.</span><span class="sxs-lookup"><span data-stu-id="e2b92-141">The extended ISO 8601-1:2019 profile implemented in <xref:System.Text.Json> defines the following components for date and time representations.</span></span> <span data-ttu-id="e2b92-142">Questi componenti vengono utilizzati per definire diversi livelli di granularità supportati durante l'analisi e la <xref:System.DateTime> formattazione <xref:System.DateTimeOffset> e le rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="e2b92-142">These components are used to define various levels of granularity supported when parsing and formatting <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span>

| <span data-ttu-id="e2b92-143">Componente</span><span class="sxs-lookup"><span data-stu-id="e2b92-143">Component</span></span>       | <span data-ttu-id="e2b92-144">Formato</span><span class="sxs-lookup"><span data-stu-id="e2b92-144">Format</span></span>                      | <span data-ttu-id="e2b92-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2b92-145">Description</span></span>                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="e2b92-146">Year</span><span class="sxs-lookup"><span data-stu-id="e2b92-146">Year</span></span>            | <span data-ttu-id="e2b92-147">"yyyy"</span><span class="sxs-lookup"><span data-stu-id="e2b92-147">"yyyy"</span></span>                      | <span data-ttu-id="e2b92-148">0001-9999</span><span class="sxs-lookup"><span data-stu-id="e2b92-148">0001-9999</span></span>                                                                       |
| <span data-ttu-id="e2b92-149">Mese</span><span class="sxs-lookup"><span data-stu-id="e2b92-149">Month</span></span>           | <span data-ttu-id="e2b92-150">"MM"</span><span class="sxs-lookup"><span data-stu-id="e2b92-150">"MM"</span></span>                        | <span data-ttu-id="e2b92-151">01-12</span><span class="sxs-lookup"><span data-stu-id="e2b92-151">01-12</span></span>                                                                           |
| <span data-ttu-id="e2b92-152">Giorno</span><span class="sxs-lookup"><span data-stu-id="e2b92-152">Day</span></span>             | <span data-ttu-id="e2b92-153">"dd"</span><span class="sxs-lookup"><span data-stu-id="e2b92-153">"dd"</span></span>                        | <span data-ttu-id="e2b92-154">01-28, 01-29, 01-30, 01-31 in base al mese/anno</span><span class="sxs-lookup"><span data-stu-id="e2b92-154">01-28, 01-29, 01-30, 01-31 based on month/year</span></span>                                  |
| <span data-ttu-id="e2b92-155">Ora</span><span class="sxs-lookup"><span data-stu-id="e2b92-155">Hour</span></span>            | <span data-ttu-id="e2b92-156">"HH"</span><span class="sxs-lookup"><span data-stu-id="e2b92-156">"HH"</span></span>                        | <span data-ttu-id="e2b92-157">00-23</span><span class="sxs-lookup"><span data-stu-id="e2b92-157">00-23</span></span>                                                                           |
| <span data-ttu-id="e2b92-158">Minuto</span><span class="sxs-lookup"><span data-stu-id="e2b92-158">Minute</span></span>          | <span data-ttu-id="e2b92-159">"mm"</span><span class="sxs-lookup"><span data-stu-id="e2b92-159">"mm"</span></span>                        | <span data-ttu-id="e2b92-160">00-59</span><span class="sxs-lookup"><span data-stu-id="e2b92-160">00-59</span></span>                                                                           |
| <span data-ttu-id="e2b92-161">Secondo</span><span class="sxs-lookup"><span data-stu-id="e2b92-161">Second</span></span>          | <span data-ttu-id="e2b92-162">"ss"</span><span class="sxs-lookup"><span data-stu-id="e2b92-162">"ss"</span></span>                        | <span data-ttu-id="e2b92-163">00-59</span><span class="sxs-lookup"><span data-stu-id="e2b92-163">00-59</span></span>                                                                           |
| <span data-ttu-id="e2b92-164">Seconda frazione</span><span class="sxs-lookup"><span data-stu-id="e2b92-164">Second fraction</span></span> | <span data-ttu-id="e2b92-165">"FFFFFFF"</span><span class="sxs-lookup"><span data-stu-id="e2b92-165">"FFFFFFF"</span></span>                   | <span data-ttu-id="e2b92-166">Minimo una cifra, un massimo di 16 cifre</span><span class="sxs-lookup"><span data-stu-id="e2b92-166">Minimum of one digit, maximum of 16 digits</span></span>                                      |
| <span data-ttu-id="e2b92-167">Offset tempo</span><span class="sxs-lookup"><span data-stu-id="e2b92-167">Time offset</span></span>     | <span data-ttu-id="e2b92-168">"K"</span><span class="sxs-lookup"><span data-stu-id="e2b92-168">"K"</span></span>                         | <span data-ttu-id="e2b92-169">"Z" o "(' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-169">Either "Z" or "('+'/'-')HH':'mm"</span></span>                                                |
| <span data-ttu-id="e2b92-170">Tempo parziale</span><span class="sxs-lookup"><span data-stu-id="e2b92-170">Partial time</span></span>    | <span data-ttu-id="e2b92-171">"HH":' mm ':' SS [FFFFFFF] "</span><span class="sxs-lookup"><span data-stu-id="e2b92-171">"HH':'mm':'ss[FFFFFFF]"</span></span>     | <span data-ttu-id="e2b92-172">Tempo senza informazioni di offset UTC</span><span class="sxs-lookup"><span data-stu-id="e2b92-172">Time without UTC offset information</span></span>                                             |
| <span data-ttu-id="e2b92-173">Data completa</span><span class="sxs-lookup"><span data-stu-id="e2b92-173">Full date</span></span>       | <span data-ttu-id="e2b92-174">"yyyy-'-dd"</span><span class="sxs-lookup"><span data-stu-id="e2b92-174">"yyyy'-'MM'-'dd"</span></span>            | <span data-ttu-id="e2b92-175">Data calendario</span><span class="sxs-lookup"><span data-stu-id="e2b92-175">Calendar date</span></span>                                                                   |
| <span data-ttu-id="e2b92-176">Ora completa</span><span class="sxs-lookup"><span data-stu-id="e2b92-176">Full time</span></span>       | <span data-ttu-id="e2b92-177">"Time'K parziale"</span><span class="sxs-lookup"><span data-stu-id="e2b92-177">"'Partial time'K"</span></span>           | <span data-ttu-id="e2b92-178">Ora UTC del giorno o ora locale del giorno con offset dell'ora tra l'ora locale e l'ora UTC</span><span class="sxs-lookup"><span data-stu-id="e2b92-178">UTC of day or Local time of day with the time offset between local time and UTC</span></span> |
| <span data-ttu-id="e2b92-179">Data/ora</span><span class="sxs-lookup"><span data-stu-id="e2b92-179">Date time</span></span>       | <span data-ttu-id="e2b92-180">"Ora completa '''''''</span><span class="sxs-lookup"><span data-stu-id="e2b92-180">"'Full date''T''Full time'"</span></span> | <span data-ttu-id="e2b92-181">Data e ora del calendario del giorno, ad esempio 2019-07-26T16:59:57-05:00</span><span class="sxs-lookup"><span data-stu-id="e2b92-181">Calendar date and time of day, e.g. 2019-07-26T16:59:57-05:00</span></span>                   |

### <a name="support-for-parsing"></a><span data-ttu-id="e2b92-182">Supporto per l'analisi</span><span class="sxs-lookup"><span data-stu-id="e2b92-182">Support for parsing</span></span>

<span data-ttu-id="e2b92-183">Per l'analisi vengono definiti i livelli di granularità seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2b92-183">The following levels of granularity are defined for parsing:</span></span>

1. <span data-ttu-id="e2b92-184">' Data completa '</span><span class="sxs-lookup"><span data-stu-id="e2b92-184">'Full date'</span></span>
    1. <span data-ttu-id="e2b92-185">"yyyy-'-dd"</span><span class="sxs-lookup"><span data-stu-id="e2b92-185">"yyyy'-'MM'-'dd"</span></span>

2. <span data-ttu-id="e2b92-186">"'' Data completa ' T'' ora '':'' minute '"</span><span class="sxs-lookup"><span data-stu-id="e2b92-186">"'Full date''T''Hour'':''Minute'"</span></span>
    1. <span data-ttu-id="e2b92-187">"yyyy-'-T'HH": "mm"</span><span class="sxs-lookup"><span data-stu-id="e2b92-187">"yyyy'-'MM'-'dd'T'HH':'mm"</span></span>

3. <span data-ttu-id="e2b92-188">"Ora parziale"'''''</span><span class="sxs-lookup"><span data-stu-id="e2b92-188">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="e2b92-189">"yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="e2b92-189">"yyyy'-'MM'-'dd'T'HH':'mm':'ss" ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>
    2. <span data-ttu-id="e2b92-190">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="e2b92-190">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

4. <span data-ttu-id="e2b92-191">"'' Data completa '' T'' ora '':'' minute '' offset dell'ora '"</span><span class="sxs-lookup"><span data-stu-id="e2b92-191">"'Full date''T''Time hour'':''Minute''Time offset'"</span></span>
    1. <span data-ttu-id="e2b92-192">"yyyy-'-T'HH": "mmZ"</span><span class="sxs-lookup"><span data-stu-id="e2b92-192">"yyyy'-'MM'-'dd'T'HH':'mmZ"</span></span>
    2. <span data-ttu-id="e2b92-193">"yyyy-'-T'HH ':' mm (' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-193">"yyyy'-'MM'-'dd'T'HH':'mm('+'/'-')HH':'mm"</span></span>

5. <span data-ttu-id="e2b92-194">' Data/ora '</span><span class="sxs-lookup"><span data-stu-id="e2b92-194">'Date time'</span></span>
    1. <span data-ttu-id="e2b92-195">"yyyy-'-T'HH ':' mm ':' ssZ '</span><span class="sxs-lookup"><span data-stu-id="e2b92-195">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>
    2. <span data-ttu-id="e2b92-196">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="e2b92-196">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>
    3. <span data-ttu-id="e2b92-197">"yyyy-'-T'HH ':' mm ':' SS (' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-197">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>
    4. <span data-ttu-id="e2b92-198">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF (' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-198">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

<span data-ttu-id="e2b92-199">Se sono presenti frazioni decimali per i secondi, deve essere presente almeno una cifra. `2019-07-26T00:00:00.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="e2b92-199">If there are decimal fractions for seconds, there must be at least one digit; `2019-07-26T00:00:00.` is not allowed.</span></span>
<span data-ttu-id="e2b92-200">Quando sono consentite fino a 16 cifre frazionarie, vengono analizzate solo le prime sette.</span><span class="sxs-lookup"><span data-stu-id="e2b92-200">While up to 16 fractional digits are allowed, only the first seven are parsed.</span></span> <span data-ttu-id="e2b92-201">Qualsiasi elemento oltre il quale è considerato uno zero.</span><span class="sxs-lookup"><span data-stu-id="e2b92-201">Anything beyond that is considered a zero.</span></span>
<span data-ttu-id="e2b92-202">Ad esempio, `2019-07-26T00:00:00.1234567890` verrà analizzato come se `2019-07-26T00:00:00.1234567`fosse.</span><span class="sxs-lookup"><span data-stu-id="e2b92-202">For example, `2019-07-26T00:00:00.1234567890` will be parsed as if it is `2019-07-26T00:00:00.1234567`.</span></span>
<span data-ttu-id="e2b92-203">In questo modo è possibile rimanere compatibili <xref:System.DateTime> con l'implementazione, che è limitata a questa risoluzione.</span><span class="sxs-lookup"><span data-stu-id="e2b92-203">This is to stay compatible with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>

<span data-ttu-id="e2b92-204">I secondi intercalari non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e2b92-204">Leap seconds are not supported.</span></span>

### <a name="support-for-formatting"></a><span data-ttu-id="e2b92-205">Supporto per la formattazione</span><span class="sxs-lookup"><span data-stu-id="e2b92-205">Support for formatting</span></span>

<span data-ttu-id="e2b92-206">Per la formattazione vengono definiti i livelli di granularità seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2b92-206">The following levels of granularity are defined for formatting:</span></span>

1. <span data-ttu-id="e2b92-207">"Ora parziale"'''''</span><span class="sxs-lookup"><span data-stu-id="e2b92-207">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="e2b92-208">"yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="e2b92-208">"yyyy'-'MM'-'dd'T'HH':'mm':'ss"  ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>

        <span data-ttu-id="e2b92-209">Usato per formattare un <xref:System.DateTime> oggetto senza secondi frazionari e senza informazioni di offset.</span><span class="sxs-lookup"><span data-stu-id="e2b92-209">Used to format a <xref:System.DateTime> without fractional seconds and without offset information.</span></span>

    2. <span data-ttu-id="e2b92-210">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="e2b92-210">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

        <span data-ttu-id="e2b92-211">Usato per formattare un <xref:System.DateTime> oggetto con i secondi frazionari ma senza informazioni di offset.</span><span class="sxs-lookup"><span data-stu-id="e2b92-211">Used to format a <xref:System.DateTime> with fractional seconds but without offset information.</span></span>

2. <span data-ttu-id="e2b92-212">' Data/ora '</span><span class="sxs-lookup"><span data-stu-id="e2b92-212">'Date time'</span></span>
    1. <span data-ttu-id="e2b92-213">"yyyy-'-T'HH ':' mm ':' ssZ '</span><span class="sxs-lookup"><span data-stu-id="e2b92-213">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>

        <span data-ttu-id="e2b92-214">Utilizzato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o senza secondi frazionari, ma con una differenza UTC.</span><span class="sxs-lookup"><span data-stu-id="e2b92-214">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a UTC offset.</span></span>

    2. <span data-ttu-id="e2b92-215">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFFZ"</span><span class="sxs-lookup"><span data-stu-id="e2b92-215">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>

        <span data-ttu-id="e2b92-216">Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o con i secondi frazionari e con una differenza UTC.</span><span class="sxs-lookup"><span data-stu-id="e2b92-216">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a UTC offset.</span></span>

    3. <span data-ttu-id="e2b92-217">"yyyy-'-T'HH ':' mm ':' SS (' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-217">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="e2b92-218">Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o senza secondi frazionari ma con un offset locale.</span><span class="sxs-lookup"><span data-stu-id="e2b92-218">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a local offset.</span></span>

    4. <span data-ttu-id="e2b92-219">"yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF (' +'/'-') HH ':' mm '</span><span class="sxs-lookup"><span data-stu-id="e2b92-219">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="e2b92-220">Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o con i secondi frazionari e con un offset locale.</span><span class="sxs-lookup"><span data-stu-id="e2b92-220">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a local offset.</span></span>
