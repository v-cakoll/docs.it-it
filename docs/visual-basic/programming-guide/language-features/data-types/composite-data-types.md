---
title: Tipi di dati compositi (Visual Basic) | Documenti di Microsoft
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
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
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
ms.openlocfilehash: 5f0c6215ce45d724a7b5c8c4f8e34ea27bce8fe4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="8eb67-102">Tipi di dati compositi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8eb67-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="8eb67-103">Oltre ai tipi di dati elementari [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] alimentatori, è possibile unire elementi di tipi diversi per creare *tipi di dati compositi* , ad esempio classi, matrici e strutture.</span><span class="sxs-lookup"><span data-stu-id="8eb67-103">In addition to the elementary data types [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="8eb67-104">È possibile compilare i tipi di dati composti da tipi di base e da altri tipi composti.</span><span class="sxs-lookup"><span data-stu-id="8eb67-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="8eb67-105">Ad esempio, è possibile definire una matrice di elementi di struttura o una struttura con i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="8eb67-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8eb67-106">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8eb67-106">Data Types</span></span>  
 <span data-ttu-id="8eb67-107">Un tipo composito è diverso dal tipo di dati di uno qualsiasi dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="8eb67-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="8eb67-108">Ad esempio, una matrice di `Integer` elementi non è il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8eb67-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="8eb67-109">Dati di tipo matrice sono in genere rappresentato utilizzando il tipo di elemento tra parentesi e virgole in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8eb67-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="8eb67-110">Ad esempio, una matrice unidimensionale di `String` elementi viene rappresentata come `String()`e una matrice bidimensionale di `Boolean` elementi viene rappresentata come `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="8eb67-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="8eb67-111">Tipi di struttura</span><span class="sxs-lookup"><span data-stu-id="8eb67-111">Structure Types</span></span>  
 <span data-ttu-id="8eb67-112">È disponibile alcun tipo di dati singolo che comprende tutte le strutture.</span><span class="sxs-lookup"><span data-stu-id="8eb67-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="8eb67-113">Ogni definizione di una struttura rappresenta invece un tipo di dati univoco, anche se due strutture definiscono elementi identici nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="8eb67-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="8eb67-114">Tuttavia, se si creano due o più istanze della stessa struttura, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tali dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8eb67-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="array-types"></a><span data-ttu-id="8eb67-115">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="8eb67-115">Array Types</span></span>  
 <span data-ttu-id="8eb67-116">È disponibile alcun tipo di dati singolo che comprende tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="8eb67-116">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="8eb67-117">Il tipo di dati di una determinata istanza di una matrice viene determinato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8eb67-117">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="8eb67-118">Il fatto di essere una matrice</span><span class="sxs-lookup"><span data-stu-id="8eb67-118">The fact of being an array</span></span>  
  
-   <span data-ttu-id="8eb67-119">La classificazione (numero di dimensioni) della matrice</span><span class="sxs-lookup"><span data-stu-id="8eb67-119">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="8eb67-120">Il tipo di elemento della matrice</span><span class="sxs-lookup"><span data-stu-id="8eb67-120">The element type of the array</span></span>  
  
 <span data-ttu-id="8eb67-121">In particolare, la lunghezza di una dimensione specificata non fa parte del tipo di dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="8eb67-121">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="8eb67-122">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8eb67-122">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="8eb67-123">Nell'esempio precedente, le variabili di matrice `arrayA` e `arrayB` vengono considerati dello stesso tipo di dati, ovvero `Byte()` , anche se vengono inizializzate su lunghezze diverse.</span><span class="sxs-lookup"><span data-stu-id="8eb67-123">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="8eb67-124">Variabili `arrayB` e `arrayC` non sono dello stesso tipo perché i relativi tipi di elemento sono diversi.</span><span class="sxs-lookup"><span data-stu-id="8eb67-124">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="8eb67-125">Variabili `arrayC` e `arrayD` non sono dello stesso tipo perché i relativi indici sono differenti.</span><span class="sxs-lookup"><span data-stu-id="8eb67-125">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="8eb67-126">Variabili `arrayD` e `arrayE` hanno lo stesso tipo, ovvero `Short(,)` , perché le classificazioni e i tipi di elemento sono gli stessi, anche se `arrayD` non ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="8eb67-126">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="8eb67-127">Per ulteriori informazioni sulle matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8eb67-127">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="8eb67-128">Tipi di classe</span><span class="sxs-lookup"><span data-stu-id="8eb67-128">Class Types</span></span>  
 <span data-ttu-id="8eb67-129">È disponibile alcun tipo di dati singolo che comprende tutte le classi.</span><span class="sxs-lookup"><span data-stu-id="8eb67-129">There is no single data type comprising all classes.</span></span> <span data-ttu-id="8eb67-130">Sebbene una classe può ereditare da un'altra classe, ognuno è un tipo di dati separato.</span><span class="sxs-lookup"><span data-stu-id="8eb67-130">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="8eb67-131">Più istanze della stessa classe sono dello stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8eb67-131">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="8eb67-132">Se si assegna una variabile di istanza di classe a un altro, non solo sono gli stessi dati di tipo, puntano alla stessa istanza di classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="8eb67-132">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="8eb67-133">Per ulteriori informazioni sulle classi, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="8eb67-133">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb67-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eb67-134">See Also</span></span>  
 <span data-ttu-id="8eb67-135">[Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-135">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="8eb67-136"> [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-136"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="8eb67-137"> [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-137"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="8eb67-138"> [Tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-138"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="8eb67-139"> [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-139"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="8eb67-140"> [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-140"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="8eb67-141"> [Risoluzione dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8eb67-141"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="8eb67-142"> [Procedura: Inserire più valori in una variabile](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span><span class="sxs-lookup"><span data-stu-id="8eb67-142"> [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span></span>
