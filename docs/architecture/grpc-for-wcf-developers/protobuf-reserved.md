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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="74daa-103">Campi riservati protobuf</span><span class="sxs-lookup"><span data-stu-id="74daa-103">Protobuf reserved fields</span></span>

<span data-ttu-id="74daa-104">Le garanzie di compatibilità con le versioni precedenti nel buffer del protocollo (Protobuf) si basano sui numeri di campo che rappresentano sempre lo stesso elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="74daa-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="74daa-105">Se un campo viene rimosso da un messaggio in una nuova versione del servizio, tale numero non deve mai essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="74daa-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="74daa-106">È possibile applicare questo `reserved` utilizzando la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="74daa-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="74daa-107">Se `displayName` i `marketId` campi e `Stock` sono stati rimossi dal messaggio definito in precedenza, i relativi numeri di campo devono essere riservati come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="74daa-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="74daa-108">È inoltre possibile `reserved` utilizzare la parola chiave come segnaposto per i campi che potrebbero essere aggiunti in futuro.</span><span class="sxs-lookup"><span data-stu-id="74daa-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="74daa-109">È possibile esprimere numeri di campo contigui `to` come intervallo utilizzando la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="74daa-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="74daa-110">[Successivo](protobuf-repeated.md)
>[precedente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="74daa-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
