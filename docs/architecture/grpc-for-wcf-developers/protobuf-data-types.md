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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="01a4e-103">Tipi di dati scalari protobuf</span><span class="sxs-lookup"><span data-stu-id="01a4e-103">Protobuf scalar data types</span></span>

<span data-ttu-id="01a4e-104">Protobuf supporta un intervallo di tipi valore scalari nativi.</span><span class="sxs-lookup"><span data-stu-id="01a4e-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="01a4e-105">La tabella seguente elenca tutti i tipi con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="01a4e-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="01a4e-106">Tipo protobuf</span><span class="sxs-lookup"><span data-stu-id="01a4e-106">Protobuf type</span></span> | <span data-ttu-id="01a4e-107">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="01a4e-107">C# type</span></span>      | <span data-ttu-id="01a4e-108">Note</span><span class="sxs-lookup"><span data-stu-id="01a4e-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="01a4e-109">1</span><span class="sxs-lookup"><span data-stu-id="01a4e-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="01a4e-110">1</span><span class="sxs-lookup"><span data-stu-id="01a4e-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="01a4e-111">1</span><span class="sxs-lookup"><span data-stu-id="01a4e-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="01a4e-112">1</span><span class="sxs-lookup"><span data-stu-id="01a4e-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="01a4e-113">2</span><span class="sxs-lookup"><span data-stu-id="01a4e-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="01a4e-114">2</span><span class="sxs-lookup"><span data-stu-id="01a4e-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="01a4e-115">2</span><span class="sxs-lookup"><span data-stu-id="01a4e-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="01a4e-116">2</span><span class="sxs-lookup"><span data-stu-id="01a4e-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="01a4e-117">3\.</span><span class="sxs-lookup"><span data-stu-id="01a4e-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="01a4e-118">4</span><span class="sxs-lookup"><span data-stu-id="01a4e-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="01a4e-119">Note</span><span class="sxs-lookup"><span data-stu-id="01a4e-119">Notes</span></span>

1. <span data-ttu-id="01a4e-120">La codifica standard per `int32` e `int64` è inefficiente quando si utilizzano valori con segno.</span><span class="sxs-lookup"><span data-stu-id="01a4e-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="01a4e-121">Se è probabile che il campo contenga numeri negativi, usare invece `sint32` o `sint64`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="01a4e-122">Entrambi i C# tipi vengono mappati rispettivamente ai tipi`int`e`long`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="01a4e-123">I campi `fixed` utilizzano sempre lo stesso numero di byte indipendentemente dal valore.</span><span class="sxs-lookup"><span data-stu-id="01a4e-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="01a4e-124">Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="01a4e-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="01a4e-125">Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit) e la lunghezza codificata non può essere maggiore di 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="01a4e-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="01a4e-126">Il runtime di protobuf fornisce un tipo di `ByteString` che esegue il mapping C# facilmente da e verso`byte[]`matrici.</span><span class="sxs-lookup"><span data-stu-id="01a4e-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="01a4e-127">Altri tipi primitivi .NET</span><span class="sxs-lookup"><span data-stu-id="01a4e-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="01a4e-128">Date e ore</span><span class="sxs-lookup"><span data-stu-id="01a4e-128">Dates and times</span></span>

<span data-ttu-id="01a4e-129">I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti a<xref:System.DateTimeOffset>,<xref:System.DateTime>e<xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="01a4e-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="01a4e-130">Questi tipi possono essere specificati usando alcune estensioni "tipi noti" di Google, che forniscono supporto per la generazione di codice e il runtime per i tipi di campo più complessi nelle piattaforme supportate.</span><span class="sxs-lookup"><span data-stu-id="01a4e-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="01a4e-131">La tabella seguente illustra i tipi di data e ora:</span><span class="sxs-lookup"><span data-stu-id="01a4e-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="01a4e-132">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="01a4e-132">C# type</span></span> | <span data-ttu-id="01a4e-133">Tipo noto protobuf</span><span class="sxs-lookup"><span data-stu-id="01a4e-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="01a4e-134">Le proprietà generate nella C# classe non sono i tipi di data e ora .NET.</span><span class="sxs-lookup"><span data-stu-id="01a4e-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="01a4e-135">Le proprietà utilizzano le classi `Timestamp` e `Duration` nello spazio dei nomi `Google.Protobuf.WellKnownTypes`, che forniscono metodi per la conversione da e verso `DateTimeOffset`, `DateTime`e `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="01a4e-136">Il tipo di `Timestamp` funziona con le ore UTC; i valori `DateTimeOffset` hanno sempre un offset pari a zero e la proprietà `DateTime.Kind` sarà sempre `DateTimeKind.Utc`ta.</span><span class="sxs-lookup"><span data-stu-id="01a4e-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="01a4e-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="01a4e-137">System.Guid</span></span>

<span data-ttu-id="01a4e-138">Il tipo di <xref:System.Guid>, noto come `UUID` su altre piattaforme, non è supportato direttamente da protobuf e non esiste alcun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="01a4e-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="01a4e-139">L'approccio migliore consiste nel gestire `Guid` valori come `string` campo, usando il formato esadecimale `8-4-4-4-12` standard (ad esempio, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), che può essere analizzato da tutti i linguaggi e le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="01a4e-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="01a4e-140">Non usare un campo di `bytes` per i valori di `Guid`, in quanto i problemi con l'impostazione dell'oggetto di tipo possono comportare un comportamento irregolare quando si interagisce con altre piattaforme, ad esempio Java.</span><span class="sxs-lookup"><span data-stu-id="01a4e-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="01a4e-141">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="01a4e-141">Nullable types</span></span>

<span data-ttu-id="01a4e-142">La generazione di codice protobuf C# per utilizza i tipi nativi, ad esempio`int`per`int32`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="01a4e-143">Ciò significa che i valori vengono sempre inclusi e non possono essere null.</span><span class="sxs-lookup"><span data-stu-id="01a4e-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="01a4e-144">Per i valori che richiedono un valore null esplicito, ad esempio C# l'uso di `int?` nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# .</span><span class="sxs-lookup"><span data-stu-id="01a4e-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="01a4e-145">Per usarli, importare `wrappers.proto` nel file di `.proto`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="01a4e-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="01a4e-146">Protobuf utilizzerà la semplice `T?` (ad esempio `int?`) per la proprietà del messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="01a4e-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="01a4e-147">La tabella seguente mostra l'elenco completo dei tipi di wrapper con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="01a4e-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="01a4e-148">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="01a4e-148">C# type</span></span>   | <span data-ttu-id="01a4e-149">Wrapper di tipo noto</span><span class="sxs-lookup"><span data-stu-id="01a4e-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="01a4e-150">I tipi noti `Timestamp` e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable, ma è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="01a4e-151">decimali</span><span class="sxs-lookup"><span data-stu-id="01a4e-151">Decimals</span></span>

<span data-ttu-id="01a4e-152">Protobuf non supporta in modo nativo il tipo di `decimal` .NET, ma solo `double` e `float`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="01a4e-153">Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo di `Decimal` standard ai tipi noti, grazie al supporto della piattaforma per linguaggi e Framework che lo supportano, ma non è ancora stato implementato alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="01a4e-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="01a4e-154">È possibile creare una definizione di messaggio per rappresentare il tipo di `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET, ma gli sviluppatori su altre piattaforme avrebbero dovuto comprendere il formato usato e implementare la propria gestione per questo.</span><span class="sxs-lookup"><span data-stu-id="01a4e-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="01a4e-155">Creazione di un tipo decimale personalizzato per protobuf</span><span class="sxs-lookup"><span data-stu-id="01a4e-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="01a4e-156">Un'implementazione molto semplice potrebbe essere simile al tipo di `Money` non standard usato da alcune API Google, senza il campo `currency`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="01a4e-157">Il campo `nanos` rappresenta i valori da `0.999_999_999` a `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="01a4e-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="01a4e-158">Ad esempio, il valore `decimal` `1.5m` verrebbe rappresentato come `{ units = 1, nanos = 500_000_000 }` (questo è il motivo per cui nel campo `nanos` in questo esempio viene usato il tipo di `sfixed32`, che codifica in modo più efficiente rispetto a `int32` per valori più grandi).</span><span class="sxs-lookup"><span data-stu-id="01a4e-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="01a4e-159">Se il campo `units` è negativo, anche il campo `nanos` dovrebbe essere negativo.</span><span class="sxs-lookup"><span data-stu-id="01a4e-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="01a4e-160">Sono disponibili più algoritmi per la codifica di `decimal` valori come stringhe di byte, ma questo messaggio è molto più semplice da comprendere rispetto a uno di essi e i valori non sono *[interessati da l'](https://en.wikipedia.org/wiki/Endianness)* impostazione di un valore per le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="01a4e-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="01a4e-161">La conversione tra questo tipo e il tipo di `decimal` BCL potrebbe essere C# implementata in modo analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="01a4e-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="01a4e-162">Ogni volta che si utilizzano tipi di messaggi di utilità personalizzati come questo, è **necessario** documentarli con commenti nel `.proto` in modo che altri sviluppatori possano implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.</span><span class="sxs-lookup"><span data-stu-id="01a4e-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="01a4e-163">[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="01a4e-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
