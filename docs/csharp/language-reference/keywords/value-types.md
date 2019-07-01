---
title: Tipi valore - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 9907811a43f408020e2ee76621d4975a53945570
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424027"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="e7cc8-102">Tipi valore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e7cc8-102">Value types (C# Reference)</span></span>

<span data-ttu-id="e7cc8-103">Esistono due tipi di tipi valore:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="e7cc8-104">Struct</span><span class="sxs-lookup"><span data-stu-id="e7cc8-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="e7cc8-105">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e7cc8-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="e7cc8-106">Funzionalità principali dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="e7cc8-106">Main features of value types</span></span>

<span data-ttu-id="e7cc8-107">Una variabile di un tipo valore contiene un valore del tipo.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="e7cc8-108">Ad esempio, una variabile del tipo `int` potrebbe contenere il valore `42`.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="e7cc8-109">Questo comportamento è diverso rispetto a una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo, noto anche come oggetto.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="e7cc8-110">Quando si assegna un nuovo valore a una variabile di un tipo valore, viene copiato quel valore.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="e7cc8-111">Quando si assegna un nuovo valore a una variabile di un tipo riferimento, viene copiato il riferimento, non l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="e7cc8-112">Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e7cc8-113">A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="e7cc8-114">Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="e7cc8-115">Le variabili del tipo valore non possono essere `null` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="e7cc8-116">Le variabili dei [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) corrispondenti possono invece essere `null`.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-116">However, variables of the corresponding [nullable types](../../../csharp/programming-guide/nullable-types/index.md) can be `null`.</span></span>

<span data-ttu-id="e7cc8-117">Ogni tipo valore ha un costruttore senza parametri implicito che inizializza il valore predefinito del tipo.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="e7cc8-118">Per informazioni sui valori predefiniti dei tipi valore, vedere [Tabella dei valori predefiniti](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="e7cc8-119">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="e7cc8-119">Simple types</span></span>

<span data-ttu-id="e7cc8-120">I *tipi semplici* sono un set di tipi struct predefiniti forniti da C# e comprendono i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="e7cc8-121">[Tipi integrali](../builtin-types/integral-numeric-types.md): i tipi numerici interi e il tipo [char](char.md)</span><span class="sxs-lookup"><span data-stu-id="e7cc8-121">[Integral types](../builtin-types/integral-numeric-types.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="e7cc8-122">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="e7cc8-122">Floating-point types</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="e7cc8-123">bool</span><span class="sxs-lookup"><span data-stu-id="e7cc8-123">bool</span></span>](bool.md)

<span data-ttu-id="e7cc8-124">I tipi semplici sono identificati tramite parole chiave, le quali sono in realtà semplicemente degli alias dei tipi struct predefiniti nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="e7cc8-125">Ad esempio, [int](../builtin-types/integral-numeric-types.md) è un alias di <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-125">For example, [int](../builtin-types/integral-numeric-types.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e7cc8-126">Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="e7cc8-127">I tipi semplici si differenziano da altri tipi struct in quanto permettono alcune operazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="e7cc8-128">I tipi semplici possono essere inizializzati mediante valori letterali.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="e7cc8-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="e7cc8-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="e7cc8-131">Non sono ammesse costanti di altri tipi struct.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="e7cc8-132">Le espressioni costanti, in cui tutti gli operandi sono costanti di tipo semplice, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="e7cc8-133">Per altre informazioni, vedere la sezione [Tipi semplici](~/_csharplang/spec/types.md#simple-types) nella [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="e7cc8-134">Inizializzazione dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="e7cc8-134">Initializing value types</span></span>

<span data-ttu-id="e7cc8-135">Le variabili locali in C# devono essere inizializzate prima di poter essere usate.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="e7cc8-136">È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="e7cc8-137">Non è possibile usarla prima di averla inizializzata.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="e7cc8-138">È possibile inizializzarla mediante l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="e7cc8-139">Questa istruzione è equivalente all'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="e7cc8-140">Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="e7cc8-141">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="e7cc8-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="e7cc8-142">Usando l'operatore [new](../operators/new-operator.md), viene chiamato il costruttore senza parametri del tipo specifico e viene assegnato il valore predefinito alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-142">Using the [new](../operators/new-operator.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="e7cc8-143">Nell'esempio precedente il costruttore senza parametri ha assegnato il valore `0` a `myInt`.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="e7cc8-144">Per altre informazioni sui valori assegnati chiamando i costruttori predefiniti, vedere [Tabella dei valori predefiniti](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-144">For more information about values assigned by calling default constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="e7cc8-145">Con i tipi definiti dall'utente, usare [new](../operators/new-operator.md) per richiamare il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-145">With user-defined types, use [new](../operators/new-operator.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="e7cc8-146">Ad esempio, l'istruzione seguente richiama il costruttore senza parametri dello struct `Point`:</span><span class="sxs-lookup"><span data-stu-id="e7cc8-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
Point p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="e7cc8-147">Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e7cc8-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="e7cc8-148">Per altre informazioni sull'operatore `new`, vedere [new](../operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-148">For more information about the `new` operator, see [new](../operators/new-operator.md).</span></span>

<span data-ttu-id="e7cc8-149">Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="e7cc8-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7cc8-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7cc8-150">See also</span></span>

- [<span data-ttu-id="e7cc8-151">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e7cc8-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e7cc8-152">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e7cc8-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e7cc8-153">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e7cc8-153">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e7cc8-154">Tipi</span><span class="sxs-lookup"><span data-stu-id="e7cc8-154">Types</span></span>](types.md)
- [<span data-ttu-id="e7cc8-155">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="e7cc8-155">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="e7cc8-156">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="e7cc8-156">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)
