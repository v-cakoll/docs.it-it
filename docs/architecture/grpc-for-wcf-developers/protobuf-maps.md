---
title: Protobuf Maps for dictionarys-gRPC per sviluppatori WCF
description: Informazioni su come usare le mappe protobuf per rappresentare i tipi di dizionario in .NET.
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543131"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="03865-103">Mappe protobuf per i dizionari</span><span class="sxs-lookup"><span data-stu-id="03865-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="03865-104">È importante essere in grado di rappresentare raccolte arbitrarie di valori denominati nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="03865-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="03865-105">In .NET, questo viene comunemente gestito tramite i tipi di dizionario.</span><span class="sxs-lookup"><span data-stu-id="03865-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="03865-106">L'equivalente del tipo di <xref:System.Collections.Generic.IDictionary%602> .NET nel buffer del protocollo (protobuf) è il tipo di `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="03865-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="03865-107">In questa sezione viene illustrato come dichiarare un tipo di `map` in protobuf e come utilizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="03865-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="03865-108">Nel codice generato `map` campi utilizzano la classe `Google.Protobuf.Collections.MapField<TKey, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="03865-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="03865-109">Questa classe implementa le interfacce della raccolta .NET standard, incluso <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="03865-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="03865-110">I campi mappa non possono essere ripetuti direttamente in una definizione di messaggio.</span><span class="sxs-lookup"><span data-stu-id="03865-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="03865-111">È tuttavia possibile creare un messaggio annidato contenente una mappa e utilizzare `repeated` sul tipo di messaggio, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="03865-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="03865-112">Uso delle proprietà di MapField nel codice</span><span class="sxs-lookup"><span data-stu-id="03865-112">Using MapField properties in code</span></span>

<span data-ttu-id="03865-113">Le proprietà `MapField` generate dai campi `map` sono di sola lettura e non verranno mai `null`.</span><span class="sxs-lookup"><span data-stu-id="03865-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="03865-114">Per impostare una proprietà Map, utilizzare il metodo `Add(IDictionary<TKey,TValue> values)` sulla proprietà `MapField` vuota per copiare i valori da qualsiasi dizionario .NET.</span><span class="sxs-lookup"><span data-stu-id="03865-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="03865-115">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="03865-115">Further reading</span></span>

<span data-ttu-id="03865-116">Per ulteriori informazioni su protobuf, vedere la documentazione ufficiale di [protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="03865-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="03865-117">[Precedente](protobuf-enums.md)
>[Successivo](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="03865-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
