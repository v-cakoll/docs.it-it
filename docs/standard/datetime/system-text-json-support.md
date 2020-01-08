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
ms.openlocfilehash: 8198359e2c54c4ed098703fbcc070f7469b3362a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344646"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Supporto di DateTime e DateTimeOffset in System.Text.Json

La libreria System. Text. JSON analizza e scrive <xref:System.DateTime> e <xref:System.DateTimeOffset> i valori in base al profilo esteso ISO 8601:-2019.
I [convertitori](xref:System.Text.Json.Serialization.JsonConverter%601) forniscono supporto personalizzato per la serializzazione e la deserializzazione con <xref:System.Text.Json.JsonSerializer>.
Il supporto personalizzato può essere implementato anche quando si usano <xref:System.Text.Json.Utf8JsonReader> e <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="support-for-the-iso-8601-12019-format"></a>Supporto per il formato ISO 8601-1:2019

I tipi <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>e <xref:System.Text.Json.JsonElement> analizzano e scrivono <xref:System.DateTime> e <xref:System.DateTimeOffset> le rappresentazioni di testo in base al profilo esteso del formato ISO 8601-1:2019; ad esempio, 2019-07-26T16:59:57-05:00.

i dati di <xref:System.DateTime> e di <xref:System.DateTimeOffset> possono essere serializzati con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

Possono anche essere deserializzati con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

Con le opzioni predefinite, le rappresentazioni di input <xref:System.DateTime> e di testo di <xref:System.DateTimeOffset> devono essere conformi al profilo ISO 8601-1:2019 esteso.
Se si tenta di deserializzare le rappresentazioni che non sono conformi al profilo, <xref:System.Text.Json.JsonSerializer> genererà una <xref:System.Text.Json.JsonException>:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

Il <xref:System.Text.Json.JsonDocument> fornisce accesso strutturato al contenuto di un payload JSON, incluse le rappresentazioni di <xref:System.DateTime> e <xref:System.DateTimeOffset>. Nell'esempio seguente viene illustrato come, quando viene fornita una raccolta di temperature, è possibile calcolare la temperatura media del lunedì:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

Se si tenta di calcolare la temperatura media fornita da un payload con rappresentazioni di <xref:System.DateTime> non conformi, <xref:System.Text.Json.JsonDocument> genererà una <xref:System.FormatException>:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

Il livello inferiore <xref:System.Text.Json.Utf8JsonWriter> scrive i dati <xref:System.DateTime> e <xref:System.DateTimeOffset>:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<xref:System.Text.Json.Utf8JsonReader> analizza i dati <xref:System.DateTime> e <xref:System.DateTimeOffset>:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

Il tentativo di leggere formati non conformi con <xref:System.Text.Json.Utf8JsonReader> causerà la generazione di una <xref:System.FormatException>:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a>Supporto personalizzato per <xref:System.DateTime> e <xref:System.DateTimeOffset>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a>Quando si usa <xref:System.Text.Json.JsonSerializer>

Se si desidera che il serializzatore esegua l'analisi o la formattazione personalizzata, è possibile implementare [convertitori personalizzati](xref:System.Text.Json.Serialization.JsonConverter%601).
Ecco alcuni esempi:

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Utilizzo di `DateTime(Offset).Parse` e `DateTime(Offset).ToString`

Se non è possibile determinare i formati delle rappresentazioni di input <xref:System.DateTime> o <xref:System.DateTimeOffset> testo, è possibile usare il metodo `DateTime(Offset).Parse` nella logica di lettura del convertitore. In questo modo è possibile utilizzare. Supporto completo di NET per l'analisi di diversi formati di testo <xref:System.DateTime> e <xref:System.DateTimeOffset>, incluse le stringhe non ISO 8601 e i formati ISO 8601 che non sono conformi al profilo ISO 8601-1:2019 esteso. Questo approccio è significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.

Per la serializzazione, è possibile usare il metodo `DateTime(Offset).ToString` nella logica di scrittura del convertitore. In questo modo è possibile scrivere <xref:System.DateTime> e <xref:System.DateTimeOffset> valori utilizzando uno dei [formati di data e ora standard](../base-types/standard-date-and-time-format-strings.md)e i [formati di data e ora personalizzati](../base-types/custom-date-and-time-format-strings.md).
Questo è anche significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Quando si implementa <xref:System.Text.Json.Serialization.JsonConverter%601>e `T` è <xref:System.DateTime>, il parametro `typeToConvert` sarà sempre `typeof(DateTime)`.
Il parametro è utile per gestire i casi polimorfici e quando si usano i generics per ottenere `typeof(T)` in modo efficiente.

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Utilizzo di <xref:System.Buffers.Text.Utf8Parser> e <xref:System.Buffers.Text.Utf8Formatter>

È possibile utilizzare metodi veloci di analisi e formattazione basati su UTF-8 nella logica del convertitore se le rappresentazioni di input <xref:System.DateTime> o <xref:System.DateTimeOffset> testo sono conformi a una delle [stringhe di formato di data e ora standard](../base-types/standard-date-and-time-format-strings.md)"R", "l", "o" o "G" oppure si desidera scrivere in base a uno di questi formati. Questa operazione è molto più rapida rispetto all'uso di `DateTime(Offset).Parse` e `DateTime(Offset).ToString`.

Questo esempio mostra un convertitore personalizzato che serializza e deserializza i valori <xref:System.DateTime> in base al [formato standard "R"](../base-types/standard-date-and-time-format-strings.md#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Il formato standard "R" sarà sempre lungo 29 caratteri.

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Utilizzo di `DateTime(Offset).Parse` come fallback per l'analisi nativa del serializzatore

Se in genere si prevede che l'input <xref:System.DateTime> o <xref:System.DateTimeOffset> i dati siano conformi al profilo ISO 8601-1:2019 esteso, è possibile usare la logica di analisi nativa del serializzatore. È anche possibile implementare un meccanismo di fallback solo nel caso.
Questo esempio mostra che, dopo aver eseguito l'analisi di una rappresentazione <xref:System.DateTime> testo utilizzando <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, il convertitore analizza correttamente i dati utilizzando <xref:System.DateTime.Parse(System.String)>.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a>Quando si scrive con <xref:System.Text.Json.Utf8JsonWriter>

Se si desidera scrivere una rappresentazione <xref:System.DateTime> personalizzata o <xref:System.DateTimeOffset> testo con <xref:System.Text.Json.Utf8JsonWriter>, è possibile formattare la rappresentazione personalizzata in un <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`o <xref:System.Text.Json.JsonEncodedText>, quindi passarla al metodo <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A?displayProperty=nameWithType> o <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A?displayProperty=nameWithType> corrispondente.

Nell'esempio seguente viene illustrato come è possibile creare un formato di <xref:System.DateTime> personalizzato con <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>, quindi scritto con il metodo <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)>:

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a>Durante la lettura con <xref:System.Text.Json.Utf8JsonReader>

Se si vuole leggere una rappresentazione <xref:System.DateTime> personalizzata o <xref:System.DateTimeOffset> testo con <xref:System.Text.Json.Utf8JsonReader>, è possibile ottenere il valore del token JSON corrente come <xref:System.String> usando <xref:System.Text.Json.Utf8JsonReader.GetString>, quindi analizzare il valore usando la logica personalizzata.

Nell'esempio seguente viene illustrato come è possibile recuperare una rappresentazione di testo <xref:System.DateTimeOffset> personalizzata utilizzando <xref:System.Text.Json.Utf8JsonReader.GetString>, quindi analizzata utilizzando <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>:

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Profilo ISO 8601-1:2019 esteso in System. Text. JSON

### <a name="date-and-time-components"></a>Componenti di data e ora

Il profilo ISO 8601-1:2019 esteso implementato in <xref:System.Text.Json> definisce i componenti seguenti per le rappresentazioni di data e ora. Questi componenti vengono utilizzati per definire diversi livelli di granularità supportati durante l'analisi e la formattazione di <xref:System.DateTime> e <xref:System.DateTimeOffset> rappresentazioni.

| Componente       | Formato                      | Descrizione                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Anno            | "yyyy"                      | 0001-9999                                                                       |
| Mese           | "MM"                        | 01-12                                                                           |
| Day             | "dd"                        | 01-28, 01-29, 01-30, 01-31 in base al mese/anno                                  |
| Hour            | "HH"                        | 00-23                                                                           |
| Minute          | "mm"                        | 00-59                                                                           |
| Second          | "ss"                        | 00-59                                                                           |
| Seconda frazione | "FFFFFFF"                   | Minimo una cifra, un massimo di 16 cifre                                      |
| Offset tempo     | "K"                         | "Z" o "(' +'/'-') HH ':' mm '                                                |
| Tempo parziale    | "HH":' mm ':' SS [FFFFFFF] "     | Tempo senza informazioni di offset UTC                                             |
| Data completa       | "yyyy-'-dd"            | Data calendario                                                                   |
| Ora completa       | "Time'K parziale"           | Ora UTC del giorno o ora locale del giorno con offset dell'ora tra l'ora locale e l'ora UTC |
| Data e ora       | "Ora completa ''''''' | Data e ora del calendario del giorno, ad esempio 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Supporto per l'analisi

Per l'analisi vengono definiti i livelli di granularità seguenti:

1. ' Data completa '
    1. "yyyy-'-dd"

2. "'' Data completa ' T'' ora '':'' minute '"
    1. "yyyy-'-T'HH": "mm"

3. "Ora parziale"'''''
    1. "yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))
    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF

4. "'' Data completa '' T'' ora '':'' minute '' offset dell'ora '"
    1. "yyyy-'-T'HH": "mmZ"
    2. "yyyy-'-T'HH ':' mm (' +'/'-') HH ':' mm '

5. ' Data/ora '
    1. "yyyy-'-T'HH ':' mm ':' ssZ '
    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFFZ"
    3. "yyyy-'-T'HH ':' mm ':' SS (' +'/'-') HH ':' mm '
    4. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF (' +'/'-') HH ':' mm '

Se sono presenti frazioni decimali per i secondi, deve essere presente almeno una cifra. `2019-07-26T00:00:00.` non è consentito.
Quando sono consentite fino a 16 cifre frazionarie, vengono analizzate solo le prime sette. Qualsiasi elemento oltre il quale è considerato uno zero.
Ad esempio, `2019-07-26T00:00:00.1234567890` verrà analizzato come se fosse `2019-07-26T00:00:00.1234567`.
In questo modo è possibile rimanere compatibili con l'implementazione di <xref:System.DateTime>, che è limitata a questa risoluzione.

I secondi intercalari non sono supportati.

### <a name="support-for-formatting"></a>Supporto per la formattazione

Per la formattazione vengono definiti i livelli di granularità seguenti:

1. "Ora parziale"'''''
    1. "yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](../base-types/standard-date-and-time-format-strings.md#the-sortable-s-format-specifier))

        Usato per formattare un <xref:System.DateTime> senza secondi frazionari e senza informazioni di offset.

    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF

        Usato per formattare un <xref:System.DateTime> con i secondi frazionari ma senza informazioni di offset.

2. ' Data/ora '
    1. "yyyy-'-T'HH ':' mm ':' ssZ '

        Utilizzato per formattare un <xref:System.DateTime> senza secondi frazionari ma con offset UTC.

    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFFZ"

        Utilizzato per formattare un <xref:System.DateTime> con i secondi frazionari e con una differenza UTC.

    3. "yyyy-'-T'HH ':' mm ':' SS (' +'/'-') HH ':' mm '

        Usato per formattare un <xref:System.DateTime> o <xref:System.DateTimeOffset> senza secondi frazionari ma con un offset locale.

    4. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF (' +'/'-') HH ':' mm '

        Usato per formattare un <xref:System.DateTime> o <xref:System.DateTimeOffset> con i secondi frazionari e con un offset locale.

Se presenti, vengono scritti al massimo 7 cifre frazionarie. Questa operazione è allineata all'implementazione di <xref:System.DateTime>, che è limitata a questa risoluzione.
