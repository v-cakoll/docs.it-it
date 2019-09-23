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
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Protobuf i campi any e di per i tipi Variant

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La gestione dei tipi di proprietà dinamici (ovvero le proprietà `object`di tipo) in WCF è complessa. È necessario specificare i serializzatori, è necessario fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) e così via.

Protobuf offre due opzioni più semplici per gestire i valori che possono essere di più di un tipo. Il `Any` tipo può rappresentare qualsiasi tipo di messaggio protobuf noto, mentre `oneof` la parola chiave consente di specificare che è possibile impostare solo uno di un intervallo di campi in un determinato messaggio.

## <a name="any"></a>Qualsiasi

`Any`è uno dei "tipi noti" di protobuf: una raccolta di tipi di messaggi utili e riutilizzabili con implementazioni in tutte le lingue supportate. Per usare il `Any` tipo, è necessario importare la `google/protobuf/any.proto` definizione.

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

Nel C# codice, la `Any` classe fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.

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

Il `Descriptor` campo statico di ogni tipo generato viene usato dal codice di Reflection interno di protobuf per `Any` risolvere i tipi di campo. Esiste anche un `TryUnpack<T>` metodo, ma crea un'istanza non inizializzata di anche in `T` caso di errore, quindi è preferibile usare il `Is` metodo come illustrato in precedenza.

## <a name="oneof"></a>Di

I campi di sono una funzionalità del linguaggio `oneof` : la parola chiave viene gestita dal compilatore quando genera la classe Message. L' `oneof` utilizzo di per `ChangeNotification` specificare il messaggio potrebbe essere simile al seguente:

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

I campi all' `oneof` interno del set devono avere numeri di campo univoci all'interno della dichiarazione generale del messaggio.

Quando si usa `oneof`, il codice C# generato include un'enumerazione che specifica quale dei campi è stata impostata. È possibile testare l'enumerazione per individuare il campo da impostare. I campi che non sono `null` impostati restituiscono o il valore predefinito, anziché generare un'eccezione.

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

L'impostazione di qualsiasi campo che fa parte `oneof` di un set eliminerà automaticamente tutti gli altri campi nel set. Non è possibile `repeated` usare `oneof`con. È invece possibile creare un messaggio annidato con il campo ripetuto o il `oneof` set per ovviare a questa limitazione.

>[!div class="step-by-step"]
>[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)
