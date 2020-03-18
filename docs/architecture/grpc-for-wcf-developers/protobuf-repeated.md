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
# <a name="repeated-fields-for-lists-and-arrays"></a>Campi ripetuti per elenchi e matrici

Gli elenchi vengono specificati nel buffer di protocollo `repeated` (Protobuf) utilizzando la parola chiave prefix. Nell'esempio seguente viene illustrato come creare un elenco:The following example shows how to create a list:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Nel codice generato, `repeated` i campi `Google.Protobuf.Collections.RepeatedField<T>` sono rappresentati dal tipo generico anziché da qualsiasi tipo di raccolta .NET incorporato.

Il `RepeatedField<T>` tipo include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario. Implementa tutte le interfacce di raccolta <xref:System.Collections.Generic.IList%601> .NET standard, ad esempio e <xref:System.Collections.Generic.IEnumerable%601>. È quindi possibile utilizzare query LINQ o convertirle facilmente in una matrice o in un elenco.

>[!div class="step-by-step"]
>[Successivo](protobuf-nested-types.md)
>[precedente](protobuf-reserved.md)
