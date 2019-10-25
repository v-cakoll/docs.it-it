---
title: Tipi di dati scalari protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di dati di base e noti supportati da protobuf e gRPC in .NET Core.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: cae9cc483ffb791a9b53e6a2d9d7c0924d725a67
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846353"
---
# <a name="protobuf-scalar-data-types"></a>Tipi di dati scalari protobuf

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
| `string`      | `string`     | 3\.     |
| `bytes`       | `ByteString` | 4     |

## <a name="notes"></a>Note

1. La codifica standard per `int32` e `int64` è inefficiente quando si utilizzano valori con segno. Se è probabile che il campo contenga numeri negativi, usare invece `sint32` o `sint64`. Entrambi i C# tipi vengono mappati rispettivamente ai tipi`int`e`long`.
2. I campi `fixed` utilizzano sempre lo stesso numero di byte indipendentemente dal valore. Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.
3. Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit) e la lunghezza codificata non può essere maggiore di 2<sup>32</sup>.
4. Il runtime di protobuf fornisce un tipo di `ByteString` che esegue il mapping C# facilmente da e verso`byte[]`matrici.

## <a name="other-net-primitive-types"></a>Altri tipi primitivi .NET

### <a name="dates-and-times"></a>Date e ore

I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti a<xref:System.DateTimeOffset>,<xref:System.DateTime>e<xref:System.TimeSpan>. Questi tipi possono essere specificati usando alcune estensioni "tipi noti" di Google, che forniscono supporto per la generazione di codice e il runtime per i tipi di campo più complessi nelle piattaforme supportate. La tabella seguente illustra i tipi di data e ora:

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

Le proprietà generate nella C# classe non sono i tipi di data e ora .NET. Le proprietà utilizzano le classi `Timestamp` e `Duration` nello spazio dei nomi `Google.Protobuf.WellKnownTypes`, che forniscono metodi per la conversione da e verso `DateTimeOffset`, `DateTime`e `TimeSpan`.

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
> Il tipo di `Timestamp` funziona con le ore UTC; i valori `DateTimeOffset` hanno sempre un offset pari a zero e la proprietà `DateTime.Kind` sarà sempre `DateTimeKind.Utc`ta.

### <a name="systemguid"></a>System.Guid

Il tipo di <xref:System.Guid>, noto come `UUID` su altre piattaforme, non è supportato direttamente da protobuf e non esiste alcun tipo noto. L'approccio migliore consiste nel gestire `Guid` valori come `string` campo, usando il formato esadecimale `8-4-4-4-12` standard (ad esempio, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), che può essere analizzato da tutti i linguaggi e le piattaforme. Non usare un campo di `bytes` per i valori di `Guid`, in quanto i problemi con l'impostazione dell'oggetto di tipo possono comportare un comportamento irregolare quando si interagisce con altre piattaforme, ad esempio Java.

### <a name="nullable-types"></a>Tipi nullable

La generazione di codice protobuf C# per utilizza i tipi nativi, ad esempio`int`per`int32`. Ciò significa che i valori vengono sempre inclusi e non possono essere null. Per i valori che richiedono un valore null esplicito, ad esempio C# l'uso di `int?` nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# . Per usarli, importare `wrappers.proto` nel file di `.proto`, come indicato di seguito:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf utilizzerà la semplice `T?` (ad esempio `int?`) per la proprietà del messaggio generata.

La tabella seguente mostra l'elenco completo dei tipi di wrapper con il C# tipo equivalente:

| Tipo C#   | Wrapper di tipo noto       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

I tipi noti `Timestamp` e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable, ma è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.

## <a name="decimals"></a>decimali

Protobuf non supporta in modo nativo il tipo di `decimal` .NET, ma solo `double` e `float`. Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo di `Decimal` standard ai tipi noti, grazie al supporto della piattaforma per linguaggi e Framework che lo supportano, ma non è ancora stato implementato alcun elemento.

È possibile creare una definizione di messaggio per rappresentare il tipo di `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET, ma gli sviluppatori su altre piattaforme avrebbero dovuto comprendere il formato usato e implementare la propria gestione per questo.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creazione di un tipo decimale personalizzato per protobuf

Un'implementazione molto semplice potrebbe essere simile al tipo di `Money` non standard usato da alcune API Google, senza il campo `currency`.

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

Il campo `nanos` rappresenta i valori da `0.999_999_999` a `-0.999_999_999`. Ad esempio, il valore `decimal` `1.5m` verrebbe rappresentato come `{ units = 1, nanos = 500_000_000 }` (questo è il motivo per cui nel campo `nanos` in questo esempio viene usato il tipo di `sfixed32`, che codifica in modo più efficiente rispetto a `int32` per valori più grandi). Se il campo `units` è negativo, anche il campo `nanos` dovrebbe essere negativo.

> [!NOTE]
> Sono disponibili più algoritmi per la codifica di `decimal` valori come stringhe di byte, ma questo messaggio è molto più semplice da comprendere rispetto a uno di essi e i valori non sono *[interessati da l'](https://en.wikipedia.org/wiki/Endianness)* impostazione di un valore per le diverse piattaforme.

La conversione tra questo tipo e il tipo di `decimal` BCL potrebbe essere C# implementata in modo analogo al seguente.

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
> Ogni volta che si utilizzano tipi di messaggi di utilità personalizzati come questo, è **necessario** documentarli con commenti nel `.proto` in modo che altri sviluppatori possano implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.

>[!div class="step-by-step"]
>[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)
