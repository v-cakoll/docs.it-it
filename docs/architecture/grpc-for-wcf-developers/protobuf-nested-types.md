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
# <a name="protobuf-nested-types"></a><span data-ttu-id="88e35-103">Tipi annidati protobuf</span><span class="sxs-lookup"><span data-stu-id="88e35-103">Protobuf nested types</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="88e35-104">Così come C# consente di dichiarare le classi all'interno di altre classi, protobuf consente di annidare le definizioni dei messaggi all'interno di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="88e35-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="88e35-105">Nell'esempio seguente viene illustrato come creare tipi di messaggi annidati:</span><span class="sxs-lookup"><span data-stu-id="88e35-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="88e35-106">Nel codice generato C# , il `Inner` tipo verrà dichiarato in una classe statica `Types` annidata all'interno della `HelloRequest` classe:</span><span class="sxs-lookup"><span data-stu-id="88e35-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="88e35-107">[Precedente](protobuf-data-types.md)
>[Successivo](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="88e35-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
