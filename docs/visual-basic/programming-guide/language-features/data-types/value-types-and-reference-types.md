---
title: Value Types and Reference Types
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cbab25e4af6b96ae22fe18d0b8a8fdbc7a7c7a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="920f1-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="920f1-102">Value Types and Reference Types</span></span>
<span data-ttu-id="920f1-103">In Visual Basic, i tipi di dati vengono implementati in base alla relativa classificazione.</span><span class="sxs-lookup"><span data-stu-id="920f1-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="920f1-104">I tipi di dati Visual Basic possono essere classificati in base a una variabile di un determinato tipo archiviazione o meno i propri dati o un puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="920f1-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="920f1-105">Se archivia i propri dati è un *tipo di valore*; se contiene un puntatore ai dati in un' posizione in memoria è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="920f1-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="920f1-106">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="920f1-106">Value Types</span></span>  
 <span data-ttu-id="920f1-107">Un tipo di dati è un *tipo di valore* se contiene i dati nella propria allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="920f1-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="920f1-108">Tipi di valore sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="920f1-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="920f1-109">Tutti i tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="920f1-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="920f1-110">`Boolean`, `Char` e `Date`</span><span class="sxs-lookup"><span data-stu-id="920f1-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="920f1-111">Tutte le strutture, anche se i relativi membri sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="920f1-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="920f1-112">Le enumerazioni, in quanto il relativo tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o `ULong`</span><span class="sxs-lookup"><span data-stu-id="920f1-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="920f1-113">Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="920f1-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="920f1-114">Per questo motivo, i tipi valore come `Char` e `Integer` vengono implementati dalle strutture di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="920f1-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="920f1-115">È possibile dichiarare un tipo di valore utilizzando la parola chiave riservata, ad esempio, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="920f1-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="920f1-116">È inoltre possibile utilizzare il `New` (parola chiave) per inizializzare un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="920f1-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="920f1-117">Ciò è particolarmente utile se il tipo ha un costruttore che accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="920f1-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="920f1-118">Un esempio di questo è il <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> costruttore, che genera un nuovo `Decimal` valore dalle parti fornite.</span><span class="sxs-lookup"><span data-stu-id="920f1-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="920f1-119">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="920f1-119">Reference Types</span></span>  
 <span data-ttu-id="920f1-120">Oggetto *tipo di riferimento* contiene un puntatore a un'altra posizione di memoria che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="920f1-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="920f1-121">I tipi di riferimento includono:</span><span class="sxs-lookup"><span data-stu-id="920f1-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="920f1-122">Tutte le matrici, anche se i relativi elementi sono tipi di valore</span><span class="sxs-lookup"><span data-stu-id="920f1-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="920f1-123">Tipi di classe, ad esempio <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="920f1-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="920f1-124">Delegati</span><span class="sxs-lookup"><span data-stu-id="920f1-124">Delegates</span></span>  
  
 <span data-ttu-id="920f1-125">Una classe è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="920f1-125">A class is a *reference type*.</span></span> <span data-ttu-id="920f1-126">Per questo motivo, tipi di riferimento, ad esempio `Object` e `String` sono supportati da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classi.</span><span class="sxs-lookup"><span data-stu-id="920f1-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="920f1-127">Si noti che ogni matrice è un tipo riferimento, anche se i relativi membri sono tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="920f1-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="920f1-128">Poiché ogni tipo di riferimento rappresenta una classe sottostante di .NET Framework, è necessario utilizzare il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave quando la si inizializza.</span><span class="sxs-lookup"><span data-stu-id="920f1-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="920f1-129">L'istruzione seguente consente di inizializzare una matrice.</span><span class="sxs-lookup"><span data-stu-id="920f1-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="920f1-130">Elementi che non sono tipi</span><span class="sxs-lookup"><span data-stu-id="920f1-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="920f1-131">I seguenti elementi di programmazione non è qualificano come tipi, perché non è possibile specificare uno di essi come tipo di dati per un elemento dichiarato:</span><span class="sxs-lookup"><span data-stu-id="920f1-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="920f1-132">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="920f1-132">Namespaces</span></span>  
  
-   <span data-ttu-id="920f1-133">Moduli</span><span class="sxs-lookup"><span data-stu-id="920f1-133">Modules</span></span>  
  
-   <span data-ttu-id="920f1-134">Eventi</span><span class="sxs-lookup"><span data-stu-id="920f1-134">Events</span></span>  
  
-   <span data-ttu-id="920f1-135">Proprietà e routine</span><span class="sxs-lookup"><span data-stu-id="920f1-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="920f1-136">Le variabili, costanti e campi</span><span class="sxs-lookup"><span data-stu-id="920f1-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="920f1-137">Utilizzo del tipo di dati oggetto</span><span class="sxs-lookup"><span data-stu-id="920f1-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="920f1-138">È possibile assegnare un tipo riferimento o un tipo di valore a una variabile del `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="920f1-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="920f1-139">Un `Object` variabile contiene sempre un puntatore ai dati, mai i dati stessi.</span><span class="sxs-lookup"><span data-stu-id="920f1-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="920f1-140">Tuttavia, se si assegna un tipo di valore a un `Object` variabile, si comporta come se contenesse i propri dati.</span><span class="sxs-lookup"><span data-stu-id="920f1-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="920f1-141">Per ulteriori informazioni, vedere [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="920f1-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="920f1-142">È possibile scoprire se un `Object` variabile funge da un tipo riferimento o un tipo di valore passandola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> metodo il <xref:Microsoft.VisualBasic.Information> classe del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="920f1-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="920f1-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Restituisce `True` se il contenuto del `Object` variabile rappresenta un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="920f1-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920f1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="920f1-144">See Also</span></span>  
 [<span data-ttu-id="920f1-145">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="920f1-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="920f1-146">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="920f1-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="920f1-147">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="920f1-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="920f1-148">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="920f1-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="920f1-149">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="920f1-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="920f1-150">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="920f1-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
