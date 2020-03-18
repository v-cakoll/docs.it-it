---
title: Enumerazioni Protobuf - gRPC per gli sviluppatori WCFProtobuf enumerations - gRPC for WCF developers
description: Scopri come dichiarare e usare le enumerazioni in Protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148075"
---
# <a name="protobuf-enumerations"></a>Enumerazioni protobuf

Protobuf supporta i tipi di enumerazione. Questo supporto è stato illustrato nella sezione precedente, in cui `Oneof` è stata utilizzata un'enumerazione per determinare il tipo di un campo. È possibile definire i propri tipi di enumerazione e Protobuf li compilerà in tipi enum c'è.

Poiché è possibile usare Protobuf con vari linguaggi, le convenzioni di denominazione per le enumerazioni sono diverse dalle convenzioni di C. Tuttavia, il generatore di codice converte i nomi nel caso tradizionale di C . Se l'equivalente in caso di maiuscole e minuscole Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.

Ad esempio, nell'enumerazione Protobuf seguente, `ACCOUNT_STATUS`i campi sono preceduti da . Questo prefisso è equivalente al nome `AccountStatus`dell'enumerazione pascal-case, .

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Il generatore consente di creare un'enumerazione di C' equivalente al codice seguente:The generator creates a C' enum equivalent to the following code:

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

Le definizioni di enumerazione Protobuf *devono* avere una costante zero come primo campo. Come in C, è possibile dichiarare più campi con lo stesso valore. Ma è necessario abilitare in `allow_alias` modo esplicito questa opzione utilizzando l'opzione nell'enumerazione:

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

È possibile dichiarare le enumerazioni `.proto` al livello superiore in un file o annidate all'interno di una definizione di messaggio. Le enumerazioni annidate, come i `.Types` messaggi annidati, verranno dichiarate all'interno della classe statica nella classe messaggio generata.

Non è possibile applicare l'attributo [[Flags]](xref:System.FlagsAttribute) a un'enumerazione generata da Protobuf e Protobuf non comprende le combinazioni di enumerazioni bit per bit. Guardate l'esempio seguente:

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

Se si `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`imposta su , viene serializzato `3`come valore intero . Quando un client o un server tenta di deserializzare il valore, `3`non troverà una corrispondenza nella definizione di enumerazione per . Il risultato `Region.None`sarà .

Il modo migliore per lavorare con più valori di enumerazione in Protobuf consiste nell'utilizzare un `repeated` campo del tipo enum.

>[!div class="step-by-step"]
>[Successivo](protobuf-any-oneof.md)
>[precedente](protobuf-maps.md)
