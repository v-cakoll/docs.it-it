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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="44a49-103">Campi riservati protobuf</span><span class="sxs-lookup"><span data-stu-id="44a49-103">Protobuf reserved fields</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="44a49-104">Le garanzie di compatibilità con le versioni precedenti di protobuf si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="44a49-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="44a49-105">Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="44a49-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="44a49-106">Questa operazione può essere applicata tramite la `reserved` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="44a49-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="44a49-107">Se i `displayName` `marketId`campie sono stati rimossi dal messaggiodefinitoinprecedenza,irispettivinumeridicampodevonoessereriservaticomenell'esempioseguente.`Stock`</span><span class="sxs-lookup"><span data-stu-id="44a49-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="44a49-108">La `reserved` parola chiave può essere usata anche come segnaposto per i campi che potrebbero essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="44a49-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="44a49-109">I numeri di campo contigui possono essere espressi come un `to` intervallo usando la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="44a49-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="44a49-110">[Precedente](protobuf-repeated.md)
>[Successivo](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="44a49-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
