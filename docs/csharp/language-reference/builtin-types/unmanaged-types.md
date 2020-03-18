---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 8a4599514115aa21f17c32848ce203fea704072e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846464"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="02072-102">Tipi non gestiti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02072-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="02072-103">Un tipo è un tipo non gestito se è uno dei tipi seguenti:A type is an **unmanaged type** if it's any of the following types:</span><span class="sxs-lookup"><span data-stu-id="02072-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="02072-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="02072-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="02072-105">Qualsiasi tipo [enum](enum.md)</span><span class="sxs-lookup"><span data-stu-id="02072-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="02072-106">Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="02072-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="02072-107">Qualsiasi tipo [struct](struct.md) definito dall'utente che contiene solo campi di tipi non gestiti e, in C .NET 7.3 e versioni precedenti, non è un tipo costruito (un tipo che include almeno un argomento di tipo)</span><span class="sxs-lookup"><span data-stu-id="02072-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="02072-108">A partire dalla versione 7.3 di C, è possibile usare il [ `unmanaged` vincolo](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che un parametro di tipo è un tipo non puntatore e non nullable non gestito.</span><span class="sxs-lookup"><span data-stu-id="02072-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="02072-109">A partire dalla versione 8.0 di C, un tipo struct costruito che contiene solo campi di tipi non gestiti è unmanaged, come illustrato nell'esempio seguente:At beginning with C' 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span><span class="sxs-lookup"><span data-stu-id="02072-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="02072-110">Uno struct generico può essere l'origine di tipi costruiti non gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="02072-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="02072-111">Nell'esempio precedente viene definito `Coords<T>` uno struct generico e vengono presentate gli esempi di tipi costruiti non gestiti.</span><span class="sxs-lookup"><span data-stu-id="02072-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="02072-112">L'esempio di non un `Coords<object>`tipo non gestito è .</span><span class="sxs-lookup"><span data-stu-id="02072-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="02072-113">Non è gestito perché ha i campi `object` del tipo, che non è gestito.</span><span class="sxs-lookup"><span data-stu-id="02072-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="02072-114">Se si desidera che *tutti i* tipi `unmanaged` costruiti siano tipi non gestiti, utilizzare il vincolo nella definizione di uno struct generico:</span><span class="sxs-lookup"><span data-stu-id="02072-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="02072-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="02072-115">C# language specification</span></span>

<span data-ttu-id="02072-116">Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="02072-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02072-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02072-117">See also</span></span>

- [<span data-ttu-id="02072-118">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="02072-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="02072-119">Tipi di puntatore</span><span class="sxs-lookup"><span data-stu-id="02072-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="02072-120">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="02072-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="02072-121">operatore sizeof</span><span class="sxs-lookup"><span data-stu-id="02072-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="02072-122">Operatore stackalloc</span><span class="sxs-lookup"><span data-stu-id="02072-122">stackalloc operator</span></span>](../operators/stackalloc.md)
