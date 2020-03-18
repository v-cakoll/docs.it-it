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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="bc974-103">Campi riservati protobuf</span><span class="sxs-lookup"><span data-stu-id="bc974-103">Protobuf reserved fields</span></span>

<span data-ttu-id="bc974-104">Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (Protobuf) si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="bc974-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="bc974-105">Se un campo viene rimosso da un messaggio in una nuova versione del servizio, tale numero non deve mai essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="bc974-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="bc974-106">È possibile enfore questo `reserved` utilizzando la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="bc974-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="bc974-107">Se `displayName` i `marketId` campi e `Stock` sono stati rimossi dal messaggio definito in precedenza, i relativi numeri di campo devono essere riservati come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bc974-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="bc974-108">È inoltre possibile `reserved` utilizzare la parola chiave come segnaposto per i campi che potrebbero essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="bc974-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="bc974-109">È possibile esprimere numeri di campo contigui `to` come intervallo utilizzando la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="bc974-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="bc974-110">[Successivo](protobuf-repeated.md)
>[precedente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="bc974-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
