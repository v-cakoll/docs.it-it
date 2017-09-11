---
title: Tipi di valore e tipi di riferimento | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8136f58b2e7fce15e959e04b84b05f64d078d662
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="46dd9-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="46dd9-102">Value Types and Reference Types</span></span>
<span data-ttu-id="46dd9-103">In Visual Basic, tipi di dati vengono implementati in base alla relativa classificazione.</span><span class="sxs-lookup"><span data-stu-id="46dd9-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="46dd9-104">Il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati possono essere classificati in base a che una variabile di un determinato tipo archivi i propri dati o un puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="46dd9-104">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="46dd9-105">Se archivia i propri dati è un *tipo di valore*; se contiene un puntatore ai dati in un' posizione in memoria è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="46dd9-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="46dd9-106">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="46dd9-106">Value Types</span></span>  
 <span data-ttu-id="46dd9-107">Un tipo di dati è un *tipo di valore* se contiene i dati nella propria allocazione di memoria.</span><span class="sxs-lookup"><span data-stu-id="46dd9-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="46dd9-108">Tipi di valore includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="46dd9-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="46dd9-109">Tutti i tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="46dd9-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="46dd9-110">`Boolean`, `Char` e `Date`</span><span class="sxs-lookup"><span data-stu-id="46dd9-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="46dd9-111">Tutte le strutture, anche se i relativi membri sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="46dd9-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="46dd9-112">Le enumerazioni, in quanto il relativo tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o`ULong`</span><span class="sxs-lookup"><span data-stu-id="46dd9-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="46dd9-113">Ogni struttura è un tipo di valore, anche se contiene membri di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="46dd9-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="46dd9-114">Per questo motivo, i tipi valore, ad esempio `Char` e `Integer` sono implementati da strutture di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46dd9-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="46dd9-115">È possibile dichiarare un tipo di valore utilizzando la parola chiave riservata, ad esempio, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="46dd9-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="46dd9-116">È inoltre possibile utilizzare il `New` (parola chiave) per inizializzare un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="46dd9-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="46dd9-117">Ciò è particolarmente utile se il tipo ha un costruttore che accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="46dd9-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="46dd9-118">Un esempio di questo è il <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>costruttore, che crea un nuovo `Decimal` valore dalle parti fornite.</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29></span><span class="sxs-lookup"><span data-stu-id="46dd9-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="46dd9-119">Tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="46dd9-119">Reference Types</span></span>  
 <span data-ttu-id="46dd9-120">Oggetto *tipo di riferimento* contiene un puntatore a un'altra posizione di memoria che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="46dd9-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="46dd9-121">Tipi di riferimento includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="46dd9-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="46dd9-122">Tutte le matrici, anche se i relativi elementi sono tipi di valore</span><span class="sxs-lookup"><span data-stu-id="46dd9-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="46dd9-123">Tipi di classe, ad esempio<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="46dd9-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="46dd9-124">Delegati</span><span class="sxs-lookup"><span data-stu-id="46dd9-124">Delegates</span></span>  
  
 <span data-ttu-id="46dd9-125">Una classe è un *tipo di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="46dd9-125">A class is a *reference type*.</span></span> <span data-ttu-id="46dd9-126">Per questo motivo, tipi di riferimento, ad esempio `Object` e `String` sono supportati da [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] classi.</span><span class="sxs-lookup"><span data-stu-id="46dd9-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes.</span></span> <span data-ttu-id="46dd9-127">Si noti che ogni matrice è un tipo di riferimento, anche se i relativi membri sono tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="46dd9-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="46dd9-128">Poiché ogni tipo di riferimento rappresenta una classe .NET Framework sottostante, è necessario utilizzare il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave quando si inizializza.</span><span class="sxs-lookup"><span data-stu-id="46dd9-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="46dd9-129">L'istruzione seguente consente di inizializzare una matrice.</span><span class="sxs-lookup"><span data-stu-id="46dd9-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="46dd9-130">Elementi che non sono tipi</span><span class="sxs-lookup"><span data-stu-id="46dd9-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="46dd9-131">I seguenti elementi di programmazione non è qualificano come tipi, perché non è possibile specificare uno di essi come tipo di dati per un elemento dichiarato:</span><span class="sxs-lookup"><span data-stu-id="46dd9-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="46dd9-132">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="46dd9-132">Namespaces</span></span>  
  
-   <span data-ttu-id="46dd9-133">Moduli</span><span class="sxs-lookup"><span data-stu-id="46dd9-133">Modules</span></span>  
  
-   <span data-ttu-id="46dd9-134">Eventi</span><span class="sxs-lookup"><span data-stu-id="46dd9-134">Events</span></span>  
  
-   <span data-ttu-id="46dd9-135">Le proprietà e procedure</span><span class="sxs-lookup"><span data-stu-id="46dd9-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="46dd9-136">Le variabili, costanti e campi</span><span class="sxs-lookup"><span data-stu-id="46dd9-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="46dd9-137">Utilizzo del tipo di dati oggetto</span><span class="sxs-lookup"><span data-stu-id="46dd9-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="46dd9-138">È possibile assegnare un tipo di riferimento o un tipo di valore a una variabile del `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="46dd9-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="46dd9-139">Un `Object` variabile contiene sempre un puntatore ai dati, mai i dati stessi.</span><span class="sxs-lookup"><span data-stu-id="46dd9-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="46dd9-140">Tuttavia, se si assegna un tipo di valore a un `Object` variabile, si comporta come se contenesse i propri dati.</span><span class="sxs-lookup"><span data-stu-id="46dd9-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="46dd9-141">Per ulteriori informazioni, vedere [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="46dd9-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="46dd9-142">È possibile scoprire se un `Object` variabile funge da un tipo di riferimento o un tipo di valore passandola al <xref:Microsoft.VisualBasic.Information.IsReference%2A>metodo la <xref:Microsoft.VisualBasic.Information>classe del <xref:Microsoft.VisualBasic?displayProperty=fullName>dello spazio dei nomi.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="46dd9-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="46dd9-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>Restituisce `True` se il contenuto di `Object` variabile rappresenta un tipo di riferimento.</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="46dd9-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dd9-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46dd9-144">See Also</span></span>  
 <span data-ttu-id="46dd9-145">[Tipi di valore nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="46dd9-145">[Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="46dd9-146"> [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="46dd9-146"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="46dd9-147"> [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="46dd9-147"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="46dd9-148"> [Utilizzo efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="46dd9-148"> [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md) </span></span>  
<span data-ttu-id="46dd9-149"> [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="46dd9-149"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="46dd9-150"> [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="46dd9-150"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
