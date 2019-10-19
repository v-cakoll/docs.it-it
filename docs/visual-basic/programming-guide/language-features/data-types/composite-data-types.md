---
title: Tipi di dati compositi (Visual Basic)
ms.date: 04/25/2017
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
ms.openlocfilehash: 768559c7a6caf064f7529786675e51ce19667d6b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581719"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="33b57-102">Tipi di dati compositi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33b57-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="33b57-103">Oltre ai tipi di dati elementari Visual Basic fornisce, è anche possibile assemblare elementi di tipi diversi per creare *tipi di dati compositi* , ad esempio strutture, matrici e classi.</span><span class="sxs-lookup"><span data-stu-id="33b57-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="33b57-104">È possibile compilare tipi di dati compositi da tipi elementari e da altri tipi compositi.</span><span class="sxs-lookup"><span data-stu-id="33b57-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="33b57-105">Ad esempio, è possibile definire una matrice di elementi della struttura o una struttura con membri di matrice.</span><span class="sxs-lookup"><span data-stu-id="33b57-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="33b57-106">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="33b57-106">Data Types</span></span>  
 <span data-ttu-id="33b57-107">Un tipo composito è diverso dal tipo di dati di uno dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="33b57-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="33b57-108">Una matrice di elementi `Integer`, ad esempio, non è del tipo di dati `Integer`.</span><span class="sxs-lookup"><span data-stu-id="33b57-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="33b57-109">Un tipo di dati di matrice viene in genere rappresentato utilizzando il tipo di elemento, le parentesi e le virgole secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="33b57-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="33b57-110">Ad esempio, una matrice unidimensionale di elementi `String` viene rappresentata come `String()` e una matrice bidimensionale di elementi `Boolean` viene rappresentata come `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="33b57-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="33b57-111">Tipi di struttura</span><span class="sxs-lookup"><span data-stu-id="33b57-111">Structure Types</span></span>  
 <span data-ttu-id="33b57-112">Non esiste un singolo tipo di dati costituito da tutte le strutture.</span><span class="sxs-lookup"><span data-stu-id="33b57-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="33b57-113">Al contrario, ogni definizione di una struttura rappresenta un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="33b57-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="33b57-114">Tuttavia, se si creano due o più istanze della stessa struttura, Visual Basic considera che siano dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="33b57-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="33b57-115">Tuple</span><span class="sxs-lookup"><span data-stu-id="33b57-115">Tuples</span></span>

<span data-ttu-id="33b57-116">Una tupla è una struttura leggera che contiene due o più campi i cui tipi sono predefiniti.</span><span class="sxs-lookup"><span data-stu-id="33b57-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="33b57-117">Le tuple sono supportate a partire da Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="33b57-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="33b57-118">Le tuple vengono in genere utilizzate per restituire più valori da una singola chiamata al metodo senza dover passare argomenti per riferimento o per comprimere i campi restituiti in una classe o una struttura più pesante.</span><span class="sxs-lookup"><span data-stu-id="33b57-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="33b57-119">Per ulteriori informazioni sulle tuple, vedere l'argomento [Tuple](tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="33b57-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="33b57-120">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="33b57-120">Array Types</span></span>  
 <span data-ttu-id="33b57-121">Non esiste un singolo tipo di dati costituito da tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="33b57-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="33b57-122">Il tipo di dati di una determinata istanza di una matrice è determinato dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="33b57-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="33b57-123">Il fatto di essere una matrice</span><span class="sxs-lookup"><span data-stu-id="33b57-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="33b57-124">Rango (numero di dimensioni) della matrice</span><span class="sxs-lookup"><span data-stu-id="33b57-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="33b57-125">Tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="33b57-125">The element type of the array</span></span>  
  
 <span data-ttu-id="33b57-126">In particolare, la lunghezza di una determinata dimensione non fa parte del tipo di dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="33b57-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="33b57-127">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="33b57-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="33b57-128">Nell'esempio precedente, le variabili di matrice `arrayA` e `arrayB` sono considerate dello stesso tipo di dati, `Byte()`, anche se vengono inizializzate su lunghezze diverse.</span><span class="sxs-lookup"><span data-stu-id="33b57-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="33b57-129">Le variabili `arrayB` e `arrayC` non sono dello stesso tipo perché i tipi di elemento sono diversi.</span><span class="sxs-lookup"><span data-stu-id="33b57-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="33b57-130">Le variabili `arrayC` e `arrayD` non sono dello stesso tipo perché le relative dimensioni sono diverse.</span><span class="sxs-lookup"><span data-stu-id="33b57-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="33b57-131">Le variabili `arrayD` e `arrayE` hanno lo stesso tipo, `Short(,)`, perché i relativi tipi di rango e di elemento sono gli stessi, anche se `arrayD` non è ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="33b57-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="33b57-132">Per ulteriori informazioni sulle matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="33b57-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="33b57-133">Tipi di classe</span><span class="sxs-lookup"><span data-stu-id="33b57-133">Class Types</span></span>  
 <span data-ttu-id="33b57-134">Non esiste un singolo tipo di dati costituito da tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="33b57-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="33b57-135">Sebbene una classe possa ereditare da un'altra classe, ognuno è un tipo di dati separato.</span><span class="sxs-lookup"><span data-stu-id="33b57-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="33b57-136">Più istanze della stessa classe sono dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="33b57-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="33b57-137">Se si assegna una variabile di istanza di classe a un'altra, non solo i tipi di dati hanno lo stesso tipo di dati, fanno riferimento alla stessa istanza della classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="33b57-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="33b57-138">Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="33b57-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b57-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b57-139">See also</span></span>

- [<span data-ttu-id="33b57-140">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="33b57-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="33b57-141">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="33b57-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="33b57-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33b57-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="33b57-143">Tipi valore e tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="33b57-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="33b57-144">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33b57-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="33b57-145">Strutture</span><span class="sxs-lookup"><span data-stu-id="33b57-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="33b57-146">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="33b57-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="33b57-147">Procedura: Inserire più valori in una variabile</span><span class="sxs-lookup"><span data-stu-id="33b57-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
