---
title: Conversioni di matrici (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 93e6365a70f52f730b016cd4d4ac9382baeeba55
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255150"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="b29d0-102">Conversioni di matrici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b29d0-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="b29d0-103">È possibile convertire un tipo di matrice a un tipo di matrice diversa purché si soddisfino le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b29d0-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="b29d0-104">**Numero di dimensioni uguale.**</span><span class="sxs-lookup"><span data-stu-id="b29d0-104">**Equal Rank.**</span></span> <span data-ttu-id="b29d0-105">Le classificazioni delle due matrici devono essere lo stesso, vale a dire deve avere lo stesso numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b29d0-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="b29d0-106">Tuttavia, le lunghezze delle rispettive dimensioni non sono necessario essere lo stesso.</span><span class="sxs-lookup"><span data-stu-id="b29d0-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="b29d0-107">**Tipo di dati elemento.**</span><span class="sxs-lookup"><span data-stu-id="b29d0-107">**Element Data Type.**</span></span> <span data-ttu-id="b29d0-108">I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b29d0-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="b29d0-109">Non è possibile convertire un' `Integer` matrice per un `Long` della matrice, o anche a un `Object` della matrice, in quanto è coinvolta in almeno un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="b29d0-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="b29d0-110">Per altre informazioni, vedere [tipi di valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="b29d0-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="b29d0-111">**Convertibilità della varianza.**</span><span class="sxs-lookup"><span data-stu-id="b29d0-111">**Convertibility.**</span></span> <span data-ttu-id="b29d0-112">Una conversione widening o narrowing, deve essere possibile tra i tipi di elementi delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="b29d0-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="b29d0-113">Un esempio che questo requisito non è un tentativo di conversione tra una `String` matrice e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b29d0-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b29d0-114">Questi due tipi presentano nulla in comune e non esiste alcuna conversione di qualsiasi tipo tra di essi.</span><span class="sxs-lookup"><span data-stu-id="b29d0-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="b29d0-115">Una conversione del tipo di una matrice a un altro è widening o narrowing a seconda se la conversione degli elementi rispettivi widening o narrowing.</span><span class="sxs-lookup"><span data-stu-id="b29d0-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="b29d0-116">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="b29d0-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="b29d0-117">Conversione a una matrice di oggetti</span><span class="sxs-lookup"><span data-stu-id="b29d0-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="b29d0-118">Quando si dichiara un `Object` matrice senza inizializzazione, il tipo di elemento è `Object` purché rimane non inizializzata.</span><span class="sxs-lookup"><span data-stu-id="b29d0-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="b29d0-119">Se si imposta in una matrice di una classe specifica, assume il tipo di tale classe.</span><span class="sxs-lookup"><span data-stu-id="b29d0-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="b29d0-120">Tuttavia, il relativo tipo sottostante è ancora `Object`, ed è possibile impostarlo successivamente in un'altra matrice di una classe non correlata.</span><span class="sxs-lookup"><span data-stu-id="b29d0-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="b29d0-121">Poiché tutte le classi di derivano da `Object`, è possibile modificare il tipo di elemento della matrice da una classe a qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="b29d0-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="b29d0-122">Nell'esempio seguente, non esiste alcuna conversione tra tipi `student` e `String`, ma entrambi derivano da `Object`, in modo che tutte le assegnazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="b29d0-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="b29d0-123">Tipo sottostante di una matrice</span><span class="sxs-lookup"><span data-stu-id="b29d0-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="b29d0-124">Se inizialmente si dichiara una matrice con una classe specifica, il relativo tipo di elemento sottostante è quella classe.</span><span class="sxs-lookup"><span data-stu-id="b29d0-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="b29d0-125">Se è impostarlo successivamente in una matrice di un'altra classe, deve esistere una conversione tra le due classi.</span><span class="sxs-lookup"><span data-stu-id="b29d0-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="b29d0-126">Nell'esempio riportato di seguito `students` è un `student` matrice.</span><span class="sxs-lookup"><span data-stu-id="b29d0-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="b29d0-127">Poiché non esiste alcuna conversione tra `String` e `student`, l'ultima istruzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b29d0-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="b29d0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b29d0-128">See Also</span></span>  
 [<span data-ttu-id="b29d0-129">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="b29d0-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="b29d0-130">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b29d0-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="b29d0-131">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="b29d0-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="b29d0-132">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="b29d0-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="b29d0-133">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b29d0-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="b29d0-134">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="b29d0-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="b29d0-135">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="b29d0-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="b29d0-136">Array</span><span class="sxs-lookup"><span data-stu-id="b29d0-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
