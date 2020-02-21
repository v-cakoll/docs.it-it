---
title: Messaggi di protobuf-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui i messaggi protobuf vengono definiti in IDL C#e generati in.
ms.date: 09/09/2019
ms.openlocfilehash: c7375bafb7572b0eaa0458b0310a0114e3fd078c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543040"
---
# <a name="protobuf-messages"></a>Messaggi protobuf

In questa sezione viene illustrato come dichiarare messaggi del buffer del protocollo (protobuf) nei file di `.proto`. Vengono illustrati i concetti fondamentali relativi ai numeri e ai tipi di campo e viene C# esaminato il codice generato dal compilatore `protoc`. 

Nella parte restante del capitolo verranno esaminati in modo più dettagliato il modo in cui i diversi tipi di dati sono rappresentati in protobuf.

## <a name="declaring-a-message"></a>Dichiarazione di un messaggio

In Windows Communication Foundation (WCF), una classe `Stock` per un'applicazione commerciale del mercato azionario potrebbe essere definita come nell'esempio seguente:

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

Per implementare la classe equivalente in protobuf, è necessario dichiararla nel file di `.proto`. Il compilatore `protoc` genererà la classe .NET come parte del processo di compilazione.

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

Nella prima riga viene dichiarata la versione della sintassi utilizzata. La versione 3 della lingua è stata rilasciata nel 2016. Si tratta della versione consigliata per i servizi gRPC.

La riga di `option csharp_namespace` specifica lo spazio dei nomi da utilizzare per C# i tipi generati. Questa opzione verrà ignorata quando il file di `.proto` viene compilato per altre lingue. I file protobuf spesso contengono opzioni specifiche della lingua per diverse lingue.

Nella definizione del messaggio `Stock` sono specificati quattro campi. Ogni ha un tipo, un nome e un numero di campo.

## <a name="field-numbers"></a>Numeri di campo

I numeri di campo sono una parte importante di protobuf. Vengono usati per identificare i campi nei dati con codifica binaria, che significa che non possono essere modificati dalla versione alla versione del servizio. Il vantaggio è che sono possibili compatibilità con le versioni precedenti e compatibilità con le versioni precedenti. I client e i servizi ignoreranno semplicemente i numeri di campo che non conoscono, purché venga gestita la possibilità di valori mancanti.

Nel formato binario, il numero di campo viene combinato con un identificatore di tipo. I numeri di campo da 1 a 15 possono essere codificati con il relativo tipo come singolo byte. I numeri da 16 a 2.047 accettano 2 byte. Se sono necessari più di 2.047 campi in un messaggio per qualsiasi motivo, è possibile passare a un livello superiore. Gli identificatori a byte singolo per i numeri di campo da 1 a 15 offrono prestazioni migliori, quindi è consigliabile usarli per i campi più semplici e usati di frequente.

## <a name="types"></a>Tipi

Le dichiarazioni di tipo utilizzano i tipi di dati scalari nativi di protobuf, che vengono discussi in modo più dettagliato nella [sezione successiva](protobuf-data-types.md). Nella parte restante di questo capitolo vengono illustrati i tipi incorporati di protobuf e viene illustrato il modo in cui sono correlati ai tipi .NET comuni.

> [!NOTE]
> Protobuf non supporta in modo nativo un tipo di `decimal`, quindi viene invece utilizzato `double`. Per le applicazioni che richiedono una precisione decimale completa, fare riferimento alla [sezione relativa ai numeri decimali](protobuf-data-types.md#decimals) nella parte successiva di questo capitolo.

## <a name="the-generated-code"></a>Codice generato

Quando si compila l'applicazione, protobuf crea le classi per ogni messaggio, eseguendo il mapping dei tipi nativi C# ai tipi. Il tipo di `Stock` generato avrà la firma seguente:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Il codice effettivo generato è molto più complicato di questo. Il motivo è che ogni classe contiene tutto il codice necessario per la serializzazione e la deserializzazione nel formato wire binario.

### <a name="property-names"></a>Nomi delle proprietà

Si noti che il compilatore protobuf applicato `PascalCase` ai nomi delle proprietà, anche se sono stati `snake_case` nel file `.proto`. La [Guida di stile protobuf](https://developers.google.com/protocol-buffers/docs/style) consiglia di usare `snake_case` nelle definizioni dei messaggi in modo che la generazione di codice per altre piattaforme produca il caso previsto per le convenzioni.

>[!div class="step-by-step"]
>[Precedente](protocol-buffers.md)
>[Successivo](protobuf-data-types.md)
