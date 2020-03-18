---
title: Messaggi di protobuf - gRPC per gli sviluppatori WCFProtobuf messages - gRPC for WCF developers
description: Scopri come i messaggi Protobuf vengono definiti nel file IDL e generati in C.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147984"
---
# <a name="protobuf-messages"></a>Messaggi protobuf

In questa sezione viene illustrato come dichiarare i `.proto` messaggi del buffer di protocollo (Protobuf) nei file. Vengono illustrati i concetti fondamentali dei tipi e numeri di campo `protoc` e vengono esaminato il codice c'è generato dal compilatore.

Il resto del capitolo esaminerà più in dettaglio come i diversi tipi di dati sono rappresentati in Protobuf.

## <a name="declaring-a-message"></a>Dichiarazione di un messaggioDeclaring a message

In Windows Communication Foundation `Stock` (WCF), una classe per un'applicazione di trading sul mercato azionario potrebbe essere definita come nell'esempio seguente:In Windows Communication Foundation (WCF), a class for a stock market market trading application might be defined like the following example:

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

Per implementare la classe equivalente in Protobuf, è necessario dichiararla nel `.proto` file. Il `protoc` compilatore genererà quindi la classe .NET come parte del processo di compilazione.

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

La prima riga dichiara la versione della sintassi in uso. La versione 3 della lingua è stata rilasciata nel 2016. È la versione che consigliamo per i servizi gRPC.

La `option csharp_namespace` riga specifica lo spazio dei nomi da utilizzare per i tipi C . Questa opzione verrà ignorata quando il `.proto` file viene compilato per altri linguaggi. I file Protobuf spesso contengono opzioni specifiche della lingua per diverse lingue.

La `Stock` definizione del messaggio specifica quattro campi. Ognuno ha un tipo, un nome e un numero di campo.

## <a name="field-numbers"></a>Numeri di campo

I numeri di campo sono una parte importante di Protobuf. Vengono utilizzati per identificare i campi nei dati codificati binari, il che significa che non possono passare da una versione all'altro del servizio. Il vantaggio è che la compatibilità con le versioni precedenti e la compatibilità in avanti sono possibili. I client e i servizi ignoreranno semplicemente i numeri di campo che non conoscono, a condizione che venga gestita la possibilità di una gestione dei valori mancanti.

Nel formato binario, il numero di campo viene combinato con un identificatore di tipo. I numeri di campo da 1 a 15 possono essere codificati con il tipo come un singolo byte. I numeri da 16 a 2.047 richiedono 2 byte. Si può andare più in alto se avete bisogno di più di 2.047 campi su un messaggio per qualsiasi motivo. Gli identificatori a byte singolo per i numeri di campo da 1 a 15 offrono prestazioni migliori, pertanto è consigliabile utilizzarli per i campi più semplici e utilizzati di frequente.

## <a name="types"></a>Tipi

Le dichiarazioni dei tipi utilizzano i tipi di dati scalari nativi di Protobuf, descritti in modo più dettagliato [nella sezione successiva.](protobuf-data-types.md) Il resto di questo capitolo coprirà i tipi incorporati di Protobuf e mostrerà come sono correlati ai tipi .NET comuni.

> [!NOTE]
> Protobuf non supporta in `decimal` modo nativo `double` un tipo, quindi viene usato. Per le applicazioni che richiedono la precisione decimale completa, fare riferimento alla [sezione sui decimali](protobuf-data-types.md#decimals) nella parte successiva di questo capitolo.

## <a name="the-generated-code"></a>Codice generato

Quando si compila l'applicazione, Protobuf crea classi per ognuno dei messaggi, eseguendo il mapping dei relativi tipi nativi ai tipi C. Il `Stock` tipo generato avrà la firma seguente:The generated type would have the following signature:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Il codice effettivo generato è molto più complicato di questo. Il motivo è che ogni classe contiene tutto il codice necessario per serializzare e deserializzare se stesso nel formato wire binario.

### <a name="property-names"></a>Nomi delle proprietà

Si noti che il `PascalCase` compilatore Protobuf `snake_case` applicato `.proto` ai nomi delle proprietà, anche se erano nel file. La guida di [stile Protobuf](https://developers.google.com/protocol-buffers/docs/style) consiglia di utilizzare `snake_case` nelle definizioni dei messaggi in modo che la generazione di codice per altre piattaforme produca il caso previsto per le convenzioni.

>[!div class="step-by-step"]
>[Successivo](protocol-buffers.md)
>[precedente](protobuf-data-types.md)
