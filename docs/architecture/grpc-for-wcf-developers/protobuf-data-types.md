---
title: Tipi di dati scalari Protobuf - gRPC per gli sviluppatori WCFProtobuf scalar data types - gRPC for WCF developers
description: Informazioni sui tipi di dati di base e noti supportati da Protobuf e gRPC in .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249435"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="d4c0f-103">Tipi di dati scalari protobuf</span><span class="sxs-lookup"><span data-stu-id="d4c0f-103">Protobuf scalar data types</span></span>

<span data-ttu-id="d4c0f-104">Protocol Buffer (Protobuf) supporta un intervallo di tipi di valore scalare nativi.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="d4c0f-105">Nella tabella seguente sono elencati tutti con il tipo equivalente di C':</span><span class="sxs-lookup"><span data-stu-id="d4c0f-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="d4c0f-106">Tipo di protobuf</span><span class="sxs-lookup"><span data-stu-id="d4c0f-106">Protobuf type</span></span> | <span data-ttu-id="d4c0f-107">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="d4c0f-107">C# type</span></span>      | <span data-ttu-id="d4c0f-108">Note</span><span class="sxs-lookup"><span data-stu-id="d4c0f-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="d4c0f-109">1</span><span class="sxs-lookup"><span data-stu-id="d4c0f-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="d4c0f-110">1</span><span class="sxs-lookup"><span data-stu-id="d4c0f-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="d4c0f-111">1</span><span class="sxs-lookup"><span data-stu-id="d4c0f-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="d4c0f-112">1</span><span class="sxs-lookup"><span data-stu-id="d4c0f-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="d4c0f-113">2</span><span class="sxs-lookup"><span data-stu-id="d4c0f-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="d4c0f-114">2</span><span class="sxs-lookup"><span data-stu-id="d4c0f-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="d4c0f-115">2</span><span class="sxs-lookup"><span data-stu-id="d4c0f-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="d4c0f-116">2</span><span class="sxs-lookup"><span data-stu-id="d4c0f-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="d4c0f-117">3</span><span class="sxs-lookup"><span data-stu-id="d4c0f-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="d4c0f-118">4</span><span class="sxs-lookup"><span data-stu-id="d4c0f-118">4</span></span>     |

<span data-ttu-id="d4c0f-119">Note:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-119">Notes:</span></span>

1. <span data-ttu-id="d4c0f-120">La codifica `int32` standard `int64` per e è inefficiente quando si lavora con valori firmati.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="d4c0f-121">Se è probabile che il campo `sint32` `sint64` contenga numeri negativi, utilizzare o invece.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="d4c0f-122">Questi tipi eseguono `int` il `long` mapping al linguaggio C e ai tipi, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="d4c0f-123">I `fixed` campi utilizzano sempre lo stesso numero di byte, indipendentemente dal valore.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="d4c0f-124">Questo comportamento rende la serializzazione e deserializzazione più veloce per valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="d4c0f-125">Le stringhe protobuf sono codificate in UTF-8 (o ASCII a 7 bit).</span><span class="sxs-lookup"><span data-stu-id="d4c0f-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="d4c0f-126">La lunghezza codificata non può essere maggiore di 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="d4c0f-127">Il runtime di Protobuf fornisce un `ByteString` tipo `byte[]` che esegue il mapping facilmente a e da matrici C .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="d4c0f-128">Altri tipi primitivi .NET</span><span class="sxs-lookup"><span data-stu-id="d4c0f-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="d4c0f-129">Date e ore</span><span class="sxs-lookup"><span data-stu-id="d4c0f-129">Dates and times</span></span>

<span data-ttu-id="d4c0f-130">I tipi scalari nativi non forniscono valori di data e <xref:System.DateTimeOffset> <xref:System.DateTime>ora, <xref:System.TimeSpan>equivalenti a quelli di C, , e .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="d4c0f-131">Puoi specificare questi tipi utilizzando alcune delle estensioni "Tipi noti" di Google.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="d4c0f-132">Queste estensioni forniscono la generazione di codice e il supporto runtime per i tipi di campo complessi nelle piattaforme supportate.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="d4c0f-133">Nella tabella seguente vengono illustrati i tipi di data e ora:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="d4c0f-134">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="d4c0f-134">C# type</span></span> | <span data-ttu-id="d4c0f-135">Protobuf tipo ben noto</span><span class="sxs-lookup"><span data-stu-id="d4c0f-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="d4c0f-136">Le proprietà generate nella classe C , non sono i tipi di data e ora .NET.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="d4c0f-137">Le proprietà `Timestamp` utilizzano le classi e `Duration` nello `Google.Protobuf.WellKnownTypes` spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="d4c0f-138">Queste classi forniscono metodi per `DateTimeOffset` `DateTime`la `TimeSpan`conversione in e da , e .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="d4c0f-139">Il `Timestamp` tipo funziona con l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="d4c0f-140">`DateTimeOffset`i valori hanno sempre un `DateTime.Kind` offset pari `DateTimeKind.Utc`a zero e la proprietà è sempre .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="d4c0f-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="d4c0f-141">System.Guid</span></span>

<span data-ttu-id="d4c0f-142">Protobuf non supporta direttamente <xref:System.Guid> il tipo, noto come `UUID` su altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="d4c0f-143">Non c'è un tipo ben noto per questo.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-143">There's no well-known type for it.</span></span>

<span data-ttu-id="d4c0f-144">L'approccio migliore `Guid` consiste `string` nel gestire i `8-4-4-4-12` valori come campo, utilizzando `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`il formato esadecimale standard (ad esempio, ).</span><span class="sxs-lookup"><span data-stu-id="d4c0f-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="d4c0f-145">Tutte le lingue e le piattaforme possono analizzare tale formato.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="d4c0f-146">Non usare un `bytes` campo `Guid` per i valori.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="d4c0f-147">Problemi di *endianness* ([definizione](https://en.wikipedia.org/wiki/Endianness)di Wikipedia ) possono causare un comportamento irregolare quando Protobuf interagisce con altre piattaforme, come Java.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="d4c0f-148">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="d4c0f-148">Nullable types</span></span>

<span data-ttu-id="d4c0f-149">La generazione di codice Protobuf per il `int` linguaggio C, utilizza i tipi nativi, ad esempio per `int32`.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="d4c0f-150">Quindi i valori sono sempre inclusi e non possono essere null.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="d4c0f-151">Per i valori che richiedono `int?` valori null espliciti, ad esempio l'utilizzo nel codice C, i "Tipi noti" di Protobuf includono wrapper che vengono compilati in tipi C .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="d4c0f-152">Per usarli, `wrappers.proto` importa `.proto` nel tuo file, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="d4c0f-153">Protobuf utilizzerà `T?` il semplice `int?`(ad esempio, ) per la proprietà del messaggio generato.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="d4c0f-154">Nella tabella seguente viene illustrato l'elenco completo dei tipi di wrapper con il tipo equivalente in C:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="d4c0f-155">Tipo C#</span><span class="sxs-lookup"><span data-stu-id="d4c0f-155">C# type</span></span>   | <span data-ttu-id="d4c0f-156">Wrapper del tipo noto</span><span class="sxs-lookup"><span data-stu-id="d4c0f-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="d4c0f-157">I tipi `Timestamp` noti `Duration` e sono rappresentati in .NET come classi.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="d4c0f-158">In C '8 e oltre, è possibile usare i tipi di riferimento nullable.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="d4c0f-159">Ma è importante verificare la presenza di valori null sulle `DateTimeOffset` proprietà `TimeSpan`di tali tipi durante la conversione in o .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="d4c0f-160">Decimali</span><span class="sxs-lookup"><span data-stu-id="d4c0f-160">Decimals</span></span>

<span data-ttu-id="d4c0f-161">Protobuf non supporta in modo `decimal` nativo il `double` `float`tipo .NET, just e .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="d4c0f-162">C'è una discussione in corso nel progetto Protobuf sulla possibilità di aggiungere un tipo standard `Decimal` per i tipi noti, con il supporto della piattaforma per i linguaggi e framework che lo supportano.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="d4c0f-163">Nulla è stato ancora implementato.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="d4c0f-164">È possibile creare una definizione di `decimal` messaggio per rappresentare il tipo che funzionerebbe per la serializzazione sicura tra client e server .NET.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="d4c0f-165">Ma gli sviluppatori su altre piattaforme dovrebbero comprendere il formato utilizzato e implementare la propria gestione per esso.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="d4c0f-166">Creazione di un tipo decimale personalizzato per Protobuf</span><span class="sxs-lookup"><span data-stu-id="d4c0f-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="d4c0f-167">Un'implementazione semplice potrebbe essere `Money` simile al tipo non standard `currency` utilizzato da alcune API Google, senza il campo.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="d4c0f-168">Il `nanos` campo rappresenta `0.999_999_999` `-0.999_999_999`i valori da a .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="d4c0f-169">Ad esempio, `decimal` `1.5m` il valore `{ units = 1, nanos = 500_000_000 }`verrebbe rappresentato come .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="d4c0f-170">Questo è `nanos` il motivo per `sfixed32` cui il campo in `int32` questo esempio utilizza il tipo, che codifica in modo più efficiente rispetto ai valori più grandi.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="d4c0f-171">Se `units` il campo è `nanos` negativo, anche il campo deve essere negativo.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c0f-172">Esistono più altri algoritmi `decimal` per la codifica dei valori come stringhe di byte, ma questo messaggio è più facile da comprendere rispetto a qualsiasi di essi.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="d4c0f-173">I valori non sono influenzati dall'endianness su piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="d4c0f-174">La conversione tra questo `decimal` tipo e il tipo BCL potrebbe essere implementata in C , in questo modo:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="d4c0f-175">Ogni volta che si utilizzano *must* tipi di messaggio `.proto`personalizzati come questo, è necessario documentarli con commenti in .</span><span class="sxs-lookup"><span data-stu-id="d4c0f-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="d4c0f-176">Altri sviluppatori possono quindi implementare la conversione da e verso il tipo equivalente nel proprio linguaggio o framework.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d4c0f-177">[Successivo](protobuf-messages.md)
>[precedente](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="d4c0f-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
