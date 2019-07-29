---
title: Operatore sizeof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 4852e1166a975b1a45c5bd905123a35fc846aa28
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513125"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="15328-102">Operatore sizeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="15328-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="15328-103">L'operatore `sizeof` restituisce il numero di byte occupati da una variabile di un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="15328-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="15328-104">Un argomento dell'operatore `sizeof` deve essere il nome di un [tipo non gestito](../builtin-types/unmanaged-types.md) o un parametro di tipo [vincolato](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) a un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="15328-104">An argument of the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="15328-105">L'operatore `sizeof` richiede un contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="15328-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="15328-106">Tuttavia, per le espressioni presentate nella tabella seguente vengono restituiti i valori costanti corrispondenti in fase di compilazione e non è richiesto un contesto unsafe:</span><span class="sxs-lookup"><span data-stu-id="15328-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="15328-107">Espressione</span><span class="sxs-lookup"><span data-stu-id="15328-107">Expression</span></span>|<span data-ttu-id="15328-108">Valore costante</span><span class="sxs-lookup"><span data-stu-id="15328-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="15328-109">1</span><span class="sxs-lookup"><span data-stu-id="15328-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="15328-110">1</span><span class="sxs-lookup"><span data-stu-id="15328-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="15328-111">2</span><span class="sxs-lookup"><span data-stu-id="15328-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="15328-112">2</span><span class="sxs-lookup"><span data-stu-id="15328-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="15328-113">4</span><span class="sxs-lookup"><span data-stu-id="15328-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="15328-114">4</span><span class="sxs-lookup"><span data-stu-id="15328-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="15328-115">8</span><span class="sxs-lookup"><span data-stu-id="15328-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="15328-116">8</span><span class="sxs-lookup"><span data-stu-id="15328-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="15328-117">2</span><span class="sxs-lookup"><span data-stu-id="15328-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="15328-118">4</span><span class="sxs-lookup"><span data-stu-id="15328-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="15328-119">8</span><span class="sxs-lookup"><span data-stu-id="15328-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="15328-120">16</span><span class="sxs-lookup"><span data-stu-id="15328-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="15328-121">1</span><span class="sxs-lookup"><span data-stu-id="15328-121">1</span></span>|

<span data-ttu-id="15328-122">Non è inoltre necessario usare un contesto unsafe quando l'operando dell'operatore `sizeof` è il nome di un tipo [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="15328-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="15328-123">Nell'esempio seguente viene illustrato l'uso dell'operatore `sizeof`:</span><span class="sxs-lookup"><span data-stu-id="15328-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="15328-124">L'operatore `sizeof` restituisce un numero di byte che verrebbero allocati dal Common Language Runtime in managed memory.</span><span class="sxs-lookup"><span data-stu-id="15328-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="15328-125">Per i tipi [struct](../keywords/struct.md) questo valore include l'eventuale riempimento, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="15328-125">For [struct](../keywords/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="15328-126">Il risultato dell'operatore `sizeof` può essere diverso da quello del metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, che restituisce le dimensioni di un tipo nella memoria *non gestita*.</span><span class="sxs-lookup"><span data-stu-id="15328-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="15328-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="15328-127">C# language specification</span></span>

<span data-ttu-id="15328-128">Per altre informazioni, vedere la sezione [Operatore sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="15328-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15328-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15328-129">See also</span></span>

- [<span data-ttu-id="15328-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="15328-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="15328-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="15328-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="15328-132">Operatori relativi al puntatore</span><span class="sxs-lookup"><span data-stu-id="15328-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="15328-133">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="15328-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="15328-134">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="15328-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
