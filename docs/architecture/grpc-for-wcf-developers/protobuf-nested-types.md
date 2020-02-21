---
title: Tipi annidati protobuf-gRPC per sviluppatori WCF
description: Informazioni sui tipi di messaggi annidati in protobuf e gRPC e sul modo in C#cui vengono generati in.
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542846"
---
# <a name="protobuf-nested-types"></a>Tipi annidati protobuf

Così come C# consente di dichiarare le classi all'interno di altre classi, il buffer del protocollo (protobuf) consente di annidare le definizioni dei messaggi all'interno di altri messaggi. Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:

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
