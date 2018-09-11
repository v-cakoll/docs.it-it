---
title: Enumerazioni (F#)
description: 'Informazioni su come utilizzare F # enumerazioni anziché valori letterali per rendere il codice più leggibile e gestibile.'
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44369069"
---
# <a name="enumerations"></a><span data-ttu-id="b9835-103">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b9835-103">Enumerations</span></span>

<span data-ttu-id="b9835-104">*Le enumerazioni*, noto anche come *enumerazioni*, sono tipi integrali, in cui le etichette vengono assegnate a un sottoinsieme dei valori.</span><span class="sxs-lookup"><span data-stu-id="b9835-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="b9835-105">È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.</span><span class="sxs-lookup"><span data-stu-id="b9835-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9835-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9835-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="b9835-107">Note</span><span class="sxs-lookup"><span data-stu-id="b9835-107">Remarks</span></span>

<span data-ttu-id="b9835-108">Un'enumerazione sembra molto simile a un'unione discriminata che dispone di valori semplici, ad eccezione del fatto che i valori possono essere specificati.</span><span class="sxs-lookup"><span data-stu-id="b9835-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="b9835-109">In genere, i valori sono numeri interi che iniziano da 0 o 1, o numeri interi che rappresentano posizioni di bit.</span><span class="sxs-lookup"><span data-stu-id="b9835-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="b9835-110">Se un'enumerazione deve rappresentare posizioni dei bit, è anche consigliabile usare la [flag](xref:System.FlagsAttribute) attributo.</span><span class="sxs-lookup"><span data-stu-id="b9835-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="b9835-111">Il tipo sottostante dell'enumerazione è determinato dal valore letterale che viene usato, in modo che, ad esempio, è possibile usare valori letterali con un suffisso, ad esempio `1u`, `2u`e così via, per un intero senza segno (`uint32`) tipo.</span><span class="sxs-lookup"><span data-stu-id="b9835-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="b9835-112">Quando si fa riferimento ai valori denominati, è necessario usare il nome del tipo di enumerazione se stesso come un qualificatore, vale a dire `enum-name.value1`e non semplicemente `value1`.</span><span class="sxs-lookup"><span data-stu-id="b9835-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="b9835-113">Questo comportamento è diverso da quello delle unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="b9835-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="b9835-114">Questo avviene perché le enumerazioni avere sempre la [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo.</span><span class="sxs-lookup"><span data-stu-id="b9835-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="b9835-115">Il codice seguente illustra la dichiarazione e l'uso di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b9835-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="b9835-116">È possibile convertire facilmente enumerazioni per il tipo sottostante utilizzando l'operatore appropriato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9835-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="b9835-117">I tipi enumerati possono avere uno dei seguenti tipi sottostanti: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`.</span><span class="sxs-lookup"><span data-stu-id="b9835-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="b9835-118">I tipi di enumerazione sono rappresentati in .NET Framework come tipi dalla quale vengono ereditati `System.Enum`, che a sua volta viene ereditata dalla `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="b9835-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="b9835-119">In questo modo, si tratta di tipi di valore che si trovano nello stack o inline nell'oggetto che contiene e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b9835-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="b9835-120">Ciò è importante quando i valori di criteri di ricerca su enumerazione, in quanto è necessario specificare un modello che memorizza nella cache i valori senza nome.</span><span class="sxs-lookup"><span data-stu-id="b9835-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="b9835-121">Il `enum` funzione nella libreria di F # può essere utilizzata per generare un valore di enumerazione, anche un valore diverso da quello dell'oggetto predefinito, valori denominati.</span><span class="sxs-lookup"><span data-stu-id="b9835-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="b9835-122">Si utilizza il `enum` funzione come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b9835-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="b9835-123">Il valore predefinito `enum` funzionamento della funzione con tipo `int32`.</span><span class="sxs-lookup"><span data-stu-id="b9835-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="b9835-124">Pertanto, non è utilizzabile con i tipi di enumerazione con altri tipi sottostante.</span><span class="sxs-lookup"><span data-stu-id="b9835-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="b9835-125">In alternativa, usare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="b9835-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="b9835-126">I casi, inoltre, per le enumerazioni vengono sempre generate come `public`.</span><span class="sxs-lookup"><span data-stu-id="b9835-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="b9835-127">Si tratta in modo da poter essere allineate con c# e il resto della piattaforma .NET.</span><span class="sxs-lookup"><span data-stu-id="b9835-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9835-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9835-128">See also</span></span>

- [<span data-ttu-id="b9835-129">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="b9835-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b9835-130">Cast e conversioni</span><span class="sxs-lookup"><span data-stu-id="b9835-130">Casting and Conversions</span></span>](casting-and-conversions.md)
