---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 3a1de120f5f97ba93939f332f121d70cd3091216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392974"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="bdfd1-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="bdfd1-102">Value Types and Reference Types</span></span>
<span data-ttu-id="bdfd1-103">Esistono due tipi di tipi in Visual Basic: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="bdfd1-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="bdfd1-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="bdfd1-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso del [modificatore ByRef nei parametri](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="bdfd1-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="bdfd1-107">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="bdfd1-107">Value Types</span></span>  
 <span data-ttu-id="bdfd1-108">Un tipo di dati è un *tipo di valore* se include i dati all'interno della propria allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="bdfd1-109">I tipi di valore includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdfd1-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="bdfd1-110">Tutti i tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="bdfd1-110">All numeric data types</span></span>  
  
- <span data-ttu-id="bdfd1-111">`Boolean`, `Char` e `Date`</span><span class="sxs-lookup"><span data-stu-id="bdfd1-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="bdfd1-112">Tutte le strutture, anche se i relativi membri sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="bdfd1-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="bdfd1-113">Enumerazioni, poiché il tipo sottostante è sempre,,,,,, `SByte` `Short` `Integer` `Long` `Byte` `UShort` `UInteger` o`ULong`</span><span class="sxs-lookup"><span data-stu-id="bdfd1-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="bdfd1-114">Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="bdfd1-115">Per questo motivo, i tipi di valore come `Char` e `Integer` vengono implementati da strutture di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="bdfd1-116">È possibile dichiarare un tipo valore utilizzando la parola chiave riservata, ad esempio `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="bdfd1-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="bdfd1-117">È anche possibile usare la `New` parola chiave per inizializzare un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="bdfd1-118">Questa operazione è particolarmente utile se il tipo dispone di un costruttore che accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="bdfd1-119">Un esempio è il <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> costruttore, che compila un nuovo `Decimal` valore dalle parti fornite.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="bdfd1-120">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="bdfd1-120">Reference Types</span></span>  
 <span data-ttu-id="bdfd1-121">Un *tipo riferimento* archivia un riferimento ai relativi dati.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="bdfd1-122">I tipi di riferimento includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bdfd1-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="bdfd1-123">Tutte le matrici, anche se i relativi elementi sono tipi di valore</span><span class="sxs-lookup"><span data-stu-id="bdfd1-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="bdfd1-124">Tipi di classe, ad esempio<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="bdfd1-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="bdfd1-125">Delegati</span><span class="sxs-lookup"><span data-stu-id="bdfd1-125">Delegates</span></span>  
  
 <span data-ttu-id="bdfd1-126">Una classe è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-126">A class is a *reference type*.</span></span> <span data-ttu-id="bdfd1-127">Si noti che ogni matrice è un tipo di riferimento, anche se i relativi membri sono tipi valore.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="bdfd1-128">Poiché ogni tipo di riferimento rappresenta una classe .NET Framework sottostante, è necessario utilizzare la parola chiave [new operator](../../../language-reference/operators/new-operator.md) quando viene inizializzata.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="bdfd1-129">L'istruzione seguente Inizializza una matrice.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="bdfd1-130">Elementi che non sono tipi</span><span class="sxs-lookup"><span data-stu-id="bdfd1-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="bdfd1-131">Gli elementi di programmazione seguenti non sono qualificati come tipi, perché non è possibile specificarli come tipo di dati per un elemento dichiarato:</span><span class="sxs-lookup"><span data-stu-id="bdfd1-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="bdfd1-132">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="bdfd1-132">Namespaces</span></span>  
  
- <span data-ttu-id="bdfd1-133">Moduli</span><span class="sxs-lookup"><span data-stu-id="bdfd1-133">Modules</span></span>  
  
- <span data-ttu-id="bdfd1-134">Events</span><span class="sxs-lookup"><span data-stu-id="bdfd1-134">Events</span></span>  
  
- <span data-ttu-id="bdfd1-135">Proprietà e procedure</span><span class="sxs-lookup"><span data-stu-id="bdfd1-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="bdfd1-136">Variabili, costanti e campi</span><span class="sxs-lookup"><span data-stu-id="bdfd1-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="bdfd1-137">Utilizzo del tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="bdfd1-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="bdfd1-138">È possibile assegnare un tipo di riferimento o un tipo di valore a una variabile del `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="bdfd1-139">Una `Object` variabile include sempre un riferimento ai dati, non i dati stessi.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="bdfd1-140">Tuttavia, se si assegna un tipo valore a una `Object` variabile, si comporta come se contiene i propri dati.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="bdfd1-141">Per ulteriori informazioni, vedere [tipo di dati Object](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="bdfd1-141">For more information, see [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="bdfd1-142">È possibile verificare se una `Object` variabile funge da tipo di riferimento o un tipo di valore passandola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> metodo nella <xref:Microsoft.VisualBasic.Information> classe dello <xref:Microsoft.VisualBasic?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="bdfd1-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>restituisce `True` se il contenuto della `Object` variabile rappresenta un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bdfd1-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfd1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdfd1-144">See also</span></span>

- [<span data-ttu-id="bdfd1-145">Tipi di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="bdfd1-145">Nullable Value Types</span></span>](nullable-value-types.md)
- [<span data-ttu-id="bdfd1-146">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfd1-146">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="bdfd1-147">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="bdfd1-147">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="bdfd1-148">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="bdfd1-148">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
- [<span data-ttu-id="bdfd1-149">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="bdfd1-149">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="bdfd1-150">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="bdfd1-150">Data Types</span></span>](index.md)
