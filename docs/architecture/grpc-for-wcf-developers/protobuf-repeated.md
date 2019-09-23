---
title: Campi ripetuti per elenchi e matrici-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui le raccolte vengono gestite da protobuf e sulla relativa correlazione con le raccolte .NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ad06551bf3eaec795865af227815b78c9601d0db
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184183"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="56190-103">Campi ripetuti per elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="56190-103">Repeated fields for lists and arrays</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="56190-104">Gli elenchi vengono specificati in protobuf usando `repeated` la parola chiave prefix.</span><span class="sxs-lookup"><span data-stu-id="56190-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="56190-105">Nell'esempio seguente viene illustrato come creare un elenco:</span><span class="sxs-lookup"><span data-stu-id="56190-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="56190-106">Nel codice generato, `repeated` i `Google.Protobuf.Collections.RepeatedField<T>` campi sono rappresentati dal tipo generico anziché da uno qualsiasi dei tipi di raccolta .NET incorporati.</span><span class="sxs-lookup"><span data-stu-id="56190-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="56190-107">Il `RepeatedField<T>` tipo include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="56190-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="56190-108">Implementa tutte le interfacce di raccolta .NET standard, ad <xref:System.Collections.Generic.IList%601> esempio <xref:System.Collections.Generic.IEnumerable%601>e, in modo da poter usare facilmente le query LINQ o convertirle in una matrice o in un elenco.</span><span class="sxs-lookup"><span data-stu-id="56190-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="56190-109">[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="56190-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
