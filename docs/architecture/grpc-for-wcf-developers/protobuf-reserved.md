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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="e01ee-103">Campi riservati protobuf</span><span class="sxs-lookup"><span data-stu-id="e01ee-103">Protobuf reserved fields</span></span>

<span data-ttu-id="e01ee-104">Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (protobuf) si basano sui numeri dei campi che rappresentano sempre lo stesso elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="e01ee-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="e01ee-105">Se un campo viene rimosso da un messaggio in una nuova versione del servizio, il numero di campo non deve mai essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="e01ee-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="e01ee-106">A questo scopo, è possibile usare la parola chiave `reserved`.</span><span class="sxs-lookup"><span data-stu-id="e01ee-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="e01ee-107">Se i campi `displayName` e `marketId` sono stati rimossi dal messaggio `Stock` definito in precedenza, i rispettivi numeri di campo devono essere riservati come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e01ee-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="e01ee-108">È anche possibile usare la parola chiave `reserved` come segnaposto per i campi che potrebbero essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="e01ee-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="e01ee-109">È possibile esprimere i numeri di campo contigui come un intervallo usando la parola chiave `to`.</span><span class="sxs-lookup"><span data-stu-id="e01ee-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="e01ee-110">[Precedente](protobuf-repeated.md)
>[Successivo](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="e01ee-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
