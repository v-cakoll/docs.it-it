---
title: Campi ripetuti per elenchi e matrici-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui le raccolte vengono gestite da protobuf e sulla relativa correlazione con le raccolte .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967362"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Campi ripetuti per elenchi e matrici

Gli elenchi vengono specificati in protobuf usando la parola chiave `repeated` prefix. Nell'esempio seguente viene illustrato come creare un elenco:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Nel codice generato i campi `repeated` sono rappresentati dal tipo generico `Google.Protobuf.Collections.RepeatedField<T>` invece che da uno qualsiasi dei tipi di raccolta .NET incorporati. Il tipo di `RepeatedField<T>` include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario. Implementa tutte le interfacce di raccolta .NET standard, ad esempio <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IEnumerable%601>, in modo da poter usare facilmente le query LINQ o convertirle in una matrice o in un elenco.

>[!div class="step-by-step"]
>[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)
