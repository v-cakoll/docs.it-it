---
title: Tipi annidati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di messaggi annidati in protobuf e gRPC e sul modo in C#cui vengono generati in.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846309"
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

Nel codice generato C# il tipo di`Inner`verrà dichiarato in una classe di`Types`statica annidata all'interno della classe`HelloRequest`:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)
