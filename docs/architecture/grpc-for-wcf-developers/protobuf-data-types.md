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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="c2b28-103">Tipi di dati scalari protobuf</span><span class="sxs-lookup"><span data-stu-id="c2b28-103">Protobuf scalar data types</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c2b28-104">Protobuf supporta un intervallo di tipi valore scalari nativi.</span><span class="sxs-lookup"><span data-stu-id="c2b28-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="c2b28-105">La tabella seguente elenca tutti i tipi con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2b28-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="c2b28-106">Tipo protobuf</span><span class="sxs-lookup"><span data-stu-id="c2b28-106">Protobuf type</span></span> | <span data-ttu-id="c2b28-107">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="c2b28-107">C# type</span></span>      | <span data-ttu-id="c2b28-108">Note</span><span class="sxs-lookup"><span data-stu-id="c2b28-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="c2b28-109">1</span><span class="sxs-lookup"><span data-stu-id="c2b28-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="c2b28-110">1</span><span class="sxs-lookup"><span data-stu-id="c2b28-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="c2b28-111">1</span><span class="sxs-lookup"><span data-stu-id="c2b28-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="c2b28-112">1</span><span class="sxs-lookup"><span data-stu-id="c2b28-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="c2b28-113">2</span><span class="sxs-lookup"><span data-stu-id="c2b28-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="c2b28-114">2</span><span class="sxs-lookup"><span data-stu-id="c2b28-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="c2b28-115">2</span><span class="sxs-lookup"><span data-stu-id="c2b28-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="c2b28-116">2</span><span class="sxs-lookup"><span data-stu-id="c2b28-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="c2b28-117">3</span><span class="sxs-lookup"><span data-stu-id="c2b28-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="c2b28-118">4</span><span class="sxs-lookup"><span data-stu-id="c2b28-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="c2b28-119">Note</span><span class="sxs-lookup"><span data-stu-id="c2b28-119">Notes</span></span>

1. <span data-ttu-id="c2b28-120">La codifica standard per `int32` ed `int64` è inefficiente quando si utilizzano valori con segno.</span><span class="sxs-lookup"><span data-stu-id="c2b28-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="c2b28-121">Se è probabile che il campo contenga numeri negativi, `sint32` usare `sint64` o.</span><span class="sxs-lookup"><span data-stu-id="c2b28-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="c2b28-122">Entrambi i C# `int` tipi vengono mappati `long` rispettivamente ai tipi e.</span><span class="sxs-lookup"><span data-stu-id="c2b28-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="c2b28-123">I `fixed` campi utilizzano sempre lo stesso numero di byte indipendentemente dal valore.</span><span class="sxs-lookup"><span data-stu-id="c2b28-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="c2b28-124">Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="c2b28-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="c2b28-125">Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit) e la lunghezza codificata non può essere maggiore di 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="c2b28-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="c2b28-126">Il runtime di protobuf fornisce `ByteString` un tipo con mapping facile da C# `byte[]` e verso le matrici.</span><span class="sxs-lookup"><span data-stu-id="c2b28-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="c2b28-127">Altri tipi primitivi .NET</span><span class="sxs-lookup"><span data-stu-id="c2b28-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="c2b28-128">Date e ore</span><span class="sxs-lookup"><span data-stu-id="c2b28-128">Dates and times</span></span>

<span data-ttu-id="c2b28-129">I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti <xref:System.DateTime>a <xref:System.DateTimeOffset>, <xref:System.TimeSpan>e.</span><span class="sxs-lookup"><span data-stu-id="c2b28-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="c2b28-130">Questi tipi possono essere specificati usando alcune estensioni "tipi noti" di Google, che forniscono supporto per la generazione di codice e il runtime per i tipi di campo più complessi nelle piattaforme supportate.</span><span class="sxs-lookup"><span data-stu-id="c2b28-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="c2b28-131">La tabella seguente illustra i tipi di data e ora:</span><span class="sxs-lookup"><span data-stu-id="c2b28-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="c2b28-132">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="c2b28-132">C# type</span></span> | <span data-ttu-id="c2b28-133">Tipo noto protobuf</span><span class="sxs-lookup"><span data-stu-id="c2b28-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="c2b28-134">Le proprietà generate nella C# classe non sono i tipi di data e ora .NET.</span><span class="sxs-lookup"><span data-stu-id="c2b28-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="c2b28-135">Le proprietà utilizzano le `Timestamp` classi `Duration` e nello `Google.Protobuf.WellKnownTypes` spazio dei nomi, `DateTimeOffset`che forniscono metodi per la conversione da e `DateTime`verso, `TimeSpan`e.</span><span class="sxs-lookup"><span data-stu-id="c2b28-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="c2b28-136">Il `Timestamp` tipo funziona con le ore UTC; i valori hanno sempre un offset pari a zero e `DateTime.Kind` la proprietà sarà sempre `DateTimeKind.Utc`. `DateTimeOffset`</span><span class="sxs-lookup"><span data-stu-id="c2b28-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="c2b28-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="c2b28-137">System.Guid</span></span>

<span data-ttu-id="c2b28-138">Il <xref:System.Guid> tipo, noto come `UUID` su altre piattaforme, non è supportato direttamente da protobuf e non esiste alcun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="c2b28-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="c2b28-139">L'approccio migliore consiste nel gestire `Guid` i valori `string` come campo, usando il `8-4-4-4-12` formato esadecimale standard (ad `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`esempio,), che può essere analizzato da tutti i linguaggi e le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="c2b28-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="c2b28-140">Non usare un `bytes` campo per `Guid` i valori, in quanto i problemi con l'impostazione dell'oggetto endian possono causare un comportamento irregolare quando si interagisce con altre piattaforme, ad esempio Java.</span><span class="sxs-lookup"><span data-stu-id="c2b28-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="c2b28-141">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="c2b28-141">Nullable types</span></span>

<span data-ttu-id="c2b28-142">La generazione di codice protobuf C# per utilizza i tipi nativi, ad `int` esempio `int32`per.</span><span class="sxs-lookup"><span data-stu-id="c2b28-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="c2b28-143">Ciò significa che i valori vengono sempre inclusi e non possono essere null.</span><span class="sxs-lookup"><span data-stu-id="c2b28-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="c2b28-144">Per i valori che richiedono un valore null esplicito `int?` , ad C# esempio l'uso del nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# .</span><span class="sxs-lookup"><span data-stu-id="c2b28-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="c2b28-145">Per usarli, importare `wrappers.proto` `.proto` nel file, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c2b28-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="c2b28-146">Protobuf utilizzerà la semplice `T?` (ad esempio, `int?`) per la proprietà del messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="c2b28-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="c2b28-147">La tabella seguente mostra l'elenco completo dei tipi di wrapper con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="c2b28-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="c2b28-148">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="c2b28-148">C# type</span></span>   | <span data-ttu-id="c2b28-149">Wrapper di tipo noto</span><span class="sxs-lookup"><span data-stu-id="c2b28-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="c2b28-150">I tipi `Timestamp` noti e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable, ma è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="c2b28-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="c2b28-151">Decimali</span><span class="sxs-lookup"><span data-stu-id="c2b28-151">Decimals</span></span>

<span data-ttu-id="c2b28-152">Protobuf non supporta in modo nativo il `decimal` tipo .NET, `double` solo `float`e.</span><span class="sxs-lookup"><span data-stu-id="c2b28-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="c2b28-153">Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo standard `Decimal` ai tipi noti, con supporto della piattaforma per linguaggi e Framework che lo supportano, ma non è ancora stato implementato alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="c2b28-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="c2b28-154">È possibile creare una definizione di messaggio per rappresentare il tipo `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET, ma gli sviluppatori su altre piattaforme dovranno comprendere il formato usato e implementare i propri gestione per l'it.</span><span class="sxs-lookup"><span data-stu-id="c2b28-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="c2b28-155">Creazione di un tipo decimale personalizzato per protobuf</span><span class="sxs-lookup"><span data-stu-id="c2b28-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="c2b28-156">Un'implementazione molto semplice potrebbe essere simile al tipo non standard `Money` usato da alcune API Google, senza il `currency` campo.</span><span class="sxs-lookup"><span data-stu-id="c2b28-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="c2b28-157">Il `nanos` campo rappresenta i valori `0.999_999_999` da `-0.999_999_999`a.</span><span class="sxs-lookup"><span data-stu-id="c2b28-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="c2b28-158">`decimal` Il valore `sfixed32` `int32` `nanos` , ad esempio, viene rappresentato come `{ units = 1, nanos = 500_000_000 }` (questo è il motivo per cui il campo in questo esempio usa il tipo, che codifica in modo più efficiente rispetto a valori maggiori). `1.5m`</span><span class="sxs-lookup"><span data-stu-id="c2b28-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="c2b28-159">Se il `units` campo è negativo, anche `nanos` il campo dovrebbe essere negativo.</span><span class="sxs-lookup"><span data-stu-id="c2b28-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="c2b28-160">Sono disponibili più algoritmi per la codifica `decimal` dei valori come stringhe di byte, ma questo messaggio è molto più facile da comprendere rispetto a uno di essi e i valori non sono *[interessati da l'](https://en.wikipedia.org/wiki/Endianness)* impostazione dell'oggetto per le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="c2b28-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="c2b28-161">La conversione tra questo tipo e il `decimal` tipo BCL può essere implementata in modo analogo al C# seguente.</span><span class="sxs-lookup"><span data-stu-id="c2b28-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="c2b28-162">Ogni volta che si utilizzano tipi di messaggi di utilità personalizzati come questo, è **necessario** documentarli `.proto` con commenti in in modo che altri sviluppatori possano implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.</span><span class="sxs-lookup"><span data-stu-id="c2b28-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c2b28-163">[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="c2b28-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
