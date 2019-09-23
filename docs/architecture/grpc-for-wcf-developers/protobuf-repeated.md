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
# <a name="repeated-fields-for-lists-and-arrays"></a>Campi ripetuti per elenchi e matrici

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Gli elenchi vengono specificati in protobuf usando `repeated` la parola chiave prefix. Nell'esempio seguente viene illustrato come creare un elenco:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Nel codice generato, `repeated` i `Google.Protobuf.Collections.RepeatedField<T>` campi sono rappresentati dal tipo generico anziché da uno qualsiasi dei tipi di raccolta .NET incorporati. Il `RepeatedField<T>` tipo include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario. Implementa tutte le interfacce di raccolta .NET standard, ad <xref:System.Collections.Generic.IList%601> esempio <xref:System.Collections.Generic.IEnumerable%601>e, in modo da poter usare facilmente le query LINQ o convertirle in una matrice o in un elenco.

>[!div class="step-by-step"]
>[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)
