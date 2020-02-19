---
title: Tipi di enumerazione C# -riferimento
description: Informazioni sui C# tipi di enumerazione che rappresentano una scelta o una combinazione di scelte
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 4377d113a18d23c8a0f9a669e6112f1a8223cc79
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450869"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="51e73-103">Tipi di enumerazioneC# (riferimento)</span><span class="sxs-lookup"><span data-stu-id="51e73-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="51e73-104">Un tipo di *enumerazione* o un tipo *enum*è un [tipo di valore](value-types.md) definito da un set di costanti denominate del tipo [numerico integrale](integral-numeric-types.md) sottostante.</span><span class="sxs-lookup"><span data-stu-id="51e73-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="51e73-105">Per definire un tipo di enumerazione, usare la parola chiave `enum` e specificare i nomi dei *membri enum*:</span><span class="sxs-lookup"><span data-stu-id="51e73-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="51e73-106">Per impostazione predefinita, i valori costanti associati dei membri enum sono di tipo `int`; iniziano con zero e aumentano di uno dopo l'ordine di testo della definizione.</span><span class="sxs-lookup"><span data-stu-id="51e73-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="51e73-107">È possibile specificare in modo esplicito qualsiasi altro tipo [numerico integrale](integral-numeric-types.md) come tipo sottostante di un tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e73-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="51e73-108">È anche possibile specificare in modo esplicito i valori costanti associati, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="51e73-108">You also can explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="51e73-109">Non è possibile definire un metodo all'interno della definizione di un tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e73-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="51e73-110">Per aggiungere funzionalità a un tipo di enumerazione, creare un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="51e73-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="51e73-111">Il valore predefinito di un tipo di enumerazione `E` è il valore prodotto dall'espressione `(E)0`, anche se zero non ha il membro enum corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51e73-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="51e73-112">Usare un tipo di enumerazione per rappresentare una scelta da un set di valori che si escludono a vicenda o da una combinazione di opzioni.</span><span class="sxs-lookup"><span data-stu-id="51e73-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="51e73-113">Per rappresentare una combinazione di scelte, definire un tipo di enumerazione come flag di bit.</span><span class="sxs-lookup"><span data-stu-id="51e73-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="51e73-114">Tipi di enumerazione come flag di bit</span><span class="sxs-lookup"><span data-stu-id="51e73-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="51e73-115">Se si vuole che un tipo di enumerazione rappresenti una combinazione di scelte, definire i membri enum per tali scelte in modo che una singola scelta sia un campo di bit.</span><span class="sxs-lookup"><span data-stu-id="51e73-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="51e73-116">Ovvero i valori associati di tali membri enum dovrebbero essere le potenze di due.</span><span class="sxs-lookup"><span data-stu-id="51e73-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="51e73-117">Quindi, è possibile usare gli [operatori logici bit per bit `|` o `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) per combinare le scelte o le combinazioni di opzioni intersecate rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="51e73-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="51e73-118">Per indicare che un tipo di enumerazione dichiara campi di bit, applicarvi l'attributo [Flags](xref:System.FlagsAttribute) .</span><span class="sxs-lookup"><span data-stu-id="51e73-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="51e73-119">Come illustrato nell'esempio seguente, è anche possibile includere alcune combinazioni tipiche nella definizione di un tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e73-119">As the following example shows, you also can include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Flags)]

<span data-ttu-id="51e73-120">Per ulteriori informazioni ed esempi, vedere la pagina di riferimento dell'API <xref:System.FlagsAttribute?displayProperty=nameWithType> e i [membri non esclusivi e la sezione attributo Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) della pagina di riferimento all'API <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51e73-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="51e73-121">Il tipo System. Enum e il vincolo enum</span><span class="sxs-lookup"><span data-stu-id="51e73-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="51e73-122">Il tipo di <xref:System.Enum?displayProperty=nameWithType> è la classe di base astratta di tutti i tipi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e73-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="51e73-123">Sono disponibili diversi metodi per ottenere informazioni su un tipo di enumerazione e i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="51e73-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="51e73-124">Per ulteriori informazioni ed esempi, vedere la pagina di riferimento dell'API <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51e73-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="51e73-125">A partire C# da 7,3, è possibile usare `System.Enum` in un vincolo della classe di base (noto come [vincolo enum](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) per specificare che un parametro di tipo è un tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51e73-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="51e73-126">Conversioni</span><span class="sxs-lookup"><span data-stu-id="51e73-126">Conversions</span></span>

<span data-ttu-id="51e73-127">Per qualsiasi tipo di enumerazione esistono conversioni esplicite tra il tipo di enumerazione e il tipo integrale sottostante.</span><span class="sxs-lookup"><span data-stu-id="51e73-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="51e73-128">Se si [esegue il cast](../operators/type-testing-and-cast.md#cast-operator-) di un valore enum al relativo tipo sottostante, il risultato è il valore integrale associato di un membro enum.</span><span class="sxs-lookup"><span data-stu-id="51e73-128">If you [cast](../operators/type-testing-and-cast.md#cast-operator-) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Conversions)]

<span data-ttu-id="51e73-129">Utilizzare il metodo <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per determinare se un tipo di enumerazione contiene un membro enum con il determinato valore associato.</span><span class="sxs-lookup"><span data-stu-id="51e73-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="51e73-130">Per qualsiasi tipo di enumerazione esistono rispettivamente le conversioni [Boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md) da e verso il tipo <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51e73-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="51e73-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="51e73-131">C# language specification</span></span>

<span data-ttu-id="51e73-132">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="51e73-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="51e73-133">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="51e73-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="51e73-134">Valori e operazioni di enumerazione</span><span class="sxs-lookup"><span data-stu-id="51e73-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="51e73-135">Operatori logici di enumerazione</span><span class="sxs-lookup"><span data-stu-id="51e73-135">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="51e73-136">Operatori di confronto di enumerazione</span><span class="sxs-lookup"><span data-stu-id="51e73-136">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="51e73-137">Conversioni esplicite dell'enumerazione</span><span class="sxs-lookup"><span data-stu-id="51e73-137">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="51e73-138">Conversioni di enumerazione implicite</span><span class="sxs-lookup"><span data-stu-id="51e73-138">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="51e73-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51e73-139">See also</span></span>

- [<span data-ttu-id="51e73-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="51e73-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="51e73-141">Stringhe di formato di enumerazione</span><span class="sxs-lookup"><span data-stu-id="51e73-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="51e73-142">Linee guida di progettazione-progettazione enum</span><span class="sxs-lookup"><span data-stu-id="51e73-142">Design guidelines - Enum design</span></span>](../../../standard/design-guidelines/enum.md)
- [<span data-ttu-id="51e73-143">Linee guida di progettazione-convenzioni di denominazione enum</span><span class="sxs-lookup"><span data-stu-id="51e73-143">Design guidelines - Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="51e73-144">Istruzione switch</span><span class="sxs-lookup"><span data-stu-id="51e73-144">switch statement</span></span>](../keywords/switch.md)
