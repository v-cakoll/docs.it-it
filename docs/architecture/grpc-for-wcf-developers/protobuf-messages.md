---
title: Messaggi di protobuf-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui i messaggi protobuf vengono definiti in IDL C#e generati in.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f6bb67fe3bc37fcb49c0e69b7960a00d584307b8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184204"
---
# <a name="protobuf-messages"></a>Messaggi protobuf

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In questa sezione viene illustrato come dichiarare i messaggi `.proto` protobuf nei file, vengono illustrati i concetti fondamentali relativi ai numeri e ai tipi C# di campo e `protoc` viene analizzato il codice generato dal compilatore. Nella parte restante del capitolo verranno esaminati in modo più dettagliato il modo in cui i diversi tipi di dati sono rappresentati in protobuf.

## <a name="declaring-a-message"></a>Dichiarazione di un messaggio

In WCF è possibile `Stock` definire una classe per un'applicazione commerciale del mercato azionario come nell'esempio seguente:

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

Per implementare la classe equivalente in protobuf, deve essere dichiarata nel `.proto` file. Il `protoc` compilatore genererà la classe .NET come parte del processo di compilazione.

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string displayName = 3;
    int32 marketId = 4;

}  
```

Nella prima riga viene dichiarata la versione della sintassi utilizzata. La versione 3 della lingua è stata rilasciata nel 2016 ed è la versione consigliata per i servizi gRPC.

La `option csharp_namespace` riga specifica lo spazio dei nomi da utilizzare per i C# tipi generati. Questa opzione verrà ignorata quando il `.proto` file viene compilato per altre lingue. È comune che i file protobuf contengano opzioni specifiche della lingua per diverse lingue.

Nella `Stock` definizione del messaggio sono specificati quattro campi, ognuno con un tipo, un nome e un numero di campo.

## <a name="field-numbers"></a>Numeri di campo

I numeri di campo sono una parte importante di protobuf. Vengono usati per identificare i campi nei dati con codifica binaria, che significa che non possono essere modificati dalla versione alla versione del servizio. Il vantaggio è che è possibile la compatibilità con le versioni precedenti e precedenti. I client e i servizi ignoreranno semplicemente i numeri di campo che non conoscono, purché venga gestita la possibilità di valori mancanti.

Nel formato binario, il numero di campo viene combinato con un identificatore di tipo. I numeri di campo da 1 a 15 possono essere codificati con il relativo tipo come singolo byte; i numeri da 16 a 2047 accettano 2 byte. Se sono necessari più di 2047 campi in un messaggio per qualsiasi motivo, è possibile passare a un livello superiore. Gli identificatori a byte singolo per i numeri di campo da 1 a 15 offrono prestazioni migliori, quindi è consigliabile usarli per i campi più semplici e usati di frequente.

## <a name="types"></a>Tipi

Le dichiarazioni di tipo utilizzano i tipi di dati scalari nativi di protobuf, che vengono discussi in modo più dettagliato nella [sezione successiva](protobuf-data-types.md). Nella parte restante di questo capitolo vengono illustrati i tipi incorporati di protobuf e viene illustrato il modo in cui sono correlati ai tipi .NET comuni.

> [!NOTE]
> Protobuf non supporta in modo nativo `decimal` un tipo, quindi viene usato Double. Per le applicazioni che richiedono una precisione decimale completa, fare riferimento alla [sezione relativa ai numeri decimali](protobuf-data-types.md#decimals) nella parte successiva di questo capitolo.

## <a name="the-generated-code"></a>Codice generato

Quando si compila l'applicazione, protobuf crea le classi per ogni messaggio, eseguendo il mapping dei tipi nativi C# ai tipi. Il tipo `Stock` generato avrà la firma seguente:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

Il codice effettivo generato è molto più complicato di questo, perché ogni classe contiene tutto il codice necessario per serializzare e deserializzare nel formato wire binario.

### <a name="property-names"></a>Nomi delle proprietà

Si noti che il compilatore protobuf `PascalCase` è stato applicato ai nomi delle proprietà `camelCase` anche se `.proto` sono presenti nel file. È preferibile usare `camelCase` nella definizione del messaggio in modo che la generazione di codice per altre piattaforme produca il caso previsto per le convenzioni.

>[!div class="step-by-step"]
>[Precedente](protocol-buffers.md)
>[Successivo](protobuf-data-types.md)
