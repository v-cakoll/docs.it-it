---
title: Protobuf i campi any e di per i tipi Variant-gRPC per gli sviluppatori WCF
description: Informazioni su come usare il tipo any e la parola chiave di per rappresentare i tipi di oggetti Variant nei messaggi.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543196"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="fd772-103">Protobuf i campi any e di per i tipi Variant</span><span class="sxs-lookup"><span data-stu-id="fd772-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="fd772-104">La gestione dei tipi di proprietà dinamici (ovvero le proprietà di tipo `object`) in Windows Communication Foundation (WCF) è complessa.</span><span class="sxs-lookup"><span data-stu-id="fd772-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="fd772-105">È ad esempio necessario specificare i serializzatori e fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="fd772-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="fd772-106">Protocollo buffer (protobuf) fornisce due opzioni più semplici per gestire valori che potrebbero essere di più di un tipo.</span><span class="sxs-lookup"><span data-stu-id="fd772-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="fd772-107">Il tipo di `Any` può rappresentare qualsiasi tipo di messaggio protobuf noto.</span><span class="sxs-lookup"><span data-stu-id="fd772-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="fd772-108">È possibile usare la parola chiave `oneof` per specificare che è possibile impostare solo uno di un intervallo di campi in qualsiasi messaggio.</span><span class="sxs-lookup"><span data-stu-id="fd772-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="fd772-109">Any</span><span class="sxs-lookup"><span data-stu-id="fd772-109">Any</span></span>

<span data-ttu-id="fd772-110">`Any` è uno dei "tipi noti" di protobuf: una raccolta di tipi di messaggi utili e riutilizzabili con implementazioni in tutte le lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="fd772-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="fd772-111">Per usare il tipo di `Any`, è necessario importare la definizione del `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="fd772-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="fd772-112">Nel C# codice, la classe `Any` fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.</span><span class="sxs-lookup"><span data-stu-id="fd772-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="fd772-113">Il codice di Reflection interno di protobuf usa il campo statico `Descriptor` in ogni tipo generato per risolvere `Any` tipi di campo.</span><span class="sxs-lookup"><span data-stu-id="fd772-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="fd772-114">Esiste anche un metodo di `TryUnpack<T>`, ma crea un'istanza non inizializzata di `T` anche in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="fd772-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="fd772-115">È preferibile usare il metodo `Is` come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fd772-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="fd772-116">Di</span><span class="sxs-lookup"><span data-stu-id="fd772-116">Oneof</span></span>

<span data-ttu-id="fd772-117">I campi di sono una funzionalità del linguaggio: il compilatore gestisce la parola chiave `oneof` quando genera la classe Message.</span><span class="sxs-lookup"><span data-stu-id="fd772-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="fd772-118">L'utilizzo di `oneof` per specificare il `ChangeNotification` messaggio potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fd772-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="fd772-119">I campi all'interno del set di `oneof` devono contenere numeri di campo univoci nella dichiarazione generale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="fd772-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="fd772-120">Quando si utilizza `oneof`, il codice C# generato include un'enumerazione che specifica quale dei campi è stata impostata.</span><span class="sxs-lookup"><span data-stu-id="fd772-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="fd772-121">È possibile testare l'enumerazione per individuare il campo da impostare.</span><span class="sxs-lookup"><span data-stu-id="fd772-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="fd772-122">I campi che non vengono impostati restituiscono `null` o il valore predefinito, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fd772-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="fd772-123">Impostando qualsiasi campo che fa parte di un set di `oneof` verranno cancellati automaticamente tutti gli altri campi nel set.</span><span class="sxs-lookup"><span data-stu-id="fd772-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="fd772-124">Non è possibile usare `repeated` con `oneof`.</span><span class="sxs-lookup"><span data-stu-id="fd772-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="fd772-125">In alternativa, è possibile creare un messaggio annidato con il campo ripetuto o il set di `oneof` per aggirare questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="fd772-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fd772-126">[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="fd772-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
