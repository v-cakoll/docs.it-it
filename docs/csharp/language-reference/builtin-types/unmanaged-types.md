---
title: Tipi non gestiti - Riferimenti per C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 81eef59ceb20bcae6c749dd59578ce35da253826
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204480"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="22c26-102">Tipi non gestiti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="22c26-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="22c26-103">Un tipo è un **tipo non gestito** se è uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22c26-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="22c26-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="22c26-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="22c26-105">Qualsiasi tipo [enum](../keywords/enum.md)</span><span class="sxs-lookup"><span data-stu-id="22c26-105">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="22c26-106">Qualsiasi tipo [puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="22c26-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="22c26-107">Qualsiasi tipo [struct](../keywords/struct.md) definito dall'utente che contiene campi solo di tipi non gestiti e, in C# 7,3 e versioni precedenti, non è un tipo costruito (un tipo che include almeno un argomento di tipo)</span><span class="sxs-lookup"><span data-stu-id="22c26-107">Any user-defined [struct](../keywords/struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="22c26-108">A partire C# da 7,3, è possibile usare il [vincolo`unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) per specificare che un parametro di tipo è un tipo non gestito non nullable.</span><span class="sxs-lookup"><span data-stu-id="22c26-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="22c26-109">A partire C# da 8,0, viene anche gestito un tipo struct *costruito* che contiene campi di tipi non gestiti, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="22c26-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="22c26-110">Uno struct generico può essere l'origine dei tipi costruiti non gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="22c26-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="22c26-111">Nell'esempio precedente viene definito uno struct generico `Coords<T>` e vengono presentati gli esempi di tipi costruiti non gestiti.</span><span class="sxs-lookup"><span data-stu-id="22c26-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="22c26-112">L'esempio di non è un tipo non gestito è `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="22c26-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="22c26-113">Non è gestita perché contiene i campi del tipo di `object`, che non è gestito.</span><span class="sxs-lookup"><span data-stu-id="22c26-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="22c26-114">Se si desidera che *tutti i* tipi costruiti siano tipi non gestiti, utilizzare il `unmanaged` vincolo nella definizione di uno struct generico:</span><span class="sxs-lookup"><span data-stu-id="22c26-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="22c26-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="22c26-115">C# language specification</span></span>

<span data-ttu-id="22c26-116">Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="22c26-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22c26-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22c26-117">See also</span></span>

- [<span data-ttu-id="22c26-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="22c26-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="22c26-119">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="22c26-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="22c26-120">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="22c26-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="22c26-121">Operatore sizeof</span><span class="sxs-lookup"><span data-stu-id="22c26-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="22c26-122">Operatore stackalloc</span><span class="sxs-lookup"><span data-stu-id="22c26-122">stackalloc operator</span></span>](../operators/stackalloc.md)
