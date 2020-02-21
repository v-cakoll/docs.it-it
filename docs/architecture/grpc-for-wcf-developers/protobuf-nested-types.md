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
# <a name="protobuf-nested-types"></a><span data-ttu-id="803f6-103">Tipi annidati protobuf</span><span class="sxs-lookup"><span data-stu-id="803f6-103">Protobuf nested types</span></span>

<span data-ttu-id="803f6-104">Così come C# consente di dichiarare le classi all'interno di altre classi, il buffer del protocollo (protobuf) consente di annidare le definizioni dei messaggi all'interno di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="803f6-104">Just as C# allows you to declare classes inside other classes, Protocol Buffer (Protobuf) allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="803f6-105">Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:</span><span class="sxs-lookup"><span data-stu-id="803f6-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="803f6-106">Nel codice generato C# il tipo di `Inner` verrà dichiarato in una classe di `Types` statica annidata all'interno della classe `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="803f6-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="803f6-107">[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="803f6-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
