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
# <a name="protobuf-maps-for-dictionaries"></a>Mappe protobuf per i dizionari

È importante essere in grado di rappresentare raccolte arbitrarie di valori denominati nei messaggi. In .NET, questo viene comunemente gestito tramite i tipi di dizionario. L'equivalente del tipo di <xref:System.Collections.Generic.IDictionary%602> .NET nel buffer del protocollo (protobuf) è il tipo di `map<key_type, value_type>`. In questa sezione viene illustrato come dichiarare un tipo di `map` in protobuf e come utilizzare il codice generato.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

Nel codice generato `map` campi utilizzano la classe `Google.Protobuf.Collections.MapField<TKey, TValue>`. Questa classe implementa le interfacce della raccolta .NET standard, incluso <xref:System.Collections.Generic.IDictionary%602>.

I campi mappa non possono essere ripetuti direttamente in una definizione di messaggio. È tuttavia possibile creare un messaggio annidato contenente una mappa e utilizzare `repeated` sul tipo di messaggio, come nell'esempio seguente:

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
