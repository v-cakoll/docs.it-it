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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="dc4d9-103">Tipi di dati scalari protobuf</span><span class="sxs-lookup"><span data-stu-id="dc4d9-103">Protobuf scalar data types</span></span>

<span data-ttu-id="dc4d9-104">Il buffer del protocollo (protobuf) supporta un intervallo di tipi di valore scalari nativi.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="dc4d9-105">La tabella seguente elenca tutti i tipi con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="dc4d9-106">Tipo protobuf</span><span class="sxs-lookup"><span data-stu-id="dc4d9-106">Protobuf type</span></span> | <span data-ttu-id="dc4d9-107">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="dc4d9-107">C# type</span></span>      | <span data-ttu-id="dc4d9-108">Note</span><span class="sxs-lookup"><span data-stu-id="dc4d9-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="dc4d9-109">1</span><span class="sxs-lookup"><span data-stu-id="dc4d9-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="dc4d9-110">1</span><span class="sxs-lookup"><span data-stu-id="dc4d9-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="dc4d9-111">1</span><span class="sxs-lookup"><span data-stu-id="dc4d9-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="dc4d9-112">1</span><span class="sxs-lookup"><span data-stu-id="dc4d9-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="dc4d9-113">2</span><span class="sxs-lookup"><span data-stu-id="dc4d9-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="dc4d9-114">2</span><span class="sxs-lookup"><span data-stu-id="dc4d9-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="dc4d9-115">2</span><span class="sxs-lookup"><span data-stu-id="dc4d9-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="dc4d9-116">2</span><span class="sxs-lookup"><span data-stu-id="dc4d9-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="dc4d9-117">3</span><span class="sxs-lookup"><span data-stu-id="dc4d9-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="dc4d9-118">4</span><span class="sxs-lookup"><span data-stu-id="dc4d9-118">4</span></span>     |

<span data-ttu-id="dc4d9-119">Note:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-119">Notes:</span></span>

1. <span data-ttu-id="dc4d9-120">La codifica standard per `int32` e `int64` è inefficiente quando si utilizzano valori firmati.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="dc4d9-121">Se è probabile che il campo contenga numeri negativi, usare invece `sint32` o `sint64`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="dc4d9-122">Questi tipi vengono mappati C# rispettivamente ai tipi `int` e `long`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="dc4d9-123">I campi `fixed` utilizzano sempre lo stesso numero di byte indipendentemente dal valore.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="dc4d9-124">Questo comportamento rende più veloci la serializzazione e la deserializzazione per valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="dc4d9-125">Le stringhe protobuf sono con codifica UTF-8 (o ASCII a 7 bit).</span><span class="sxs-lookup"><span data-stu-id="dc4d9-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="dc4d9-126">La lunghezza codificata non può essere maggiore di 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="dc4d9-127">Il runtime di protobuf fornisce un tipo di `ByteString` che esegue il mapping C# facilmente da e verso `byte[]` matrici.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="dc4d9-128">Altri tipi primitivi .NET</span><span class="sxs-lookup"><span data-stu-id="dc4d9-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="dc4d9-129">Date e ore</span><span class="sxs-lookup"><span data-stu-id="dc4d9-129">Dates and times</span></span>

<span data-ttu-id="dc4d9-130">I tipi scalari nativi non forniscono i valori di data e ora, C#equivalenti a <xref:System.DateTimeOffset>, <xref:System.DateTime>e <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="dc4d9-131">È possibile specificare questi tipi usando alcune estensioni "tipi noti" di Google.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="dc4d9-132">Queste estensioni forniscono il supporto per la generazione di codice e il runtime per i tipi di campo complessi nelle piattaforme supportate.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="dc4d9-133">La tabella seguente illustra i tipi di data e ora:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="dc4d9-134">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="dc4d9-134">C# type</span></span> | <span data-ttu-id="dc4d9-135">Tipo noto protobuf</span><span class="sxs-lookup"><span data-stu-id="dc4d9-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="dc4d9-136">Le proprietà generate nella C# classe non sono i tipi di data e ora .NET.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="dc4d9-137">Le proprietà utilizzano le classi `Timestamp` e `Duration` nello spazio dei nomi `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="dc4d9-138">Queste classi forniscono metodi per la conversione da e verso `DateTimeOffset`, `DateTime`e `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="dc4d9-139">Il tipo di `Timestamp` funziona con le ore UTC.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="dc4d9-140">i valori `DateTimeOffset` hanno sempre un offset pari a zero e la proprietà `DateTime.Kind` è sempre `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="dc4d9-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="dc4d9-141">System.Guid</span></span>

<span data-ttu-id="dc4d9-142">Protobuf non supporta direttamente il tipo <xref:System.Guid>, noto come `UUID` su altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="dc4d9-143">Non esiste alcun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="dc4d9-144">L'approccio migliore consiste nel gestire i valori `Guid` come `string` campo, usando il formato esadecimale `8-4-4-4-12` standard, ad esempio `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="dc4d9-145">Tutti i linguaggi e le piattaforme possono analizzare tale formato.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="dc4d9-146">Non usare un campo `bytes` per `Guid` valori.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="dc4d9-147">I problemi con l'impostazione dell'ordine di *byte (* [definizione di Wikipedia](https://en.wikipedia.org/wiki/Endianness)) possono causare un comportamento anomalo quando protobuf interagisce con altre piattaforme, ad esempio Java.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="dc4d9-148">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="dc4d9-148">Nullable types</span></span>

<span data-ttu-id="dc4d9-149">La generazione di codice protobuf C# per utilizza i tipi nativi, ad esempio `int` per `int32`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="dc4d9-150">Pertanto, i valori vengono sempre inclusi e non possono essere null.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="dc4d9-151">Per i valori che richiedono un valore null esplicito, ad esempio C# l'uso di `int?` nel codice, i "tipi noti" di protobuf includono wrapper compilati in tipi Nullable C# .</span><span class="sxs-lookup"><span data-stu-id="dc4d9-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="dc4d9-152">Per usarli, importare `wrappers.proto` nel file di `.proto`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="dc4d9-153">Protobuf utilizzerà la semplice `T?` (ad esempio `int?`) per la proprietà del messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="dc4d9-154">La tabella seguente mostra l'elenco completo dei tipi di wrapper con il C# tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="dc4d9-155">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="dc4d9-155">C# type</span></span>   | <span data-ttu-id="dc4d9-156">Wrapper di tipo noto</span><span class="sxs-lookup"><span data-stu-id="dc4d9-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="dc4d9-157">I tipi noti `Timestamp` e `Duration` sono rappresentati in .NET come classi, quindi non è necessaria una versione nullable.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="dc4d9-158">Tuttavia è importante verificare la presenza di valori null per le proprietà di tali tipi durante la conversione in `DateTimeOffset` o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="dc4d9-159">Decimali</span><span class="sxs-lookup"><span data-stu-id="dc4d9-159">Decimals</span></span>

<span data-ttu-id="dc4d9-160">Protobuf non supporta in modo nativo il tipo di `decimal` .NET, ma solo `double` e `float`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="dc4d9-161">Nel progetto protobuf è presente una discussione continuativa sulla possibilità di aggiungere un tipo di `Decimal` standard ai tipi noti, con supporto della piattaforma per linguaggi e Framework che lo supportano.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="dc4d9-162">Non è stato ancora implementato alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="dc4d9-163">È possibile creare una definizione di messaggio per rappresentare il tipo di `decimal` che funzionerebbe per la serializzazione sicura tra client e server .NET.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="dc4d9-164">Gli sviluppatori su altre piattaforme dovrebbero tuttavia comprendere il formato usato e implementare la propria gestione per l'it.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="dc4d9-165">Creazione di un tipo decimale personalizzato per protobuf</span><span class="sxs-lookup"><span data-stu-id="dc4d9-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="dc4d9-166">Una semplice implementazione potrebbe essere simile al tipo di `Money` non standard usato da alcune API Google, senza il campo `currency`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="dc4d9-167">Il campo `nanos` rappresenta i valori da `0.999_999_999` a `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="dc4d9-168">Ad esempio, il valore `decimal` `1.5m` verrebbe rappresentato come `{ units = 1, nanos = 500_000_000 }`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="dc4d9-169">Questo è il motivo per cui nel campo `nanos` di questo esempio viene usato il tipo di `sfixed32`, che codifica in modo più efficiente rispetto al `int32` per valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="dc4d9-170">Se il campo `units` è negativo, anche il campo `nanos` dovrebbe essere negativo.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="dc4d9-171">Sono disponibili più algoritmi per codificare `decimal` valori come stringhe di byte, ma questo messaggio è più facile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="dc4d9-172">I valori non sono interessati da un valore di endian su piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="dc4d9-173">La conversione tra questo tipo e il tipo di `decimal` BCL potrebbe essere C# implementata in modo analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="dc4d9-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="dc4d9-174">Quando si usano tipi di messaggio personalizzati come questo, è *necessario* documentarli con commenti in `.proto`.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="dc4d9-175">Gli altri sviluppatori possono quindi implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o Framework.</span><span class="sxs-lookup"><span data-stu-id="dc4d9-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc4d9-176">[Precedente](protobuf-messages.md)
>[Successivo](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="dc4d9-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
