---
title: Campi ripetuti per elenchi e matrici-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui protobuf gestisce le raccolte e le relative correlazioni con le raccolte .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542959"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="100c3-103">Campi ripetuti per elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="100c3-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="100c3-104">Per specificare gli elenchi nel buffer del protocollo (protobuf), usare la parola chiave `repeated` prefix.</span><span class="sxs-lookup"><span data-stu-id="100c3-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="100c3-105">Nell'esempio seguente viene illustrato come creare un elenco:</span><span class="sxs-lookup"><span data-stu-id="100c3-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="100c3-106">Nel codice generato i campi `repeated` sono rappresentati dal tipo generico `Google.Protobuf.Collections.RepeatedField<T>` invece che da uno qualsiasi dei tipi di raccolta .NET incorporati.</span><span class="sxs-lookup"><span data-stu-id="100c3-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="100c3-107">Il tipo di `RepeatedField<T>` include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="100c3-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="100c3-108">Implementa tutte le interfacce di raccolta .NET standard, ad esempio <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="100c3-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="100c3-109">Quindi, è possibile usare le query LINQ o convertirle in una matrice o in un elenco con facilità.</span><span class="sxs-lookup"><span data-stu-id="100c3-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="100c3-110">[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="100c3-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
