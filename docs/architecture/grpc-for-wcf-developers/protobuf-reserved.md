---
title: Campi riservati protobuf - gRPC per gli sviluppatori WCFProtobuf reserved fields - gRPC for WCF developers
description: Informazioni sui campi riservati per la compatibilità tra versioni diverse.
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147945"
---
# <a name="protobuf-reserved-fields"></a>Campi riservati protobuf

Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (Protobuf) si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati. Se un campo viene rimosso da un messaggio in una nuova versione del servizio, tale numero non deve mai essere riutilizzato. È possibile enfore questo `reserved` utilizzando la parola chiave.

Se `displayName` i `marketId` campi e `Stock` sono stati rimossi dal messaggio definito in precedenza, i relativi numeri di campo devono essere riservati come nell'esempio seguente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

È inoltre possibile `reserved` utilizzare la parola chiave come segnaposto per i campi che potrebbero essere aggiunti in futuro. È possibile esprimere numeri di campo contigui `to` come intervallo utilizzando la parola chiave .

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Successivo](protobuf-repeated.md)
>[precedente](protobuf-any-oneof.md)
