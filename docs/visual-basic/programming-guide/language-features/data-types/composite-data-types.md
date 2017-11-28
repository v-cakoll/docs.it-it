---
title: Tipi di dati compositi (Visual Basic)
ms.custom: 
ms.date: 04/25/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e9adb407757dbee2f7ac5a94118623a62212faec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="4a0c8-102">Tipi di dati compositi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a0c8-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="4a0c8-103">Oltre ai tipi di dati elementare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornisce, è possibile unire gli elementi di tipi diversi per creare *tipi di dati compositi* quali classi, matrici e strutture.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-103">In addition to the elementary data types [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="4a0c8-104">È possibile compilare i tipi di dati composti da tipi di base e da altri tipi compositi.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="4a0c8-105">Ad esempio, è possibile definire una matrice di elementi di struttura o una struttura con i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4a0c8-106">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4a0c8-106">Data Types</span></span>  
 <span data-ttu-id="4a0c8-107">Un tipo composito è diverso dal tipo di dati di uno qualsiasi dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="4a0c8-108">Ad esempio, una matrice di `Integer` elementi non è il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="4a0c8-109">In genere i dati di tipo matrice sono rappresentato utilizzando il tipo di elemento, tra parentesi e virgole in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="4a0c8-110">Ad esempio, una matrice unidimensionale di `String` elementi è rappresentato come `String()`e una matrice bidimensionale di `Boolean` elementi è rappresentato come `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="4a0c8-111">Tipi di struttura</span><span class="sxs-lookup"><span data-stu-id="4a0c8-111">Structure Types</span></span>  
 <span data-ttu-id="4a0c8-112">Non vi è alcun tipo di dati singolo che comprende tutte le strutture.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="4a0c8-113">Ogni definizione di una struttura rappresenta invece un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="4a0c8-114">Tuttavia, se si creano due o più istanze della stessa struttura, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ritiene possano essere dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="4a0c8-115">Tuple</span><span class="sxs-lookup"><span data-stu-id="4a0c8-115">Tuples</span></span>

<span data-ttu-id="4a0c8-116">Una tupla è una struttura semplice che contiene due o più campi i cui tipi sono predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="4a0c8-117">Le tuple sono supportate a partire da Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="4a0c8-118">Le tuple sono utilizzate principalmente per restituire più valori da una singola chiamata al metodo senza dover passare gli argomenti per riferimento o creandone un pacchetto campi restituiti in una classe più grave o struttura.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="4a0c8-119">Vedere il [Tuple](tuples.md) per ulteriori informazioni sulle Tuple.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="4a0c8-120">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="4a0c8-120">Array Types</span></span>  
 <span data-ttu-id="4a0c8-121">Non vi è alcun tipo di dati singolo che comprende tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="4a0c8-122">Il tipo di dati di una particolare istanza di una matrice viene determinato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4a0c8-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="4a0c8-123">Il fatto di essere una matrice</span><span class="sxs-lookup"><span data-stu-id="4a0c8-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="4a0c8-124">La classificazione (numero di dimensioni) della matrice</span><span class="sxs-lookup"><span data-stu-id="4a0c8-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="4a0c8-125">Il tipo di elemento della matrice</span><span class="sxs-lookup"><span data-stu-id="4a0c8-125">The element type of the array</span></span>  
  
 <span data-ttu-id="4a0c8-126">In particolare, la lunghezza di una determinata dimensione non fa parte dell'istanza tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="4a0c8-127">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="4a0c8-128">Nell'esempio precedente, le variabili di matrice `arrayA` e `arrayB` vengono considerati dello stesso tipo di dati, ovvero `Byte()` , anche se vengono inizializzate su lunghezze diverse.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="4a0c8-129">Le variabili `arrayB` e `arrayC` non sono dello stesso tipo perché i relativi tipi di elemento sono diversi.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="4a0c8-130">Le variabili `arrayC` e `arrayD` non sono dello stesso tipo perché i relativi indici sono differenti.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="4a0c8-131">Le variabili `arrayD` e `arrayE` hanno lo stesso tipo, ovvero `Short(,)` , perché le classificazioni e i tipi di elemento sono gli stessi, anche se `arrayD` non ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="4a0c8-132">Per ulteriori informazioni sulle matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a0c8-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="4a0c8-133">Tipi di classe</span><span class="sxs-lookup"><span data-stu-id="4a0c8-133">Class Types</span></span>  
 <span data-ttu-id="4a0c8-134">Non vi è alcun tipo di dati singolo che comprende tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="4a0c8-135">Anche se una classe può ereditare da un'altra classe, ognuno è un tipo di dati separato.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="4a0c8-136">Più istanze della stessa classe sono dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="4a0c8-137">Se si assegna una variabile di istanza di classe a un altro, non solo se hanno gli stessi dati di tipo, entrambe puntano alla stessa istanza di classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="4a0c8-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="4a0c8-138">Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a0c8-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0c8-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a0c8-139">See Also</span></span>  
 [<span data-ttu-id="4a0c8-140">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4a0c8-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="4a0c8-141">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="4a0c8-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="4a0c8-142">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a0c8-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="4a0c8-143">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="4a0c8-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="4a0c8-144">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a0c8-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="4a0c8-145">Strutture</span><span class="sxs-lookup"><span data-stu-id="4a0c8-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="4a0c8-146">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4a0c8-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="4a0c8-147">Procedura: Inserire più valori in una variabile</span><span class="sxs-lookup"><span data-stu-id="4a0c8-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
