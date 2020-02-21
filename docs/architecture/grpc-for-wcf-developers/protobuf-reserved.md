---
title: Campi riservati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui campi riservati per la compatibilità tra versioni.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542976"
---
# <a name="protobuf-reserved-fields"></a>Campi riservati protobuf

Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (protobuf) si basano sui numeri dei campi che rappresentano sempre lo stesso elemento di dati. Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato. A questo scopo, è possibile usare la parola chiave `reserved`. 

Se i campi `displayName` e `marketId` sono stati rimossi dal messaggio `Stock` definito in precedenza, i rispettivi numeri di campo devono essere riservati come nell'esempio seguente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

È anche possibile usare la parola chiave `reserved` come segnaposto per i campi che potrebbero essere aggiunti in futuro. È possibile esprimere i numeri di campo contigui come un intervallo usando la parola chiave `to`.

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
