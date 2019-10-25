---
title: Protobuf Maps for dictionarys-gRPC per sviluppatori WCF
description: Informazioni su come usare le mappe protobuf per rappresentare. Tipi di dizionario di NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846330"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="deaea-103">Mappe protobuf per i dizionari</span><span class="sxs-lookup"><span data-stu-id="deaea-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="deaea-104">È importante essere in grado di rappresentare raccolte arbitrarie di valori denominati nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="deaea-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="deaea-105">In .NET questo viene comunemente gestito con i tipi di dizionario.</span><span class="sxs-lookup"><span data-stu-id="deaea-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="deaea-106">L'equivalente di protobuf del tipo di <xref:System.Collections.Generic.IDictionary%602> .NET è il tipo di `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="deaea-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="deaea-107">In questa sezione viene illustrato come dichiarare un `map` in protobuf e come utilizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="deaea-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="deaea-108">Nel codice generato `map` campi utilizzano la classe `Google.Protobuf.Collections.MapField<TKey, TValue>`, che implementa le interfacce di raccolta .NET standard, incluso <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="deaea-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="deaea-109">I campi mappa non possono essere ripetuti direttamente nella definizione di un messaggio, ma è possibile creare un messaggio annidato contenente una mappa e utilizzare `repeated` per il tipo di messaggio, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="deaea-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="deaea-110">Uso delle proprietà di MapField nel codice</span><span class="sxs-lookup"><span data-stu-id="deaea-110">Using MapField properties in code</span></span>

<span data-ttu-id="deaea-111">Le proprietà `MapField` generate dai campi `map` sono di sola lettura e non verranno mai `null`.</span><span class="sxs-lookup"><span data-stu-id="deaea-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="deaea-112">Per impostare una proprietà Map, utilizzare il metodo `Add(IDictionary<TKey,TValue> values)` sulla proprietà `MapField` vuota per copiare i valori da qualsiasi dizionario .NET.</span><span class="sxs-lookup"><span data-stu-id="deaea-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="deaea-113">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="deaea-113">Further reading</span></span>

<span data-ttu-id="deaea-114">Per ulteriori informazioni su protobuf, vedere la documentazione ufficiale di [protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="deaea-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="deaea-115">[Precedente](protobuf-enums.md)
>[Successivo](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="deaea-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
