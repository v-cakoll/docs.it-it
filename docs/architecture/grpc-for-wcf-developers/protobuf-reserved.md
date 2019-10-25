---
title: Campi riservati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui campi riservati per la compatibilità tra versioni.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846323"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="fb1a1-103">Campi riservati protobuf</span><span class="sxs-lookup"><span data-stu-id="fb1a1-103">Protobuf reserved fields</span></span>

<span data-ttu-id="fb1a1-104">Le garanzie di compatibilità con le versioni precedenti di protobuf si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="fb1a1-105">Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="fb1a1-106">Questa operazione può essere applicata usando la parola chiave `reserved`.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="fb1a1-107">Se i campi `displayName` e `marketId` sono stati rimossi dal messaggio `Stock` definito in precedenza, i rispettivi numeri di campo devono essere riservati come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="fb1a1-108">La parola chiave `reserved` può essere usata anche come segnaposto per i campi che potrebbero essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="fb1a1-109">I numeri di campo contigui possono essere espressi come un intervallo usando la parola chiave `to`.</span><span class="sxs-lookup"><span data-stu-id="fb1a1-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="fb1a1-110">[Precedente](protobuf-repeated.md)
>[Successivo](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="fb1a1-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
