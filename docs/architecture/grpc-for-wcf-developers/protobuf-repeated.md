---
title: Campi ripetuti per elenchi e matrici-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui le raccolte vengono gestite da protobuf e sulla relativa correlazione con le raccolte .NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846321"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="a5a3d-103">Campi ripetuti per elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="a5a3d-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="a5a3d-104">Gli elenchi vengono specificati in protobuf usando la parola chiave `repeated` prefix.</span><span class="sxs-lookup"><span data-stu-id="a5a3d-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="a5a3d-105">Nell'esempio seguente viene illustrato come creare un elenco:</span><span class="sxs-lookup"><span data-stu-id="a5a3d-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="a5a3d-106">Nel codice generato i campi `repeated` sono rappresentati dal tipo generico `Google.Protobuf.Collections.RepeatedField<T>` invece che da uno qualsiasi dei tipi di raccolta .NET incorporati.</span><span class="sxs-lookup"><span data-stu-id="a5a3d-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="a5a3d-107">Il tipo di `RepeatedField<T>` include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="a5a3d-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="a5a3d-108">Implementa tutte le interfacce di raccolta .NET standard, ad esempio <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IEnumerable%601>, in modo da poter usare facilmente le query LINQ o convertirle in una matrice o in un elenco.</span><span class="sxs-lookup"><span data-stu-id="a5a3d-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a5a3d-109">[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="a5a3d-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
