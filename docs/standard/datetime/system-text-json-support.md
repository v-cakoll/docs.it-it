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
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a>Supporto di DateTime e DateTimeOffset in System.Text.Json

La libreria System. Text. JSON analizza e scrive <xref:System.DateTime> i valori e <xref:System.DateTimeOffset> in base al profilo esteso ISO 8601:-2019.
I [convertitori](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0) forniscono supporto personalizzato per la serializzazione e la deserializzazione con <xref:System.Text.Json.JsonSerializer>.

## <a name="support-for-the-iso-8601-12019-format"></a>Supporto per il formato ISO 8601-1:2019

I <xref:System.Text.Json.JsonSerializer>tipi <xref:System.Text.Json.Utf8JsonReader>, ,<xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> e <xref:System.Text.Json.JsonElement> analizzano e scrivono<xref:System.DateTimeOffset> le rappresentazioni di testo in base al profilo esteso del formato ISO 8601-1:2019, ad esempio 2019-07-26T16 : 59:57-05:00.

<xref:System.DateTime>i <xref:System.DateTimeOffset> dati e possono essere serializzati <xref:System.Text.Json.JsonSerializer>con:

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/serializing-with-jsonserializer.cs)]

Possono anche essere deserializzati con <xref:System.Text.Json.JsonSerializer>:

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-valid.cs)]

Con le opzioni predefinite, <xref:System.DateTime> le <xref:System.DateTimeOffset> rappresentazioni di input e testo devono essere conformi al profilo ISO 8601-1:2019 esteso.
Il tentativo di deserializzare le rappresentazioni che non sono conformi <xref:System.Text.Json.JsonSerializer> al profilo causerà la generazione di un' <xref:System.Text.Json.JsonException>operazione:

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/deserializing-with-jsonserializer-error.cs)]

Fornisce accesso strutturato al contenuto di un payload JSON, incluse <xref:System.DateTime> le rappresentazioni e <xref:System.DateTimeOffset>. <xref:System.Text.Json.JsonDocument> Nell'esempio seguente viene illustrato come, quando viene fornita una raccolta di temperature, è possibile calcolare la temperatura media del lunedì:

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-valid.cs)]

Il tentativo di calcolare la temperatura media in base a un payload con rappresentazioni non <xref:System.DateTime> conformi <xref:System.Text.Json.JsonDocument> causerà la <xref:System.FormatException>generazione di un'operazione:

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/computing-with-jsondocument-error.cs)]

I dati e <xref:System.Text.Json.Utf8JsonWriter> le <xref:System.DateTime> scritture di <xref:System.DateTimeOffset> livello inferiore:

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/writing-with-utf8jsonwriter.cs)]

<xref:System.Text.Json.Utf8JsonReader><xref:System.DateTime> analizza e<xref:System.DateTimeOffset> dati:

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-valid.cs)]

Il tentativo di leggere formati non conformi con <xref:System.Text.Json.Utf8JsonReader> comporterà la generazione di <xref:System.FormatException>un'operazione:

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/reading-with-utf8jsonreader-error.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset-in-xrefsystemtextjsonjsonserializer"></a>Supporto personalizzato per <xref:System.DateTime> e <xref:System.DateTimeOffset> in<xref:System.Text.Json.JsonSerializer>

Se si desidera che il serializzatore esegua l'analisi o la formattazione personalizzata, è possibile implementare [convertitori personalizzati](https://docs.microsoft.com/dotnet/api/system.text.json.serialization.jsonconverter-1?view=netcore-3.0).
Ecco alcuni esempi:

### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a>Con `DateTime(Offset).Parse` e`DateTime(Offset).ToString`

Se non è possibile determinare i formati delle rappresentazioni <xref:System.DateTimeOffset> di input <xref:System.DateTime> o testo, è possibile `DateTime(Offset).Parse` usare il metodo nella logica di lettura del convertitore. In questo modo è possibile utilizzare. Supporto completo di NET per l'analisi di <xref:System.DateTime> vari <xref:System.DateTimeOffset> formati di testo, incluse le stringhe non ISO 8601 e i formati ISO 8601 che non sono conformi al profilo ISO 8601-1:2019 esteso. Questo approccio è significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.

Per la serializzazione, è possibile usare `DateTime(Offset).ToString` il metodo nella logica di scrittura del convertitore. In questo modo è possibile <xref:System.DateTime> scrivere <xref:System.DateTimeOffset> valori e utilizzando uno dei [formati di data e ora standard](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)e i [formati di data e ora personalizzati](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).
Questo è anche significativamente meno efficiente rispetto all'utilizzo dell'implementazione nativa del serializzatore.

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> Quando si <xref:System.Text.Json.Serialization.JsonConverter%601>implementa e `T` è <xref:System.DateTime>, il `typeToConvert` parametro sarà sempre `typeof(DateTime)`.
Il parametro è utile per gestire i casi polimorfici e quando si usano i generics `typeof(T)` per ottenere un modo efficiente.

### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a>Con <xref:System.Buffers.Text.Utf8Parser> e<xref:System.Buffers.Text.Utf8Formatter>

È possibile usare i metodi rapidi di analisi e formattazione basati su UTF-8 nella logica del convertitore se <xref:System.DateTime> le <xref:System.DateTimeOffset> rappresentazioni di input o testo sono conformi a una delle [stringhe di formato di data e ora standard](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)"R", "l", "o" o "G" oppure si vuole scrivere in base a uno di questi formati. Questa operazione è molto più veloce `DateTime(Offset).Parse` rispetto `DateTime(Offset).ToString`all'utilizzo di e.

Questo esempio mostra un convertitore personalizzato che serializza e <xref:System.DateTime> deserializza i valori in base al [formato standard "R"](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> Il formato standard "R" sarà sempre lungo 29 caratteri.

### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a>Utilizzo `DateTime(Offset).Parse` di come fallback per l'analisi nativa del serializzatore

Se in genere si prevede che <xref:System.DateTime> l' <xref:System.DateTimeOffset> input o i dati siano conformi al profilo ISO 8601-1:2019 esteso, è possibile usare la logica di analisi nativa del serializzatore. È anche possibile implementare un meccanismo di fallback solo nel caso.
Questo esempio mostra che, dopo aver eseguito l'analisi <xref:System.DateTime> di una rappresentazione <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>di testo usando, il convertitore analizza correttamente i <xref:System.DateTime.Parse(System.String)>dati usando.

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/datetime-converter-examples/example3/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a>Profilo ISO 8601-1:2019 esteso in System. Text. JSON

### <a name="date-and-time-components"></a>Componenti di data e ora

Il profilo ISO 8601-1:2019 esteso implementato in <xref:System.Text.Json> definisce i componenti seguenti per le rappresentazioni di data e ora. Questi componenti vengono utilizzati per definire diversi livelli di granularità supportati durante l'analisi e la <xref:System.DateTime> formattazione <xref:System.DateTimeOffset> e le rappresentazioni.

| Componente       | Formato                      | Descrizione                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| Year            | "yyyy"                      | 0001-9999                                                                       |
| Mese           | "MM"                        | 01-12                                                                           |
| Giorno             | "dd"                        | 01-28, 01-29, 01-30, 01-31 in base al mese/anno                                  |
| Ora            | "HH"                        | 00-23                                                                           |
| Minuto          | "mm"                        | 00-59                                                                           |
| Secondo          | "ss"                        | 00-59                                                                           |
| Seconda frazione | "FFFFFFF"                   | Minimo una cifra, un massimo di 16 cifre                                      |
| Offset tempo     | "K"                         | "Z" o "(' +'/'-') HH ':' mm '                                                |
| Tempo parziale    | "HH":' mm ':' SS [FFFFFFF] "     | Tempo senza informazioni di offset UTC                                             |
| Data completa       | "yyyy-'-dd"            | Data calendario                                                                   |
| Ora completa       | "Time'K parziale"           | Ora UTC del giorno o ora locale del giorno con offset dell'ora tra l'ora locale e l'ora UTC |
| Data/ora       | "Ora completa ''''''' | Data e ora del calendario del giorno, ad esempio 2019-07-26T16:59:57-05:00                   |

### <a name="support-for-parsing"></a>Supporto per l'analisi

Per l'analisi vengono definiti i livelli di granularità seguenti:

1. ' Data completa '
    1. "yyyy-'-dd"

2. "'' Data completa ' T'' ora '':'' minute '"
    1. "yyyy-'-T'HH": "mm"

3. "Ora parziale"'''''
    1. "yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))
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
Ad esempio, `2019-07-26T00:00:00.1234567890` verrà analizzato come se `2019-07-26T00:00:00.1234567`fosse.
In questo modo è possibile rimanere compatibili <xref:System.DateTime> con l'implementazione, che è limitata a questa risoluzione.

I secondi intercalari non sono supportati.

### <a name="support-for-formatting"></a>Supporto per la formattazione

Per la formattazione vengono definiti i livelli di granularità seguenti:

1. "Ora parziale"'''''
    1. "yyyy-'-T'HH ':' mm ':' SS" ([identificatore di formato ordinabile ("s")](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))

        Usato per formattare un <xref:System.DateTime> oggetto senza secondi frazionari e senza informazioni di offset.

    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF

        Usato per formattare un <xref:System.DateTime> oggetto con i secondi frazionari ma senza informazioni di offset.

2. ' Data/ora '
    1. "yyyy-'-T'HH ':' mm ':' ssZ '

        Utilizzato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o senza secondi frazionari, ma con una differenza UTC.

    2. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFFZ"

        Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o con i secondi frazionari e con una differenza UTC.

    3. "yyyy-'-T'HH ':' mm ':' SS (' +'/'-') HH ':' mm '

        Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o senza secondi frazionari ma con un offset locale.

    4. "yyyy-'-T'HH ':' mm ':' SS ' .' FFFFFFF (' +'/'-') HH ':' mm '

        Usato per formattare un <xref:System.DateTime> oggetto <xref:System.DateTimeOffset> o con i secondi frazionari e con un offset locale.
