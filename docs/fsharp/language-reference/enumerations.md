---
title: Enumerazioni (F#)
description: "Informazioni su come utilizzare le enumerazioni di F # al posto di valori letterali per rendere il codice più leggibile e conservabile."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9272bf5a-9a9f-4314-9e34-a3248e5244f5
ms.openlocfilehash: de0273900b707c99e6fb1bcc84e5c2b9ef2bc725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="enumerations"></a><span data-ttu-id="72f82-104">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="72f82-104">Enumerations</span></span>

<span data-ttu-id="72f82-105">*Enumerazioni*, nota anche come *enumerazioni*, sono tipi integrali in cui le etichette vengono assegnate a un sottoinsieme dei valori.</span><span class="sxs-lookup"><span data-stu-id="72f82-105">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="72f82-106">È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.</span><span class="sxs-lookup"><span data-stu-id="72f82-106">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="72f82-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72f82-107">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="72f82-108">Note</span><span class="sxs-lookup"><span data-stu-id="72f82-108">Remarks</span></span>
<span data-ttu-id="72f82-109">Un'enumerazione è molto simile a un'unione discriminata che dispone di valori semplici, ad eccezione del fatto che i valori possono essere specificati.</span><span class="sxs-lookup"><span data-stu-id="72f82-109">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="72f82-110">In genere, i valori sono valori interi che iniziano da 0 o 1, o numeri interi che rappresentano posizioni dei bit.</span><span class="sxs-lookup"><span data-stu-id="72f82-110">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="72f82-111">Se un'enumerazione è progettata per rappresentare le posizioni di bit, è necessario utilizzare anche il [flag](xref:System.FlagsAttribute) attributo.</span><span class="sxs-lookup"><span data-stu-id="72f82-111">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="72f82-112">Il tipo sottostante dell'enumerazione è determinato dal valore letterale che viene utilizzato, in modo che, ad esempio, è possibile utilizzare valori letterali con un suffisso, ad esempio `1u`, `2u`e così via, per un intero senza segno (`uint32`) tipo.</span><span class="sxs-lookup"><span data-stu-id="72f82-112">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="72f82-113">Quando si fa riferimento ai valori denominati, è necessario utilizzare il nome del tipo di enumerazione stesso come un qualificatore, vale a dire `enum-name.value1`, non solo `value1`.</span><span class="sxs-lookup"><span data-stu-id="72f82-113">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="72f82-114">Questo comportamento è diverso da quello delle unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="72f82-114">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="72f82-115">Infatti, le enumerazioni dispongono sempre di [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo.</span><span class="sxs-lookup"><span data-stu-id="72f82-115">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="72f82-116">Il codice seguente illustra la dichiarazione e utilizzo di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="72f82-116">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="72f82-117">È possibile convertire facilmente enumerazioni per il tipo sottostante utilizzando l'operatore appropriato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="72f82-117">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="72f82-118">Tipi enumerati possono avere uno dei seguenti tipi sottostanti: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`.</span><span class="sxs-lookup"><span data-stu-id="72f82-118">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="72f82-119">Tipi di enumerazione sono rappresentati in .NET Framework come tipi ereditati da `System.Enum`, che a sua volta viene ereditata dalla `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="72f82-119">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="72f82-120">Di conseguenza, sono tipi di valore che si trovano nello stack o inline nell'oggetto contenitore e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="72f82-120">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="72f82-121">Questo è importante quando i valori di criteri di ricerca in una enumerazione, in quanto è necessario specificare un modello che memorizza nella cache i valori senza nome.</span><span class="sxs-lookup"><span data-stu-id="72f82-121">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="72f82-122">Il `enum` funzione nella libreria F # può essere utilizzata per generare un valore di enumerazione, anche un valore diverso da uno degli operatori, valori denominati.</span><span class="sxs-lookup"><span data-stu-id="72f82-122">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="72f82-123">Utilizzare il `enum` funzione come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="72f82-123">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="72f82-124">Il valore predefinito `enum` funzione funziona con tipo `int32`.</span><span class="sxs-lookup"><span data-stu-id="72f82-124">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="72f82-125">Non può pertanto essere utilizzato con tipi di enumerazione che dispongono di altri tipi sottostanti.</span><span class="sxs-lookup"><span data-stu-id="72f82-125">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="72f82-126">Utilizzare invece le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="72f82-126">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="72f82-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f82-127">See Also</span></span>
[<span data-ttu-id="72f82-128">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="72f82-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="72f82-129">Cast e conversioni</span><span class="sxs-lookup"><span data-stu-id="72f82-129">Casting and Conversions</span></span>](casting-and-conversions.md)
