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
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Protobuf i campi any e di per i tipi Variant

La gestione dei tipi di proprietà dinamici (ovvero le proprietà di tipo `object`) in Windows Communication Foundation (WCF) è complessa. È ad esempio necessario specificare i serializzatori e fornire gli attributi [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) .

Protocollo buffer (protobuf) fornisce due opzioni più semplici per gestire valori che potrebbero essere di più di un tipo. Il tipo di `Any` può rappresentare qualsiasi tipo di messaggio protobuf noto. È possibile usare la parola chiave `oneof` per specificare che è possibile impostare solo uno di un intervallo di campi in qualsiasi messaggio.

## <a name="any"></a>Any

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

Nel C# codice, la classe `Any` fornisce metodi per l'impostazione del campo, l'estrazione del messaggio e il controllo del tipo.

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

Il codice di Reflection interno di protobuf usa il campo statico `Descriptor` in ogni tipo generato per risolvere `Any` tipi di campo. Esiste anche un metodo di `TryUnpack<T>`, ma crea un'istanza non inizializzata di `T` anche in caso di errore. È preferibile usare il metodo `Is` come illustrato in precedenza.

## <a name="oneof"></a>Di

I campi di sono una funzionalità del linguaggio: il compilatore gestisce la parola chiave `oneof` quando genera la classe Message. L'utilizzo di `oneof` per specificare il `ChangeNotification` messaggio potrebbe essere simile al seguente:

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

I campi all'interno del set di `oneof` devono contenere numeri di campo univoci nella dichiarazione generale del messaggio.

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

Impostando qualsiasi campo che fa parte di un set di `oneof` verranno cancellati automaticamente tutti gli altri campi nel set. Non è possibile usare `repeated` con `oneof`. In alternativa, è possibile creare un messaggio annidato con il campo ripetuto o il set di `oneof` per aggirare questa limitazione.

>[!div class="step-by-step"]
>[Precedente](protobuf-reserved.md)
>[Successivo](protobuf-enums.md)
