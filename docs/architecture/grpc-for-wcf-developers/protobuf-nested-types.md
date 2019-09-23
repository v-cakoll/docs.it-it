---
title: Tipi annidati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di messaggi annidati in protobuf e gRPC e sul modo in C#cui vengono generati in.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 39bc52b37cc9e57cfe0ed5a5118c348de5f014d8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184190"
---
# <a name="protobuf-nested-types"></a>Tipi annidati protobuf

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Così come C# consente di dichiarare le classi all'interno di altre classi, protobuf consente di annidare le definizioni dei messaggi all'interno di altri messaggi. Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

Nel codice generato C# , il `Inner` tipo verrà dichiarato in una classe statica `Types` annidata all'interno della `HelloRequest` classe:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)
