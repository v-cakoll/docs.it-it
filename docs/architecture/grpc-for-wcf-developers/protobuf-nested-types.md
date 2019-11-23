---
title: Tipi annidati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di messaggi annidati in protobuf e gRPC e sul modo in C#cui vengono generati in.
ms.date: 09/09/2019
ms.openlocfilehash: bbc7ed41516d29f867bbc9da5b258f6a3c9ff261
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967392"
---
# <a name="protobuf-nested-types"></a>Tipi annidati protobuf

Così come C# consente di dichiarare le classi all'interno di altre classi, protobuf consente di annidare le definizioni dei messaggi all'interno di altri messaggi. Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

Nel codice generato C# il tipo di `Inner` verrà dichiarato in una classe di `Types` statica annidata all'interno della classe `HelloRequest`:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)
