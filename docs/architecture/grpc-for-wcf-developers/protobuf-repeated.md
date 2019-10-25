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
