---
title: Protobuf Maps for dictionarys-gRPC per sviluppatori WCF
description: Informazioni su come usare le mappe protobuf per rappresentare. Tipi di dizionario di NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f6a71fb7940145571a94eaf5c8bae9dfc91a30db
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184211"
---
# <a name="protobuf-maps-for-dictionaries"></a>Mappe protobuf per i dizionari

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

È importante essere in grado di rappresentare raccolte arbitrarie di valori denominati nei messaggi. In .NET questo viene comunemente gestito con i tipi di dizionario. L'equivalente di protobuf del tipo <xref:System.Collections.Generic.IDictionary%602> .NET è il `map<key_type, value_type>` tipo. In questa sezione viene illustrato come dichiarare `map` un in protobuf e come utilizzare il codice generato.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Nel codice generato, `map` i campi utilizzano la `Google.Protobuf.Collections.MapField<TKey, TValue>` classe, che implementa le interfacce di raccolta .NET standard, tra cui. <xref:System.Collections.Generic.IDictionary%602>

I campi mappa non possono essere ripetuti direttamente nella definizione di un messaggio, ma è possibile creare un messaggio annidato `repeated` contenente una mappa e utilizzare il tipo di messaggio, come nell'esempio seguente:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Uso delle proprietà di MapField nel codice

Le `MapField` proprietà generate `map` dai campi sono di sola lettura e non saranno mai `null`. Per impostare una proprietà Map, utilizzare il `Add(IDictionary<TKey,TValue> values)` metodo sulla proprietà Empty `MapField` per copiare i valori da qualsiasi dizionario .NET.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Ulteriori informazioni

Per ulteriori informazioni su protobuf, vedere la documentazione ufficiale di [protobuf](https://developers.google.com/protocol-buffers/docs/overview).

>[!div class="step-by-step"]
>[Precedente](protobuf-enums.md)
>[Successivo](wcf-services-to-grpc-comparison.md)
