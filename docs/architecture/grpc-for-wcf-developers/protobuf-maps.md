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
# <a name="protobuf-maps-for-dictionaries"></a>Mappe protobuf per i dizionari

È importante essere in grado di rappresentare raccolte arbitrarie di valori denominati nei messaggi. In .NET questo viene comunemente gestito con i tipi di dizionario. L'equivalente di protobuf del tipo di <xref:System.Collections.Generic.IDictionary%602> .NET è il tipo di `map<key_type, value_type>`. In questa sezione viene illustrato come dichiarare un `map` in protobuf e come utilizzare il codice generato.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Nel codice generato `map` campi utilizzano la classe `Google.Protobuf.Collections.MapField<TKey, TValue>`, che implementa le interfacce di raccolta .NET standard, incluso <xref:System.Collections.Generic.IDictionary%602>.

I campi mappa non possono essere ripetuti direttamente nella definizione di un messaggio, ma è possibile creare un messaggio annidato contenente una mappa e utilizzare `repeated` per il tipo di messaggio, come nell'esempio seguente:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Uso delle proprietà di MapField nel codice

Le proprietà `MapField` generate dai campi `map` sono di sola lettura e non verranno mai `null`. Per impostare una proprietà Map, utilizzare il metodo `Add(IDictionary<TKey,TValue> values)` sulla proprietà `MapField` vuota per copiare i valori da qualsiasi dizionario .NET.

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
