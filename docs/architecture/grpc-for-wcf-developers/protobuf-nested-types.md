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
# <a name="protobuf-nested-types"></a><span data-ttu-id="e6bf4-103">Tipi annidati protobuf</span><span class="sxs-lookup"><span data-stu-id="e6bf4-103">Protobuf nested types</span></span>

<span data-ttu-id="e6bf4-104">Così come C# consente di dichiarare le classi all'interno di altre classi, protobuf consente di annidare le definizioni dei messaggi all'interno di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="e6bf4-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="e6bf4-105">Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:</span><span class="sxs-lookup"><span data-stu-id="e6bf4-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="e6bf4-106">Nel codice generato C# il tipo di `Inner` verrà dichiarato in una classe di `Types` statica annidata all'interno della classe `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="e6bf4-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="e6bf4-107">[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="e6bf4-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
