---
title: Tipi di dati scalari protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di dati di base e noti supportati da protobuf e gRPC in .NET Core.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 8c8db795e927a44e9f75ec828336630ec9978eb6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184267"
---
# <a name="protobuf-scalar-data-types"></a>Tipi di dati scalari protobuf

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Protobuf supporta un intervallo di tipi valore scalari nativi. La tabella seguente elenca tutti i tipi con il C# tipo equivalente:

| Tipo protobuf | Tipo C#      | Note |
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

## <a name="notes"></a>Note

1. La codifica standard per `int32` ed `int64` è inefficiente quando si utilizzano valori con segno. Se è probabile che il campo contenga numeri negativi, `sint32` usare `sint64` o. Entrambi i C# `int` tipi vengono mappati `long` rispettivamente ai tipi e.
2. I `fixed` campi utilizzano sempre lo stesso numero di byte indipendentemente dal valore. Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.
3. Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit) e la lunghezza codificata non può essere maggiore di 2<sup>32</sup>.
4. Il runtime di protobuf fornisce `ByteString` un tipo con mapping facile da C# `byte[]` e verso le matrici.

## <a name="other-net-primitive-types"></a>Altri tipi primitivi .NET

### <a name="dates-and-times"></a>Date e ore

I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti <xref:System.DateTime>a <xref:System.DateTimeOffset>, <xref:System.TimeSpan>e. Questi tipi possono essere specificati usando alcune estensioni "tipi noti" di Google, che forniscono supporto per la generazione di codice e il runtime per i tipi di campo più complessi nelle piattaforme supportate. La tabella seguente illustra i tipi di data e ora:

| Tipo C# | Tipo noto protobuf |
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

Le proprietà generate nella C# classe non sono i tipi di data e ora .NET. Le proprietà utilizzano le `Timestamp` classi `Duration` e nello `Google.Protobuf.WellKnownTypes` spazio dei nomi, `DateTimeOffset`che forniscono metodi per la conversione da e `DateTime`verso, `TimeSpan`e.

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
> Il `Timestamp` tipo funziona con le ore UTC; i valori hanno sempre un offset pari a zero e `DateTime.Kind` la proprietà sarà sempre `DateTimeKind.Utc`. `DateTimeOffset`

### <a name="systemguid"></a>System.Guid

Il <xref:System.Guid> tipo, noto come `UUID` su altre piattaforme, non è supportato direttamente da protobuf e non esiste alcun tipo noto. L'approccio migliore consiste nel gestire `Guid` i valori `string` come campo, usando il `8-4-4-4-12` formato esadecimale standard (ad `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`esempio,), che può essere analizzato da tutti i linguaggi e le piattaforme. Non usare un `bytes` campo per `Guid` i valori, in quanto i problemi con l'impostazione dell'oggetto endian possono causare un comportamento irregolare quando si interagisce con altre piattaforme, ad esempio Java.

### <a name="nullable-types"></a>Tipi nullable

La generazione di codice protobuf C# per utilizza i tipi nativi, ad `int` esempio `int32`per. Ciò significa che i valori vengono sempre inclusi e non possono essere null. Per i valori che richiedono un valore null esplicito `int?` , ad C# esempio l'uso del nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# . Per usarli, importare `wrappers.proto` `.proto` nel file, come indicato di seguito:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf utilizzerà la semplice `T?` (ad esempio, `int?`) per la proprietà del messaggio generata.

La tabella seguente mostra l'elenco completo dei tipi di wrapper con il C# tipo equivalente:

| Tipo C#   | Wrapper di tipo noto       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

I tipi `Timestamp` noti e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable, ma è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.

## <a name="decimals"></a>Decimali

Protobuf non supporta in modo nativo il `decimal` tipo .NET, `double` solo `float`e. Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo standard `Decimal` ai tipi noti, con supporto della piattaforma per linguaggi e Framework che lo supportano, ma non è ancora stato implementato alcun elemento.

È possibile creare una definizione di messaggio per rappresentare il tipo `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET, ma gli sviluppatori su altre piattaforme dovranno comprendere il formato usato e implementare i propri gestione per l'it.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creazione di un tipo decimale personalizzato per protobuf

Un'implementazione molto semplice potrebbe essere simile al tipo non standard `Money` usato da alcune API Google, senza il `currency` campo.

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

Il `nanos` campo rappresenta i valori `0.999_999_999` da `-0.999_999_999`a. `decimal` Il valore `sfixed32` `int32` `nanos` , ad esempio, viene rappresentato come `{ units = 1, nanos = 500_000_000 }` (questo è il motivo per cui il campo in questo esempio usa il tipo, che codifica in modo più efficiente rispetto a valori maggiori). `1.5m` Se il `units` campo è negativo, anche `nanos` il campo dovrebbe essere negativo.

> [!NOTE]
> Sono disponibili più algoritmi per la codifica `decimal` dei valori come stringhe di byte, ma questo messaggio è molto più facile da comprendere rispetto a uno di essi e i valori non sono *[interessati da l'](https://en.wikipedia.org/wiki/Endianness)* impostazione dell'oggetto per le diverse piattaforme.

La conversione tra questo tipo e il `decimal` tipo BCL può essere implementata in modo analogo al C# seguente.

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
> Ogni volta che si utilizzano tipi di messaggi di utilità personalizzati come questo, è **necessario** documentarli `.proto` con commenti in in modo che altri sviluppatori possano implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.

>[!div class="step-by-step"]
>[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)
