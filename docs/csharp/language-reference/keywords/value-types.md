---
title: Tipi di valore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.valuetypes
dev_langs:
- CSharp
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7500426846562dd7f3bbb8ea99f300a3e8a26546
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="value-types-c-reference"></a><span data-ttu-id="0ef8f-102">Tipi di valore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0ef8f-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="0ef8f-103">I tipi valore comprendono due categorie principali:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="0ef8f-104">Struct</span><span class="sxs-lookup"><span data-stu-id="0ef8f-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="0ef8f-105">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="0ef8f-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="0ef8f-106">Gli struct sono suddivisi nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="0ef8f-107">Tipi numerici</span><span class="sxs-lookup"><span data-stu-id="0ef8f-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="0ef8f-108">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="0ef8f-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="0ef8f-109">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="0ef8f-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [<span data-ttu-id="0ef8f-110">decimal</span><span class="sxs-lookup"><span data-stu-id="0ef8f-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [<span data-ttu-id="0ef8f-111">bool</span><span class="sxs-lookup"><span data-stu-id="0ef8f-111">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="0ef8f-112">Struct definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-112">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="0ef8f-113">Funzionalità principali dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="0ef8f-113">Main Features of Value Types</span></span>  
 <span data-ttu-id="0ef8f-114">Le variabili che sono basate direttamente su tipi valore contengono valori.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-114">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="0ef8f-115">Assegnando una variabile di tipo valore a un'altra, il valore contenuto viene copiato.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-115">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="0ef8f-116">Questo comportamento è diverso dall'assegnazione delle variabili di tipo riferimento, in cui viene copiato un riferimento all'oggetto, ma non l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-116">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="0ef8f-117">Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-117">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="0ef8f-118">A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-118">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="0ef8f-119">Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-119">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="0ef8f-120">A differenza dei tipi riferimento, un tipo valore non può contenere il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-120">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="0ef8f-121">Tuttavia, la funzionalità per i [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) consente di assegnare tipi valore a `null`.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-121">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="0ef8f-122">Ogni tipo valore ha un costruttore predefinito implicito che inizializza il valore predefinito di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-122">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="0ef8f-123">Per informazioni sui valori predefiniti dei tipi valore, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0ef8f-123">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="0ef8f-124">Funzionalità principali dei tipi semplici</span><span class="sxs-lookup"><span data-stu-id="0ef8f-124">Main Features of Simple Types</span></span>  
 <span data-ttu-id="0ef8f-125">Tutti i tipi semplici, ovvero quelli integrali del linguaggio C#, sono alias dei tipi di sistema di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-125">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="0ef8f-126">Ad esempio, [int](../../../csharp/language-reference/keywords/int.md) è un alias di <xref:System.Int32?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-126">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=fullName>.</span></span> <span data-ttu-id="0ef8f-127">Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="0ef8f-127">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="0ef8f-128">Le espressioni costanti, in cui gli operandi sono tutte costanti di tipo semplice, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-128">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="0ef8f-129">I tipi semplici possono essere inizializzati mediante valori letterali.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-129">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="0ef8f-130">Ad esempio, 'A' è un valore letterale del tipo `char` e 2001 è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-130">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="0ef8f-131">Inizializzazione di tipi valore</span><span class="sxs-lookup"><span data-stu-id="0ef8f-131">Initializing Value Types</span></span>  
 <span data-ttu-id="0ef8f-132">Le variabili locali in C# devono essere inizializzate prima di poter essere usate.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-132">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="0ef8f-133">È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-133">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```  
int myInt;  
```  
  
 <span data-ttu-id="0ef8f-134">Non è possibile usarla prima di averla inizializzata.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-134">You cannot use it before you initialize it.</span></span> <span data-ttu-id="0ef8f-135">È possibile inizializzarla mediante l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-135">You can initialize it using the following statement:</span></span>  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="0ef8f-136">Questa istruzione è equivalente all'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-136">This statement is equivalent to the following statement:</span></span>  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="0ef8f-137">Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-137">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="0ef8f-138">- oppure -</span><span class="sxs-lookup"><span data-stu-id="0ef8f-138">–or–</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="0ef8f-139">Usando l'operatore [new](../../../csharp/language-reference/keywords/new.md), viene chiamato il costruttore predefinito del tipo specifico e viene assegnato il valore predefinito alla variabile.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-139">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="0ef8f-140">Nell'esempio precedente, il costruttore predefinito assegna il valore `0` a `myInt`.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-140">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="0ef8f-141">Per altre informazioni sui valori assegnati chiamando i costruttori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0ef8f-141">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="0ef8f-142">Con i tipi definiti dall'utente, usare [new](../../../csharp/language-reference/keywords/new.md) per richiamare il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-142">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="0ef8f-143">Ad esempio, l'istruzione seguente richiama il costruttore predefinito dello struct `Point`:</span><span class="sxs-lookup"><span data-stu-id="0ef8f-143">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="0ef8f-144">Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0ef8f-144">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="0ef8f-145">Per altre informazioni sull'operatore new, vedere [new](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="0ef8f-145">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="0ef8f-146">Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="0ef8f-146">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef8f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef8f-147">See Also</span></span>  
 <span data-ttu-id="0ef8f-148">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef8f-148">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ef8f-149">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef8f-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0ef8f-150">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef8f-150">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0ef8f-151">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="0ef8f-151">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="0ef8f-152">[Tabelle di riferimento per i tipi](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="0ef8f-152">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="0ef8f-153">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="0ef8f-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

