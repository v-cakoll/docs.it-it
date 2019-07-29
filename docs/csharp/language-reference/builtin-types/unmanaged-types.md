---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512067"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="21e94-102">Tipi non gestiti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="21e94-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="21e94-103">Un **tipo non gestito** è un tipo che non è un tipo riferimento o un tipo costruito (un tipo che include almeno un argomento di tipo) e che non contiene campi di tipo riferimento o di tipo costruito a qualsiasi livello di annidamento.</span><span class="sxs-lookup"><span data-stu-id="21e94-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="21e94-104">In altre parole, un tipo non gestito è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="21e94-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="21e94-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="21e94-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="21e94-106">Qualsiasi tipo [enum](../keywords/enum.md)</span><span class="sxs-lookup"><span data-stu-id="21e94-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="21e94-107">Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="21e94-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="21e94-108">Qualsiasi tipo [struct](../keywords/struct.md) definito dall'utente che non sia un tipo costruito e che contenga campi solo di tipi non gestiti</span><span class="sxs-lookup"><span data-stu-id="21e94-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="21e94-109">A partire da C# 7.3, è possibile usare il [vincolo `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che il parametro di tipo deve essere un tipo non gestito non puntatore.</span><span class="sxs-lookup"><span data-stu-id="21e94-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="21e94-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="21e94-110">C# language specification</span></span>

<span data-ttu-id="21e94-111">Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="21e94-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21e94-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e94-112">See also</span></span>

- [<span data-ttu-id="21e94-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="21e94-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="21e94-114">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="21e94-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="21e94-115">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="21e94-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="21e94-116">Operatore sizeof</span><span class="sxs-lookup"><span data-stu-id="21e94-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="21e94-117">Operatore stackalloc</span><span class="sxs-lookup"><span data-stu-id="21e94-117">stackalloc operator</span></span>](../operators/stackalloc.md)
