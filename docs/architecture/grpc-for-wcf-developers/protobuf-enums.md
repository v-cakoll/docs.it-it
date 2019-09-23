---
title: Enumerazioni protobuf-gRPC per sviluppatori WCF
description: Informazioni su come dichiarare e usare le enumerazioni in protobuf.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: d93319b713588129a19246976a82bb03a90ce680
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184239"
---
# <a name="protobuf-enumerations"></a>Enumerazioni protobuf

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Protobuf supporta i tipi di enumerazione, come illustrato nella sezione precedente, in cui è stata usata un'enumerazione per determinare `oneof` il tipo di un campo. È possibile definire tipi di enumerazione personalizzati e protobuf li compilerà C# ai tipi enum. Poiché protobuf può essere usato con lingue diverse, le convenzioni di denominazione per le enumerazioni sono C# diverse dalle convenzioni. Tuttavia, il generatore di codice è intelligente e converte i nomi nel caso C# tradizionale. Se l'equivalente del case Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.

Ad esempio, in questa enumerazione protobuf i campi sono preceduti `ACCOUNT_STATUS`da, che equivale al nome enum del case Pascal:. `AccountStatus`

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Il generatore crea quindi un' C# enumerazione equivalente al codice seguente:

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

Le definizioni di enumerazione protobuf **devono** avere una costante zero come primo campo. Come in C#, è possibile dichiarare più campi con lo stesso valore, ma è necessario abilitare in modo esplicito questa opzione `allow_alias` usando l'opzione nell'enumerazione:

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

È possibile dichiarare Enumerazioni al primo livello in un `.proto` file o annidate all'interno di una definizione di messaggio. Le enumerazioni annidate, ad esempio i messaggi annidati, `.Types` verranno dichiarate all'interno della classe statica nella classe Message generata.

Non è possibile applicare l'attributo [[flags]](xref:System.FlagsAttribute) a un'enumerazione generata da protobuf e protobuf non riconosce le combinazioni di enumerazione bit per bit. Esaminare l'esempio seguente:

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region availableIn = 1;
}
```

Se si imposta `product.AvailableIn` su `Region.NorthAmerica | Region.SouthAmerica`, viene serializzato come valore `3`Integer. Quando un client o un server tenta di deserializzare il valore, non troverà una corrispondenza nella definizione di enumerazione per `3` e il risultato `Region.None`sarà.

Il modo migliore per lavorare con più valori enum in protobuf consiste nell'usare un `repeated` campo di tipo enum.

>[!div class="step-by-step"]
>[Precedente](protobuf-any-oneof.md)
>[Successivo](protobuf-maps.md)
