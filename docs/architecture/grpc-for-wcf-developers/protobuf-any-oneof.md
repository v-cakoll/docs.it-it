---
title: Protobuf i campi any e di per i tipi Variant-gRPC per gli sviluppatori WCF
description: Informazioni su come usare il tipo any e la parola chiave di per rappresentare i tipi di oggetti Variant nei messaggi.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 9e730e96bfdb25ef6e07ee10967921408c6f2e84
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184281"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="c8c14-103">Protobuf i campi any e di per i tipi Variant</span><span class="sxs-lookup"><span data-stu-id="c8c14-103">Protobuf Any and Oneof fields for variant types</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c8c14-104">La gestione dei tipi di proprietà dinamici (ovvero le proprietà `object`di tipo) in WCF è complessa.</span><span class="sxs-lookup"><span data-stu-id="c8c14-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="c8c14-105">È necessario specificare i serializzatori, è necessario fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) e così via.</span><span class="sxs-lookup"><span data-stu-id="c8c14-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="c8c14-106">Protobuf offre due opzioni più semplici per gestire i valori che possono essere di più di un tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c14-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="c8c14-107">Il `Any` tipo può rappresentare qualsiasi tipo di messaggio protobuf noto, mentre `oneof` la parola chiave consente di specificare che è possibile impostare solo uno di un intervallo di campi in un determinato messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8c14-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="c8c14-108">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="c8c14-108">Any</span></span>

<span data-ttu-id="c8c14-109">`Any`è uno dei "tipi noti" di protobuf: una raccolta di tipi di messaggi utili e riutilizzabili con implementazioni in tutte le lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="c8c14-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="c8c14-110">Per usare il `Any` tipo, è necessario importare la `google/protobuf/any.proto` definizione.</span><span class="sxs-lookup"><span data-stu-id="c8c14-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="c8c14-111">Nel C# codice, la `Any` classe fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c14-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="c8c14-112">Il `Descriptor` campo statico di ogni tipo generato viene usato dal codice di Reflection interno di protobuf per `Any` risolvere i tipi di campo.</span><span class="sxs-lookup"><span data-stu-id="c8c14-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="c8c14-113">Esiste anche un `TryUnpack<T>` metodo, ma crea un'istanza non inizializzata di anche in `T` caso di errore, quindi è preferibile usare il `Is` metodo come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c8c14-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="c8c14-114">Di</span><span class="sxs-lookup"><span data-stu-id="c8c14-114">Oneof</span></span>

<span data-ttu-id="c8c14-115">I campi di sono una funzionalità del linguaggio `oneof` : la parola chiave viene gestita dal compilatore quando genera la classe Message.</span><span class="sxs-lookup"><span data-stu-id="c8c14-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="c8c14-116">L' `oneof` utilizzo di per `ChangeNotification` specificare il messaggio potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8c14-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="c8c14-117">I campi all' `oneof` interno del set devono avere numeri di campo univoci all'interno della dichiarazione generale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8c14-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="c8c14-118">Quando si usa `oneof`, il codice C# generato include un'enumerazione che specifica quale dei campi è stata impostata.</span><span class="sxs-lookup"><span data-stu-id="c8c14-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="c8c14-119">È possibile testare l'enumerazione per individuare il campo da impostare.</span><span class="sxs-lookup"><span data-stu-id="c8c14-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="c8c14-120">I campi che non sono `null` impostati restituiscono o il valore predefinito, anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c8c14-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="c8c14-121">L'impostazione di qualsiasi campo che fa parte `oneof` di un set eliminerà automaticamente tutti gli altri campi nel set.</span><span class="sxs-lookup"><span data-stu-id="c8c14-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="c8c14-122">Non è possibile `repeated` usare `oneof`con.</span><span class="sxs-lookup"><span data-stu-id="c8c14-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="c8c14-123">È invece possibile creare un messaggio annidato con il campo ripetuto o il `oneof` set per ovviare a questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="c8c14-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c8c14-124">[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="c8c14-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
