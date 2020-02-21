---
title: Tipi di dati scalari protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di dati di base e noti supportati da protobuf e gRPC in .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543157"
---
# <a name="protobuf-scalar-data-types"></a>Tipi di dati scalari protobuf

Il buffer del protocollo (protobuf) supporta un intervallo di tipi di valore scalari nativi. La tabella seguente elenca tutti i tipi con il C# tipo equivalente:

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

Note:

1. La codifica standard per `int32` e `int64` è inefficiente quando si utilizzano valori firmati. Se è probabile che il campo contenga numeri negativi, usare invece `sint32` o `sint64`. Questi tipi vengono mappati C# rispettivamente ai tipi `int` e `long`.
2. I campi `fixed` utilizzano sempre lo stesso numero di byte indipendentemente dal valore. Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.
3. Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit). La lunghezza codificata non può essere maggiore di 2<sup>32</sup>.
4. Il runtime di protobuf fornisce un tipo di `ByteString` che esegue il mapping C# facilmente da e verso `byte[]` matrici.

## <a name="other-net-primitive-types"></a>Altri tipi primitivi .NET

### <a name="dates-and-times"></a>Date e ore

I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti a <xref:System.DateTimeOffset>, <xref:System.DateTime>e <xref:System.TimeSpan>. È possibile specificare questi tipi usando alcune estensioni "tipi noti" di Google. Queste estensioni forniscono il supporto per la generazione di codice e il runtime per i tipi di campo complessi nelle piattaforme supportate. 

La tabella seguente illustra i tipi di data e ora:

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

Le proprietà generate nella C# classe non sono i tipi di data e ora .NET. Le proprietà utilizzano le classi `Timestamp` e `Duration` nello spazio dei nomi `Google.Protobuf.WellKnownTypes`. Queste classi forniscono metodi per la conversione da e verso `DateTimeOffset`, `DateTime`e `TimeSpan`.

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
> Il tipo di `Timestamp` funziona con le ore UTC. i valori `DateTimeOffset` hanno sempre un offset pari a zero e la proprietà `DateTime.Kind` è sempre `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf non supporta direttamente il tipo <xref:System.Guid>, noto come `UUID` su altre piattaforme. Non esiste alcun tipo noto. 

L'approccio migliore consiste nel gestire i valori `Guid` come `string` campo, usando il formato esadecimale `8-4-4-4-12` standard, ad esempio `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`. Tutti i linguaggi e le piattaforme possono analizzare tale formato.

Non usare un campo `bytes` per `Guid` valori. I problemi con l'impostazione dell'ordine di *byte (* [definizione di Wikipedia](https://en.wikipedia.org/wiki/Endianness)) possono causare un comportamento anomalo quando protobuf interagisce con altre piattaforme, ad esempio Java.

### <a name="nullable-types"></a>Tipi nullable

La generazione di codice protobuf C# per utilizza i tipi nativi, ad esempio `int` per `int32`. Pertanto, i valori vengono sempre inclusi e non possono essere null. 

Per i valori che richiedono un valore null esplicito, ad esempio C# l'uso di `int?` nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# . Per usarli, importare `wrappers.proto` nel file di `.proto`, come indicato di seguito:

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

I tipi noti `Timestamp` e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable. Tuttavia è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.

## <a name="decimals"></a>Decimali

Protobuf non supporta in modo nativo il tipo di `decimal` .NET, ma solo `double` e `float`. Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo di `Decimal` standard ai tipi noti, con supporto della piattaforma per linguaggi e Framework che lo supportano. Non è stato ancora implementato alcun elemento.

È possibile creare una definizione di messaggio per rappresentare il tipo di `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET. Gli sviluppatori su altre piattaforme dovrebbero tuttavia comprendere il formato usato e implementare la propria gestione per l'it.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creazione di un tipo decimale personalizzato per protobuf

Una semplice implementazione potrebbe essere simile al tipo di `Money` non standard usato da alcune API Google, senza il campo `currency`.

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

Il campo `nanos` rappresenta i valori da `0.999_999_999` a `-0.999_999_999`. Ad esempio, il valore `decimal` `1.5m` verrebbe rappresentato come `{ units = 1, nanos = 500_000_000 }`. Questo è il motivo per cui nel campo `nanos` di questo esempio viene usato il tipo di `sfixed32`, che codifica in modo più efficiente rispetto al `int32` per valori più grandi. Se il campo `units` è negativo, anche il campo `nanos` dovrebbe essere negativo.

> [!NOTE]
> Sono disponibili più algoritmi per codificare `decimal` valori come stringhe di byte, ma questo messaggio è più facile da comprendere. I valori non sono interessati da un valore di endian su piattaforme diverse.

La conversione tra questo tipo e il tipo di `decimal` BCL potrebbe essere C# implementata in modo analogo al seguente:

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
> Quando si usano tipi di messaggio personalizzati come questo, è *necessario* documentarli con commenti in `.proto`. Gli altri sviluppatori possono quindi implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.

>[!div class="step-by-step"]
>[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)
