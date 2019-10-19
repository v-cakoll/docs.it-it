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
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582639"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="6d4a2-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="6d4a2-102">Value Types and Reference Types</span></span>
<span data-ttu-id="6d4a2-103">Esistono due tipi di tipi in Visual Basic: tipi di riferimento e tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="6d4a2-104">Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="6d4a2-105">Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="6d4a2-106">Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso del [modificatore ByRef nei parametri](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="6d4a2-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="6d4a2-107">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="6d4a2-107">Value Types</span></span>  
 <span data-ttu-id="6d4a2-108">Un tipo di dati è un *tipo di valore* se include i dati all'interno della propria allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="6d4a2-109">I tipi di valore includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d4a2-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="6d4a2-110">Tutti i tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="6d4a2-110">All numeric data types</span></span>  
  
- <span data-ttu-id="6d4a2-111">`Boolean`, `Char`e `Date`</span><span class="sxs-lookup"><span data-stu-id="6d4a2-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="6d4a2-112">Tutte le strutture, anche se i relativi membri sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="6d4a2-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="6d4a2-113">Enumerazioni, poiché il tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` o `ULong`</span><span class="sxs-lookup"><span data-stu-id="6d4a2-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="6d4a2-114">Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="6d4a2-115">Per questo motivo, i tipi di valore come `Char` e `Integer` vengono implementati da .NET Framework strutture.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="6d4a2-116">È possibile dichiarare un tipo valore utilizzando la parola chiave riservata, ad esempio `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="6d4a2-117">È anche possibile usare la parola chiave `New` per inizializzare un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="6d4a2-118">Questa operazione è particolarmente utile se il tipo dispone di un costruttore che accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="6d4a2-119">Un esempio è il costruttore <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, che compila un nuovo valore `Decimal` dalle parti fornite.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="6d4a2-120">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="6d4a2-120">Reference Types</span></span>  
 <span data-ttu-id="6d4a2-121">Un *tipo riferimento* archivia un riferimento ai relativi dati.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="6d4a2-122">I tipi di riferimento includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d4a2-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="6d4a2-123">Tutte le matrici, anche se i relativi elementi sono tipi di valore</span><span class="sxs-lookup"><span data-stu-id="6d4a2-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="6d4a2-124">Tipi di classe, ad esempio <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="6d4a2-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="6d4a2-125">Delegati</span><span class="sxs-lookup"><span data-stu-id="6d4a2-125">Delegates</span></span>  
  
 <span data-ttu-id="6d4a2-126">Una classe è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-126">A class is a *reference type*.</span></span> <span data-ttu-id="6d4a2-127">Si noti che ogni matrice è un tipo di riferimento, anche se i relativi membri sono tipi valore.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="6d4a2-128">Poiché ogni tipo di riferimento rappresenta una classe .NET Framework sottostante, è necessario utilizzare la parola chiave [new operator](../../../../visual-basic/language-reference/operators/new-operator.md) quando viene inizializzata.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="6d4a2-129">L'istruzione seguente Inizializza una matrice.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="6d4a2-130">Elementi che non sono tipi</span><span class="sxs-lookup"><span data-stu-id="6d4a2-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="6d4a2-131">Gli elementi di programmazione seguenti non sono qualificati come tipi, perché non è possibile specificarli come tipo di dati per un elemento dichiarato:</span><span class="sxs-lookup"><span data-stu-id="6d4a2-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="6d4a2-132">Namespaces</span><span class="sxs-lookup"><span data-stu-id="6d4a2-132">Namespaces</span></span>  
  
- <span data-ttu-id="6d4a2-133">Moduli</span><span class="sxs-lookup"><span data-stu-id="6d4a2-133">Modules</span></span>  
  
- <span data-ttu-id="6d4a2-134">eventi</span><span class="sxs-lookup"><span data-stu-id="6d4a2-134">Events</span></span>  
  
- <span data-ttu-id="6d4a2-135">Proprietà e procedure</span><span class="sxs-lookup"><span data-stu-id="6d4a2-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="6d4a2-136">Variabili, costanti e campi</span><span class="sxs-lookup"><span data-stu-id="6d4a2-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="6d4a2-137">Utilizzo del tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="6d4a2-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="6d4a2-138">È possibile assegnare un tipo di riferimento o un tipo di valore a una variabile con il tipo di dati `Object`.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="6d4a2-139">Una variabile `Object` include sempre un riferimento ai dati, non i dati stessi.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="6d4a2-140">Tuttavia, se si assegna un tipo valore a una variabile di `Object`, si comporta come se contiene i propri dati.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="6d4a2-141">Per ulteriori informazioni, vedere [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="6d4a2-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="6d4a2-142">È possibile verificare se una variabile di `Object` funge da tipo di riferimento o un tipo di valore passandola al metodo <xref:Microsoft.VisualBasic.Information.IsReference%2A> nella classe <xref:Microsoft.VisualBasic.Information> dello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="6d4a2-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> restituisce `True` se il contenuto della variabile `Object` rappresenta un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4a2-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d4a2-144">See also</span></span>

- [<span data-ttu-id="6d4a2-145">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="6d4a2-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="6d4a2-146">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d4a2-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="6d4a2-147">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="6d4a2-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="6d4a2-148">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6d4a2-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="6d4a2-149">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="6d4a2-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="6d4a2-150">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6d4a2-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
