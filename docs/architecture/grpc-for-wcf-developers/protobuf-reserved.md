---
title: Campi riservati protobuf - gRPC per gli sviluppatori WCFProtobuf reserved fields - gRPC for WCF developers
description: Informazioni sui campi riservati per la compatibilità tra versioni diverse.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111036"
---
# <a name="protobuf-reserved-fields"></a>Campi riservati protobuf

Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (Protobuf) si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati. Se un campo viene rimosso da un messaggio in una nuova versione del servizio, tale numero non deve mai essere riutilizzato. È possibile applicare questo `reserved` utilizzando la parola chiave.

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
