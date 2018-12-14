---
title: Tipi valore (Riferimenti per C#)
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: baf0db751cd70d50d4cf440626dd405b01c8d7ad
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147717"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="88fa7-102">Tipi valore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="88fa7-102">Value types (C# Reference)</span></span>

<span data-ttu-id="88fa7-103">Esistono due tipi di tipi valore:</span><span class="sxs-lookup"><span data-stu-id="88fa7-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="88fa7-104">Struct</span><span class="sxs-lookup"><span data-stu-id="88fa7-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="88fa7-105">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="88fa7-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="88fa7-106">Funzionalità principali dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="88fa7-106">Main features of value types</span></span>

<span data-ttu-id="88fa7-107">Una variabile di un tipo valore contiene un valore del tipo.</span><span class="sxs-lookup"><span data-stu-id="88fa7-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="88fa7-108">Ad esempio, una variabile del tipo `int` potrebbe contenere il valore `42`.</span><span class="sxs-lookup"><span data-stu-id="88fa7-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="88fa7-109">Questo comportamento è diverso rispetto a una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo, noto anche come oggetto.</span><span class="sxs-lookup"><span data-stu-id="88fa7-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="88fa7-110">Quando si assegna un nuovo valore a una variabile di un tipo valore, viene copiato quel valore.</span><span class="sxs-lookup"><span data-stu-id="88fa7-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="88fa7-111">Quando si assegna un nuovo valore a una variabile di un tipo riferimento, viene copiato il riferimento, non l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="88fa7-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="88fa7-112">Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88fa7-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
<span data-ttu-id="88fa7-113">A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="88fa7-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="88fa7-114">Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="88fa7-114">However, like reference types, structs can implement interfaces.</span></span>  
  
<span data-ttu-id="88fa7-115">Le variabili del tipo valore non possono essere `null` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="88fa7-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="88fa7-116">Le variabili dei [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) corrispondenti possono invece essere `null`.</span><span class="sxs-lookup"><span data-stu-id="88fa7-116">However, variables of the corresponding [nullable types](../../../csharp/programming-guide/nullable-types/index.md) can be `null`.</span></span>
  
<span data-ttu-id="88fa7-117">Ogni tipo valore ha un costruttore predefinito implicito che inizializza il valore predefinito di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="88fa7-117">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="88fa7-118">Per informazioni sui valori predefiniti dei tipi valore, vedere [Tabella dei valori predefiniti](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>  
  
## <a name="simple-types"></a><span data-ttu-id="88fa7-119">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="88fa7-119">Simple types</span></span>

<span data-ttu-id="88fa7-120">I *tipi semplici* sono un set di tipi struct predefiniti forniti da C# e comprendono i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="88fa7-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="88fa7-121">[Tipi integrali](integral-types-table.md): i tipi numerici interi e il tipo [char](char.md)</span><span class="sxs-lookup"><span data-stu-id="88fa7-121">[Integral types](integral-types-table.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="88fa7-122">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="88fa7-122">Floating-point types</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="88fa7-123">bool</span><span class="sxs-lookup"><span data-stu-id="88fa7-123">bool</span></span>](bool.md)

<span data-ttu-id="88fa7-124">I tipi semplici sono identificati tramite parole chiave, le quali sono in realtà semplicemente degli alias dei tipi struct predefiniti nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="88fa7-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="88fa7-125">Ad esempio, [int](int.md) è un alias di <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88fa7-125">For example, [int](int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="88fa7-126">Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="88fa7-127">I tipi semplici si differenziano da altri tipi struct in quanto permettono alcune operazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="88fa7-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="88fa7-128">I tipi semplici possono essere inizializzati mediante valori letterali.</span><span class="sxs-lookup"><span data-stu-id="88fa7-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="88fa7-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="88fa7-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="88fa7-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="88fa7-131">Non sono ammesse costanti di altri tipi struct.</span><span class="sxs-lookup"><span data-stu-id="88fa7-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="88fa7-132">Le espressioni costanti, in cui tutti gli operandi sono costanti di tipo semplice, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="88fa7-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="88fa7-133">Per altre informazioni, vedere la sezione [Tipi semplici](~/_csharplang/spec/types.md#simple-types) nella [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="initializing-value-types"></a><span data-ttu-id="88fa7-134">Inizializzazione dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="88fa7-134">Initializing value types</span></span>

 <span data-ttu-id="88fa7-135">Le variabili locali in C# devono essere inizializzate prima di poter essere usate.</span><span class="sxs-lookup"><span data-stu-id="88fa7-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="88fa7-136">È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="88fa7-136">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```csharp  
int myInt;  
```  
  
 <span data-ttu-id="88fa7-137">Non è possibile usarla prima di averla inizializzata.</span><span class="sxs-lookup"><span data-stu-id="88fa7-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="88fa7-138">È possibile inizializzarla mediante l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="88fa7-138">You can initialize it using the following statement:</span></span>  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="88fa7-139">Questa istruzione è equivalente all'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="88fa7-139">This statement is equivalent to the following statement:</span></span>  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="88fa7-140">Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="88fa7-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```csharp  
int myInt = new int();  
```  
  
 <span data-ttu-id="88fa7-141">- oppure -</span><span class="sxs-lookup"><span data-stu-id="88fa7-141">–or–</span></span>  
  
```csharp  
int myInt = 0;  
```  
  
 <span data-ttu-id="88fa7-142">Usando l'operatore [new](new.md), viene chiamato il costruttore predefinito del tipo specifico e viene assegnato il valore predefinito alla variabile.</span><span class="sxs-lookup"><span data-stu-id="88fa7-142">Using the [new](new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="88fa7-143">Nell'esempio precedente, il costruttore predefinito assegna il valore `0` a `myInt`.</span><span class="sxs-lookup"><span data-stu-id="88fa7-143">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="88fa7-144">Per altre informazioni sui valori assegnati chiamando i costruttori predefiniti, vedere [Tabella dei valori predefiniti](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-144">For more information about values assigned by calling default constructors, see [Default values table](default-values-table.md).</span></span>  
  
 <span data-ttu-id="88fa7-145">Con i tipi definiti dall'utente, usare [new](new.md) per richiamare il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="88fa7-145">With user-defined types, use [new](new.md) to invoke the default constructor.</span></span> <span data-ttu-id="88fa7-146">Ad esempio, l'istruzione seguente richiama il costruttore predefinito dello struct `Point`:</span><span class="sxs-lookup"><span data-stu-id="88fa7-146">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="88fa7-147">Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="88fa7-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="88fa7-148">Per altre informazioni sull'operatore `new`, vedere [new](new.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-148">For more information about the `new` operator, see [new](new.md).</span></span>  
  
 <span data-ttu-id="88fa7-149">Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="88fa7-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fa7-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88fa7-150">See also</span></span>

- [<span data-ttu-id="88fa7-151">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="88fa7-151">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="88fa7-152">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="88fa7-152">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="88fa7-153">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="88fa7-153">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="88fa7-154">Tipi</span><span class="sxs-lookup"><span data-stu-id="88fa7-154">Types</span></span>](types.md)  
- [<span data-ttu-id="88fa7-155">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="88fa7-155">Reference tables for types</span></span>](reference-tables-for-types.md)  
- [<span data-ttu-id="88fa7-156">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="88fa7-156">Reference Types</span></span>](reference-types.md)  
- [<span data-ttu-id="88fa7-157">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="88fa7-157">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)  
