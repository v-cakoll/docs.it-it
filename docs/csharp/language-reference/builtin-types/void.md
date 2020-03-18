---
title: void - Riferimento in C
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: c6c1c28e3d7a53a1dcadcf50d8d7f42c8c8aeee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846209"
---
# <a name="void-c-reference"></a><span data-ttu-id="8f564-102">void (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="8f564-102">void (C# reference)</span></span>

<span data-ttu-id="8f564-103">Utilizzare `void` come tipo restituito di un [metodo](../../programming-guide/classes-and-structs/methods.md) (o una [funzione locale](../../programming-guide/classes-and-structs/local-functions.md)) per specificare che il metodo non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="8f564-103">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/VoidType.cs#VoidExample)]

<span data-ttu-id="8f564-104">È inoltre `void` possibile utilizzare come tipo referente per dichiarare un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8f564-104">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="8f564-105">Per altre informazioni, vedere [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="8f564-105">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="8f564-106">Non è `void` possibile utilizzare come tipo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="8f564-106">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f564-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f564-107">See also</span></span>

- [<span data-ttu-id="8f564-108">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="8f564-108">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
