---
title: 'Procedura: inizializzare una variabile di matrice in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3ccdbed601d3fa87acb0833bc153c199b17a4eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="1c751-102">Procedura: inizializzare una variabile di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c751-102">How to: Initialize an Array Variable in Visual Basic</span></span>
<span data-ttu-id="1c751-103">Inizializzare una variabile di matrice includendo una matrice di valori letterale in una `New` clausola e specificando i valori iniziali della matrice.</span><span class="sxs-lookup"><span data-stu-id="1c751-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="1c751-104">È possibile specificare il tipo o consentire che possa essere dedotto dai valori nel valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="1c751-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="1c751-105">Per ulteriori informazioni su come viene dedotto il tipo, vedere "Compilazione di una matrice con i valori iniziali" in [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c751-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="1c751-106">Per inizializzare una variabile di matrice con un valore letterale di matrice</span><span class="sxs-lookup"><span data-stu-id="1c751-106">To initialize an array variable by using an array literal</span></span>  
  
-   <span data-ttu-id="1c751-107">Nel `New` clausola, o quando si assegna il valore di matrice, specificare i valori degli elementi tra parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="1c751-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="1c751-108">L'esempio seguente mostra i diversi modi per dichiarare, creare e inizializzare una variabile per contenere una matrice che contiene elementi di tipo `Char`.</span><span class="sxs-lookup"><span data-stu-id="1c751-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     <span data-ttu-id="1c751-109">Dopo l'esecuzione di ogni istruzione, la matrice che viene creata avrà una lunghezza pari a 3, con gli elementi in corrispondenza dell'indice 0 e l'indice 2 contenente i valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="1c751-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="1c751-110">Se si specificano sia il limite superiore che i valori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore.</span><span class="sxs-lookup"><span data-stu-id="1c751-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="1c751-111">Si noti che non è necessario specificare il limite superiore dell'indice, se si specificano valori di elemento in un valore letterale della matrice.</span><span class="sxs-lookup"><span data-stu-id="1c751-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="1c751-112">Se non viene specificato alcun limite superiore, le dimensioni della matrice viene dedotto in base al numero di valori nel valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="1c751-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="1c751-113">Per inizializzare una variabile di matrice multidimensionale tramite valori letterali di matrice</span><span class="sxs-lookup"><span data-stu-id="1c751-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
-   <span data-ttu-id="1c751-114">Annidare i valori tra parentesi graffe (`{}`) all'interno delle parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="1c751-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="1c751-115">Verificare che i valori letterali di matrice annidati che tutti dedotti come matrici dello stesso tipo e lunghezza.</span><span class="sxs-lookup"><span data-stu-id="1c751-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="1c751-116">Esempio di codice seguente mostra alcuni esempi di inizializzazione di matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="1c751-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   <span data-ttu-id="1c751-117">In modo esplicito, è possibile specificare i limiti della matrice o lasciarli e che il compilatore di dedurre il tipo di matrice in base ai valori nel valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="1c751-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="1c751-118">Se si fornisce i valori e i limiti superiori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore di ogni dimensione.</span><span class="sxs-lookup"><span data-stu-id="1c751-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="1c751-119">L'esempio seguente mostra i diversi modi per dichiarare, creare e inizializzare una variabile per contenere una matrice bidimensionale con elementi di tipo`Short`</span><span class="sxs-lookup"><span data-stu-id="1c751-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     <span data-ttu-id="1c751-120">Dopo l'esecuzione di ogni istruzione, la matrice creata contiene sei elementi inizializzati con gli indici `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, e `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="1c751-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="1c751-121">Ogni posizione della matrice contiene il valore `10`.</span><span class="sxs-lookup"><span data-stu-id="1c751-121">Each array location contains the value `10`.</span></span>  
  
-   <span data-ttu-id="1c751-122">Nell'esempio seguente viene eseguito lo scorrimento di una matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="1c751-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="1c751-123">In un'applicazione console di Windows che viene scritto in Visual Basic, incollare il codice all'interno di `Sub Main()` metodo.</span><span class="sxs-lookup"><span data-stu-id="1c751-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="1c751-124">I commenti ultimo mostrano l'output.</span><span class="sxs-lookup"><span data-stu-id="1c751-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="1c751-125">Per inizializzare una variabile di matrice di matrici mediante valori letterali di matrice</span><span class="sxs-lookup"><span data-stu-id="1c751-125">To initialize a jagged array variable by using array literals</span></span>  
  
-   <span data-ttu-id="1c751-126">Annidare i valori di oggetto tra parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="1c751-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="1c751-127">Anche se è inoltre possibile annidare i valori letterali di matrice che specificano matrici di lunghezza diversa, nel caso di una matrice di matrici, assicurarsi che i valori letterali di matrice annidati vengono racchiusi tra parentesi (`()`).</span><span class="sxs-lookup"><span data-stu-id="1c751-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="1c751-128">Le parentesi forzano la valutazione dei valori letterali di matrice annidati e le matrici risultanti vengono utilizzate come i valori iniziali della matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="1c751-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="1c751-129">Esempio di codice seguente mostra due esempi di inizializzazione di matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="1c751-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   <span data-ttu-id="1c751-130">Nell'esempio seguente viene eseguito lo scorrimento di una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="1c751-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="1c751-131">In un'applicazione console di Windows che viene scritto in Visual Basic, incollare il codice all'interno di `Sub Main()` metodo.</span><span class="sxs-lookup"><span data-stu-id="1c751-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="1c751-132">L'ultimo commenti nel codice viene illustrato l'output.</span><span class="sxs-lookup"><span data-stu-id="1c751-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1c751-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c751-133">See Also</span></span>  
 [<span data-ttu-id="1c751-134">Array</span><span class="sxs-lookup"><span data-stu-id="1c751-134">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="1c751-135">Risoluzione dei problemi relativi alle matrici</span><span class="sxs-lookup"><span data-stu-id="1c751-135">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
