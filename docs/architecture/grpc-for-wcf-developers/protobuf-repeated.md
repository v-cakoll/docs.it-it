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
# <a name="repeated-fields-for-lists-and-arrays"></a>Campi ripetuti per elenchi e matrici

Per specificare gli elenchi nel buffer del protocollo (protobuf), usare la parola chiave `repeated` prefix. Nell'esempio seguente viene illustrato come creare un elenco:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Nel codice generato i campi `repeated` sono rappresentati dal tipo generico `Google.Protobuf.Collections.RepeatedField<T>` invece che da uno qualsiasi dei tipi di raccolta .NET incorporati. 

Il tipo di `RepeatedField<T>` include il codice necessario per serializzare e deserializzare l'elenco nel formato wire binario. Implementa tutte le interfacce di raccolta .NET standard, ad esempio <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IEnumerable%601>. Quindi, è possibile usare le query LINQ o convertirle in una matrice o in un elenco con facilità.

>[!div class="step-by-step"]
>[Precedente](protobuf-nested-types.md)
>[Successivo](protobuf-reserved.md)
