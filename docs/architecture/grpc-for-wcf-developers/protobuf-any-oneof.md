---
title: Protobuf i campi any e di per i tipi Variant-gRPC per gli sviluppatori WCF
description: Informazioni su come usare il tipo any e la parola chiave di per rappresentare i tipi di oggetti Variant nei messaggi.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 10f55288eb4a6aa603228da5b4850317d6bde614
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846384"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Protobuf i campi any e di per i tipi Variant

La gestione dei tipi di proprietà dinamici (ovvero le proprietà di tipo `object`) in WCF è complessa. È necessario specificare i serializzatori, è necessario fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) e così via.

Protobuf offre due opzioni più semplici per gestire i valori che possono essere di più di un tipo. Il tipo di `Any` può rappresentare qualsiasi tipo di messaggio protobuf noto, mentre la parola chiave `oneof` consente di specificare che è possibile impostare solo uno di un intervallo di campi in un determinato messaggio.

## <a name="any"></a>Qualsiasi

`Any` è uno dei "tipi noti" di protobuf: una raccolta di tipi di messaggi utili e riutilizzabili con implementazioni in tutte le lingue supportate. Per usare il tipo di `Any`, è necessario importare la definizione del `google/protobuf/any.proto`.

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

Nel C# codice, la classe`Any`fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.

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

Il `Descriptor` campo statico in ogni tipo generato viene usato dal codice di Reflection interno di protobuf per risolvere `Any` tipi di campo. Esiste anche un metodo di `TryUnpack<T>`, ma crea un'istanza non inizializzata di `T` anche in caso di errore, quindi è preferibile usare il metodo `Is` come illustrato in precedenza.

## <a name="oneof"></a>Di

I campi di sono una funzionalità del linguaggio: la parola chiave `oneof` viene gestita dal compilatore quando genera la classe Message. L'utilizzo di `oneof` per specificare il `ChangeNotification` messaggio potrebbe essere simile al seguente:

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

I campi all'interno del set di `oneof` devono contenere numeri di campo univoci all'interno della dichiarazione generale del messaggio.

Quando si utilizza `oneof`, il codice C# generato include un'enumerazione che specifica quale dei campi è stata impostata. È possibile testare l'enumerazione per individuare il campo da impostare. I campi che non vengono impostati restituiscono `null` o il valore predefinito, anziché generare un'eccezione.

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

L'impostazione di un campo che fa parte di un set di `oneof` eliminerà automaticamente tutti gli altri campi nel set. Non è possibile usare `repeated` con `oneof`. In alternativa, è possibile creare un messaggio annidato con il campo ripetuto o il set di `oneof` per aggirare questa limitazione.

>[!div class="step-by-step"]
>[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)
