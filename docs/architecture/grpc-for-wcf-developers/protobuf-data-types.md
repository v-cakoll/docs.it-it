---
title: Tipi di dati scalari Protobuf - gRPC per gli sviluppatori WCFProtobuf scalar data types - gRPC for WCF developers
description: Informazioni sui tipi di dati di base e noti supportati da Protobuf e gRPC in .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: a40f51fa32ddb97ba417ec01f31e1f0187f0d544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148127"
---
# <a name="protobuf-scalar-data-types"></a>Tipi di dati scalari protobuf

Protocol Buffer (Protobuf) supporta un intervallo di tipi di valore scalare nativi. Nella tabella seguente sono elencati tutti con il tipo equivalente di C':

| Tipo di protobuf | Tipo C#      | Note |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

Note:

1. La codifica `int32` standard `int64` per e è inefficiente quando si lavora con valori firmati. Se è probabile che il campo `sint32` `sint64` contenga numeri negativi, utilizzare o invece. Questi tipi eseguono `int` il `long` mapping al linguaggio C e ai tipi, rispettivamente.
2. I `fixed` campi utilizzano sempre lo stesso numero di byte, indipendentemente dal valore. Questo comportamento rende la serializzazione e deserializzazione più veloce per valori più grandi.
3. Le stringhe protobuf sono codificate in UTF-8 (o ASCII a 7 bit). La lunghezza codificata non può essere maggiore di 2<sup>32</sup>.
4. Il runtime di Protobuf fornisce un `ByteString` tipo `byte[]` che esegue il mapping facilmente a e da matrici C .

## <a name="other-net-primitive-types"></a>Altri tipi primitivi .NET

### <a name="dates-and-times"></a>Date e ore

I tipi scalari nativi non forniscono valori di data e <xref:System.DateTimeOffset> <xref:System.DateTime>ora, <xref:System.TimeSpan>equivalenti a quelli di C, , e . Puoi specificare questi tipi utilizzando alcune delle estensioni "Tipi noti" di Google. Queste estensioni forniscono la generazione di codice e il supporto runtime per i tipi di campo complessi nelle piattaforme supportate.

Nella tabella seguente vengono illustrati i tipi di data e ora:

| Tipo C# | Protobuf tipo ben noto |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

Le proprietà generate nella classe C , non sono i tipi di data e ora .NET. Le proprietà `Timestamp` utilizzano le classi e `Duration` nello `Google.Protobuf.WellKnownTypes` spazio dei nomi . Queste classi forniscono metodi per `DateTimeOffset` `DateTime`la `TimeSpan`conversione in e da , e .

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> Il `Timestamp` tipo funziona con l'ora UTC. `DateTimeOffset`i valori hanno sempre un `DateTime.Kind` offset pari `DateTimeKind.Utc`a zero e la proprietà è sempre .

### <a name="systemguid"></a>System.Guid

Protobuf non supporta direttamente <xref:System.Guid> il tipo, noto come `UUID` su altre piattaforme. Non c'è un tipo ben noto per questo.

L'approccio migliore `Guid` consiste `string` nel gestire i `8-4-4-4-12` valori come campo, utilizzando `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`il formato esadecimale standard (ad esempio, ). Tutte le lingue e le piattaforme possono analizzare tale formato.

Non usare un `bytes` campo `Guid` per i valori. Problemi di *endianness* ([definizione](https://en.wikipedia.org/wiki/Endianness)di Wikipedia ) possono causare un comportamento irregolare quando Protobuf interagisce con altre piattaforme, come Java.

### <a name="nullable-types"></a>Tipi nullable

La generazione di codice Protobuf per il `int` linguaggio C, utilizza i tipi nativi, ad esempio per `int32`. Quindi i valori sono sempre inclusi e non possono essere null.

Per i valori che richiedono `int?` valori null espliciti, ad esempio l'utilizzo nel codice C, i "Tipi noti" di Protobuf includono wrapper che vengono compilati in tipi C . Per usarli, `wrappers.proto` importa `.proto` nel tuo file, in questo modo:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf utilizzerà `T?` il semplice `int?`(ad esempio, ) per la proprietà del messaggio generato.

Nella tabella seguente viene illustrato l'elenco completo dei tipi di wrapper con il tipo equivalente in C:

| Tipo C#   | Wrapper del tipo noto       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

I tipi `Timestamp` noti `Duration` e sono rappresentati in .NET come classi, pertanto non è necessario una versione nullable. Ma è importante verificare la presenza di valori null sulle `DateTimeOffset` proprietà `TimeSpan`di tali tipi durante la conversione in o .

## <a name="decimals"></a>Decimali

Protobuf non supporta in modo `decimal` nativo il `double` `float`tipo .NET, just e . C'è una discussione in corso nel progetto Protobuf sulla possibilità di aggiungere un tipo standard `Decimal` per i tipi noti, con il supporto della piattaforma per i linguaggi e framework che lo supportano. Nulla è stato ancora implementato.

È possibile creare una definizione di `decimal` messaggio per rappresentare il tipo che funzionerebbe per la serializzazione sicura tra client e server .NET. Ma gli sviluppatori su altre piattaforme dovrebbero comprendere il formato utilizzato e implementare la propria gestione per esso.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creazione di un tipo decimale personalizzato per Protobuf

Un'implementazione semplice potrebbe essere `Money` simile al tipo non standard `currency` utilizzato da alcune API Google, senza il campo.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

Il `nanos` campo rappresenta `0.999_999_999` `-0.999_999_999`i valori da a . Ad esempio, `decimal` `1.5m` il valore `{ units = 1, nanos = 500_000_000 }`verrebbe rappresentato come . Questo è `nanos` il motivo per `sfixed32` cui il campo in `int32` questo esempio utilizza il tipo, che codifica in modo più efficiente rispetto ai valori più grandi. Se `units` il campo è `nanos` negativo, anche il campo deve essere negativo.

> [!NOTE]
> Esistono più altri algoritmi `decimal` per la codifica dei valori come stringhe di byte, ma questo messaggio è più facile da comprendere rispetto a qualsiasi di essi. I valori non sono influenzati dall'endianness su piattaforme diverse.

La conversione tra questo `decimal` tipo e il tipo BCL potrebbe essere implementata in C , in questo modo:

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> Ogni volta che si utilizzano *must* tipi di messaggio `.proto`personalizzati come questo, è necessario documentarli con commenti in . Altri sviluppatori possono quindi implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o framework.

>[!div class="step-by-step"]
>[Successivo](protobuf-messages.md)
>[precedente](protobuf-nested-types.md)
