---
title: Campi riservati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui campi riservati per la compatibilità tra versioni.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: d4d40ca12d41ec37e0baebf10de9d0690e4297cc
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184176"
---
# <a name="protobuf-reserved-fields"></a>Campi riservati protobuf

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le garanzie di compatibilità con le versioni precedenti di protobuf si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati. Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato. Questa operazione può essere applicata tramite la `reserved` parola chiave. Se i `displayName` `marketId`campie sono stati rimossi dal messaggiodefinitoinprecedenza,irispettivinumeridicampodevonoessereriservaticomenell'esempioseguente.`Stock`

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

La `reserved` parola chiave può essere usata anche come segnaposto per i campi che potrebbero essere aggiunti in futuro. I numeri di campo contigui possono essere espressi come un `to` intervallo usando la parola chiave.

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
