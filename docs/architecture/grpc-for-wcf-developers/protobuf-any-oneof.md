---
title: Protobuf i campi any e di per i tipi Variant-gRPC per gli sviluppatori WCF
description: Informazioni su come usare il tipo any e la parola chiave di per rappresentare i tipi di oggetti Variant nei messaggi.
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971608"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="aa9f3-103">Protobuf i campi any e di per i tipi Variant</span><span class="sxs-lookup"><span data-stu-id="aa9f3-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="aa9f3-104">La gestione dei tipi di proprietà dinamici (ovvero le proprietà di tipo `object`) in WCF è complessa.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="aa9f3-105">È necessario specificare i serializzatori, è necessario fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) e così via.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="aa9f3-106">Protobuf offre due opzioni più semplici per gestire i valori che possono essere di più di un tipo.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="aa9f3-107">Il tipo di `Any` può rappresentare qualsiasi tipo di messaggio protobuf noto, mentre la parola chiave `oneof` consente di specificare che è possibile impostare solo uno di un intervallo di campi in un determinato messaggio.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="aa9f3-108">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="aa9f3-108">Any</span></span>

<span data-ttu-id="aa9f3-109">`Any` è uno dei "tipi noti" di protobuf: una raccolta di tipi di messaggi utili e riutilizzabili con implementazioni in tutte le lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="aa9f3-110">Per usare il tipo di `Any`, è necessario importare la definizione del `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="aa9f3-111">Nel C# codice, la classe `Any` fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="aa9f3-112">Il `Descriptor` campo statico in ogni tipo generato viene usato dal codice di Reflection interno di protobuf per risolvere `Any` tipi di campo.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="aa9f3-113">Esiste anche un metodo di `TryUnpack<T>`, ma crea un'istanza non inizializzata di `T` anche in caso di errore, quindi è preferibile usare il metodo `Is` come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="aa9f3-114">Di</span><span class="sxs-lookup"><span data-stu-id="aa9f3-114">Oneof</span></span>

<span data-ttu-id="aa9f3-115">I campi di sono una funzionalità del linguaggio: la parola chiave `oneof` viene gestita dal compilatore quando genera la classe Message.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="aa9f3-116">L'utilizzo di `oneof` per specificare il `ChangeNotification` messaggio potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="aa9f3-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="aa9f3-117">I campi all'interno del set di `oneof` devono contenere numeri di campo univoci all'interno della dichiarazione generale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="aa9f3-118">Quando si utilizza `oneof`, il codice C# generato include un'enumerazione che specifica quale dei campi è stata impostata.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="aa9f3-119">È possibile testare l'enumerazione per individuare il campo da impostare.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="aa9f3-120">I campi che non vengono impostati restituiscono `null` o il valore predefinito, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="aa9f3-121">L'impostazione di un campo che fa parte di un set di `oneof` eliminerà automaticamente tutti gli altri campi nel set.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="aa9f3-122">Non è possibile usare `repeated` con `oneof`.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="aa9f3-123">In alternativa, è possibile creare un messaggio annidato con il campo ripetuto o il set di `oneof` per aggirare questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="aa9f3-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aa9f3-124">[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="aa9f3-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
