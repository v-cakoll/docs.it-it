---
title: Enumerazioni
description: Informazioni su come usare F# le enumerazioni al posto dei valori letterali per rendere il codice più leggibile e gestibile.
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630346"
---
# <a name="enumerations"></a><span data-ttu-id="1ace5-103">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="1ace5-103">Enumerations</span></span>

<span data-ttu-id="1ace5-104">Le enumerazioni, note anchecome enumerazioni, sono tipi integrali in cui le etichette vengono assegnate a un subset di valori.</span><span class="sxs-lookup"><span data-stu-id="1ace5-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="1ace5-105">È possibile usarle in sostituzione ai valori letterali per rendere il codice più leggibile e gestibile.</span><span class="sxs-lookup"><span data-stu-id="1ace5-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ace5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ace5-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="1ace5-107">Note</span><span class="sxs-lookup"><span data-stu-id="1ace5-107">Remarks</span></span>

<span data-ttu-id="1ace5-108">Un'enumerazione è simile a un'unione discriminata con valori semplici, ad eccezione del fatto che è possibile specificare i valori.</span><span class="sxs-lookup"><span data-stu-id="1ace5-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="1ace5-109">I valori sono in genere numeri interi che iniziano da 0 o 1 oppure numeri interi che rappresentano posizioni di bit.</span><span class="sxs-lookup"><span data-stu-id="1ace5-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="1ace5-110">Se un'enumerazione è progettata per rappresentare posizioni di bit, è necessario utilizzare anche l'attributo [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="1ace5-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="1ace5-111">Il tipo sottostante dell'enumerazione è determinato dal valore letterale usato, in modo che, ad esempio, è possibile usare valori letterali con un suffisso, ad `1u`esempio `2u`, e così via, per un tipo di`uint32`Unsigned Integer ().</span><span class="sxs-lookup"><span data-stu-id="1ace5-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="1ace5-112">Quando si fa riferimento ai valori denominati, è necessario usare il nome del tipo di enumerazione stesso come qualificatore, ovvero `enum-name.value1`, non solo `value1`.</span><span class="sxs-lookup"><span data-stu-id="1ace5-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="1ace5-113">Questo comportamento è diverso da quello delle unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="1ace5-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="1ace5-114">Questo perché le enumerazioni hanno sempre l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) .</span><span class="sxs-lookup"><span data-stu-id="1ace5-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="1ace5-115">Il codice seguente illustra la dichiarazione e l'uso di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1ace5-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="1ace5-116">È possibile convertire facilmente le enumerazioni nel tipo sottostante usando l'operatore appropriato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1ace5-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="1ace5-117">I tipi enumerati possono avere uno dei seguenti tipi sottostanti `sbyte`: `byte` `int16`,, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`.</span><span class="sxs-lookup"><span data-stu-id="1ace5-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="1ace5-118">I tipi di enumerazione sono rappresentati nella .NET Framework come tipi ereditati `System.Enum`da, che a sua volta viene `System.ValueType`ereditato da.</span><span class="sxs-lookup"><span data-stu-id="1ace5-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="1ace5-119">Sono pertanto tipi di valore che si trovano nello stack o inline nell'oggetto contenitore e qualsiasi valore del tipo sottostante è un valore valido dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1ace5-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="1ace5-120">Questa operazione è significativa quando si verificano criteri di ricerca sui valori di enumerazione, perché è necessario fornire un modello che catturi i valori senza nome.</span><span class="sxs-lookup"><span data-stu-id="1ace5-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="1ace5-121">La `enum` funzione nella F# libreria può essere usata per generare un valore di enumerazione, anche un valore diverso da uno dei valori denominati predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1ace5-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="1ace5-122">Usare la `enum` funzione come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1ace5-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="1ace5-123">La funzione `enum` predefinita funziona con il `int32`tipo.</span><span class="sxs-lookup"><span data-stu-id="1ace5-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="1ace5-124">Pertanto, non può essere utilizzato con tipi di enumerazione con altri tipi sottostanti.</span><span class="sxs-lookup"><span data-stu-id="1ace5-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="1ace5-125">Usare invece il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="1ace5-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="1ace5-126">Inoltre, i case per le enumerazioni vengono sempre emessi `public`come.</span><span class="sxs-lookup"><span data-stu-id="1ace5-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="1ace5-127">In questo modo si allineano C# con e il resto della piattaforma .NET.</span><span class="sxs-lookup"><span data-stu-id="1ace5-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ace5-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ace5-128">See also</span></span>

- [<span data-ttu-id="1ace5-129">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1ace5-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="1ace5-130">Cast e conversioni</span><span class="sxs-lookup"><span data-stu-id="1ace5-130">Casting and Conversions</span></span>](casting-and-conversions.md)
