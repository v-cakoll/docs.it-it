---
title: Conversioni di matrice
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
ms.openlocfilehash: 1d20b01200d3f967e3355dc6e9651291003d140e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402005"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="43d3d-102">Conversioni di matrici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43d3d-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="43d3d-103">È possibile convertire un tipo di matrice in un tipo di matrice diverso purché si soddisfino le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43d3d-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="43d3d-104">**Rango uguale.**</span><span class="sxs-lookup"><span data-stu-id="43d3d-104">**Equal Rank.**</span></span> <span data-ttu-id="43d3d-105">Le classificazioni delle due matrici devono essere uguali, ovvero devono avere lo stesso numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="43d3d-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="43d3d-106">Tuttavia, non è necessario che le lunghezze delle rispettive dimensioni siano uguali.</span><span class="sxs-lookup"><span data-stu-id="43d3d-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="43d3d-107">**Tipo di dati dell'elemento.**</span><span class="sxs-lookup"><span data-stu-id="43d3d-107">**Element Data Type.**</span></span> <span data-ttu-id="43d3d-108">I tipi di dati degli elementi di entrambe le matrici devono essere tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="43d3d-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="43d3d-109">Non è possibile convertire una `Integer` matrice in una matrice `Long` o anche in una `Object` matrice perché è necessario almeno un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="43d3d-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="43d3d-110">Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="43d3d-110">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="43d3d-111">**Convertibilità della.**</span><span class="sxs-lookup"><span data-stu-id="43d3d-111">**Convertibility.**</span></span> <span data-ttu-id="43d3d-112">È necessario che sia possibile eseguire una conversione verso un tipo di ingrandimento o una riduzione tra i tipi di elemento delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="43d3d-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="43d3d-113">Un esempio in cui si verifica un errore di questo requisito è un tentativo di conversione tra una `String` matrice e una matrice di una classe derivata da <xref:System.Attribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="43d3d-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43d3d-114">Questi due tipi non hanno nulla in comune e non esiste alcuna conversione di alcun tipo.</span><span class="sxs-lookup"><span data-stu-id="43d3d-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="43d3d-115">Una conversione di un tipo di matrice in un altro viene ampliata o ristretta a seconda che la conversione dei rispettivi elementi sia allargata o ridotta.</span><span class="sxs-lookup"><span data-stu-id="43d3d-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="43d3d-116">Per altre informazioni, vedere [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="43d3d-116">For more information, see [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="43d3d-117">Conversione in una matrice di oggetti</span><span class="sxs-lookup"><span data-stu-id="43d3d-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="43d3d-118">Quando si dichiara una `Object` matrice senza inizializzarla, il relativo tipo di elemento è purché `Object` rimanga non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="43d3d-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="43d3d-119">Quando lo si imposta su una matrice di una classe specifica, viene utilizzato il tipo di tale classe.</span><span class="sxs-lookup"><span data-stu-id="43d3d-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="43d3d-120">Tuttavia, il tipo sottostante è ancora `Object` e successivamente è possibile impostarlo su un'altra matrice di una classe non correlata.</span><span class="sxs-lookup"><span data-stu-id="43d3d-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="43d3d-121">Poiché tutte le classi derivano da `Object` , è possibile modificare il tipo di elemento della matrice da qualsiasi classe a qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="43d3d-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="43d3d-122">Nell'esempio seguente non esiste alcuna conversione tra i tipi `student` e `String` , ma entrambi derivano da `Object` , quindi tutte le assegnazioni sono valide.</span><span class="sxs-lookup"><span data-stu-id="43d3d-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="43d3d-123">Tipo sottostante di una matrice</span><span class="sxs-lookup"><span data-stu-id="43d3d-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="43d3d-124">Se si dichiara originariamente una matrice con una classe specifica, il relativo tipo di elemento sottostante è tale classe.</span><span class="sxs-lookup"><span data-stu-id="43d3d-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="43d3d-125">Se successivamente lo si imposta su una matrice di un'altra classe, è necessario eseguire una conversione tra le due classi.</span><span class="sxs-lookup"><span data-stu-id="43d3d-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="43d3d-126">Nell'esempio seguente `students` è una `student` matrice.</span><span class="sxs-lookup"><span data-stu-id="43d3d-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="43d3d-127">Poiché non esiste alcuna conversione tra `String` e `student` , l'ultima istruzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="43d3d-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="43d3d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43d3d-128">See also</span></span>

- [<span data-ttu-id="43d3d-129">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="43d3d-129">Data Types</span></span>](index.md)
- [<span data-ttu-id="43d3d-130">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43d3d-130">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="43d3d-131">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="43d3d-131">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="43d3d-132">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="43d3d-132">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="43d3d-133">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43d3d-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="43d3d-134">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="43d3d-134">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="43d3d-135">CString</span><span class="sxs-lookup"><span data-stu-id="43d3d-135">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="43d3d-136">Matrici</span><span class="sxs-lookup"><span data-stu-id="43d3d-136">Arrays</span></span>](../arrays/index.md)
