---
title: Campi riservati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui campi riservati per la compatibilità tra versioni.
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967304"
---
# <a name="protobuf-reserved-fields"></a>Campi riservati protobuf

Le garanzie di compatibilità con le versioni precedenti di protobuf si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati. Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato. Questa operazione può essere applicata usando la parola chiave `reserved`. Se i campi `displayName` e `marketId` sono stati rimossi dal messaggio `Stock` definito in precedenza, i rispettivi numeri di campo devono essere riservati come nell'esempio seguente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

La parola chiave `reserved` può essere usata anche come segnaposto per i campi che potrebbero essere aggiunti in futuro. I numeri di campo contigui possono essere espressi come un intervallo usando la parola chiave `to`.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Precedente](protobuf-repeated.md)
>[Successivo](protobuf-any-oneof.md)
