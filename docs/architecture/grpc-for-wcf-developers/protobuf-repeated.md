---
title: Campi ripetuti per elenchi e matrici - gRPC per gli sviluppatori WCF
description: Comprendere in che modo Protobuf gestisce le raccolte e il modo in cui sono correlate alle raccolte .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147971"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="3be79-103">Campi ripetuti per elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="3be79-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="3be79-104">Gli elenchi vengono specificati nel buffer di protocollo `repeated` (Protobuf) utilizzando la parola chiave prefix.</span><span class="sxs-lookup"><span data-stu-id="3be79-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="3be79-105">Nell'esempio seguente viene illustrato come creare un elenco:The following example shows how to create a list:</span><span class="sxs-lookup"><span data-stu-id="3be79-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="3be79-106">Nel codice generato, `repeated` i campi `Google.Protobuf.Collections.RepeatedField<T>` sono rappresentati dal tipo generico anziché da qualsiasi tipo di raccolta .NET incorporato.</span><span class="sxs-lookup"><span data-stu-id="3be79-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="3be79-107">Il `RepeatedField<T>` tipo include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="3be79-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="3be79-108">Implementa tutte le interfacce di raccolta <xref:System.Collections.Generic.IList%601> .NET standard, ad esempio e <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="3be79-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="3be79-109">È quindi possibile utilizzare query LINQ o convertirle facilmente in una matrice o in un elenco.</span><span class="sxs-lookup"><span data-stu-id="3be79-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3be79-110">[Successivo](protobuf-nested-types.md)
>[precedente](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="3be79-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
