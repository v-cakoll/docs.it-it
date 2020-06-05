---
title: Tipi di dati compositi
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
ms.openlocfilehash: 3e8df5ccfeca4bc0a19237ba6d59e9d0747080ea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394298"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="16cb0-102">Tipi di dati compositi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16cb0-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="16cb0-103">Oltre ai tipi di dati elementari Visual Basic fornisce, è anche possibile assemblare elementi di tipi diversi per creare *tipi di dati compositi* , ad esempio strutture, matrici e classi.</span><span class="sxs-lookup"><span data-stu-id="16cb0-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="16cb0-104">È possibile compilare tipi di dati compositi da tipi elementari e da altri tipi compositi.</span><span class="sxs-lookup"><span data-stu-id="16cb0-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="16cb0-105">Ad esempio, è possibile definire una matrice di elementi della struttura o una struttura con membri di matrice.</span><span class="sxs-lookup"><span data-stu-id="16cb0-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="16cb0-106">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="16cb0-106">Data Types</span></span>  
 <span data-ttu-id="16cb0-107">Un tipo composito è diverso dal tipo di dati di uno dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="16cb0-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="16cb0-108">Una matrice di elementi, ad esempio, `Integer` non è del `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="16cb0-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="16cb0-109">Un tipo di dati di matrice viene in genere rappresentato utilizzando il tipo di elemento, le parentesi e le virgole secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="16cb0-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="16cb0-110">Ad esempio, una matrice unidimensionale di `String` elementi viene rappresentata come `String()` e una matrice bidimensionale di `Boolean` elementi viene rappresentata come `Boolean(,)` .</span><span class="sxs-lookup"><span data-stu-id="16cb0-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="16cb0-111">Tipi di struttura</span><span class="sxs-lookup"><span data-stu-id="16cb0-111">Structure Types</span></span>  
 <span data-ttu-id="16cb0-112">Non esiste un singolo tipo di dati costituito da tutte le strutture.</span><span class="sxs-lookup"><span data-stu-id="16cb0-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="16cb0-113">Al contrario, ogni definizione di una struttura rappresenta un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="16cb0-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="16cb0-114">Tuttavia, se si creano due o più istanze della stessa struttura, Visual Basic considera che siano dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="16cb0-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="16cb0-115">Tuple</span><span class="sxs-lookup"><span data-stu-id="16cb0-115">Tuples</span></span>

<span data-ttu-id="16cb0-116">Una tupla è una struttura leggera che contiene due o più campi i cui tipi sono predefiniti.</span><span class="sxs-lookup"><span data-stu-id="16cb0-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="16cb0-117">Le tuple sono supportate a partire da Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="16cb0-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="16cb0-118">Le tuple vengono in genere utilizzate per restituire più valori da una singola chiamata al metodo senza dover passare argomenti per riferimento o per comprimere i campi restituiti in una classe o una struttura più pesante.</span><span class="sxs-lookup"><span data-stu-id="16cb0-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="16cb0-119">Per ulteriori informazioni sulle tuple, vedere l'argomento [Tuple](tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="16cb0-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="16cb0-120">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="16cb0-120">Array Types</span></span>  
 <span data-ttu-id="16cb0-121">Non esiste un singolo tipo di dati costituito da tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="16cb0-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="16cb0-122">Il tipo di dati di una determinata istanza di una matrice è determinato dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="16cb0-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="16cb0-123">Il fatto di essere una matrice</span><span class="sxs-lookup"><span data-stu-id="16cb0-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="16cb0-124">Rango (numero di dimensioni) della matrice</span><span class="sxs-lookup"><span data-stu-id="16cb0-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="16cb0-125">Tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="16cb0-125">The element type of the array</span></span>  
  
 <span data-ttu-id="16cb0-126">In particolare, la lunghezza di una determinata dimensione non fa parte del tipo di dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="16cb0-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="16cb0-127">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="16cb0-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="16cb0-128">Nell'esempio precedente, le variabili `arrayA` di matrice e `arrayB` sono considerate dello stesso tipo di dati, `Byte()` anche se vengono inizializzate su lunghezze diverse.</span><span class="sxs-lookup"><span data-stu-id="16cb0-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="16cb0-129">`arrayB`Le variabili e `arrayC` non sono dello stesso tipo perché i tipi di elemento sono diversi.</span><span class="sxs-lookup"><span data-stu-id="16cb0-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="16cb0-130">`arrayC`Le variabili e `arrayD` non sono dello stesso tipo perché le rispettive dimensioni sono diverse.</span><span class="sxs-lookup"><span data-stu-id="16cb0-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="16cb0-131">Le variabili `arrayD` e `arrayE` hanno lo stesso tipo `Short(,)` , perché i relativi tipi di rango e di elemento sono gli stessi, anche se `arrayD` non è stato ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="16cb0-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="16cb0-132">Per ulteriori informazioni sulle matrici, vedere [matrici](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="16cb0-132">For more information on arrays, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="16cb0-133">Tipi di classe</span><span class="sxs-lookup"><span data-stu-id="16cb0-133">Class Types</span></span>  
 <span data-ttu-id="16cb0-134">Non esiste un singolo tipo di dati costituito da tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="16cb0-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="16cb0-135">Sebbene una classe possa ereditare da un'altra classe, ognuno è un tipo di dati separato.</span><span class="sxs-lookup"><span data-stu-id="16cb0-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="16cb0-136">Più istanze della stessa classe sono dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="16cb0-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="16cb0-137">Se si assegna una variabile di istanza di classe a un'altra, non solo i tipi di dati hanno lo stesso tipo di dati, fanno riferimento alla stessa istanza della classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="16cb0-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="16cb0-138">Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="16cb0-138">For more information on classes, see [Objects and Classes](../objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16cb0-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cb0-139">See also</span></span>

- [<span data-ttu-id="16cb0-140">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="16cb0-140">Data Types</span></span>](index.md)
- [<span data-ttu-id="16cb0-141">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="16cb0-141">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="16cb0-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16cb0-142">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="16cb0-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="16cb0-143">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="16cb0-144">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16cb0-144">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="16cb0-145">Strutture</span><span class="sxs-lookup"><span data-stu-id="16cb0-145">Structures</span></span>](structures.md)
- [<span data-ttu-id="16cb0-146">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="16cb0-146">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="16cb0-147">Procedura: Inserire più valori in una variabile</span><span class="sxs-lookup"><span data-stu-id="16cb0-147">How to: Hold More Than One Value in a Variable</span></span>](how-to-hold-more-than-one-value-in-a-variable.md)
