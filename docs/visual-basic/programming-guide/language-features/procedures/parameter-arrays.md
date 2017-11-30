---
title: Matrici di parametri (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ca2b5f02ac4fb3eb613488c8a9852eb2aa4ce5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="8671e-102">Matrici di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8671e-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="8671e-103">In genere, è possibile chiamare una routine con più argomenti di specifica la dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="8671e-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="8671e-104">Quando è necessario un numero indefinito di argomenti, è possibile dichiarare un *matrice di parametri*, che consente una routine di accettare una matrice di valori per un parametro.</span><span class="sxs-lookup"><span data-stu-id="8671e-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="8671e-105">Non è necessario conoscere il numero di elementi nella matrice di parametri quando si definisce la procedura.</span><span class="sxs-lookup"><span data-stu-id="8671e-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="8671e-106">Le dimensioni della matrice vengano determinata singolarmente per ogni chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="8671e-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="8671e-107">Dichiarazione di un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="8671e-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="8671e-108">Utilizzare il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) (parola chiave) per indicare una matrice di parametri nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="8671e-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="8671e-109">È necessario attenersi alle regole che seguono:</span><span class="sxs-lookup"><span data-stu-id="8671e-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="8671e-110">Una stored procedure può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="8671e-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="8671e-111">La matrice di parametri deve essere passata per valore.</span><span class="sxs-lookup"><span data-stu-id="8671e-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="8671e-112">È buona norma di programmazione includere in modo esplicito il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) parola chiave nella definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="8671e-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="8671e-113">Matrice di parametri è automaticamente facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8671e-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="8671e-114">Il valore predefinito è una matrice unidimensionale vuota di tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="8671e-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="8671e-115">Tutti i parametri che precedono la matrice di parametri devono essere obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8671e-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="8671e-116">Matrice di parametri deve essere l'unico parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8671e-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="8671e-117">La chiamata a un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="8671e-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="8671e-118">Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8671e-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="8671e-119">Nothing, vale a dire, è possibile omettere il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="8671e-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="8671e-120">In questo caso, una matrice vuota viene passata alla routine.</span><span class="sxs-lookup"><span data-stu-id="8671e-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="8671e-121">È inoltre possibile passare il [nulla](../../../../visual-basic/language-reference/nothing.md) (parola chiave), con lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="8671e-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="8671e-122">Un elenco di un numero arbitrario di argomenti, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="8671e-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="8671e-123">Il tipo di dati di ogni argomento deve essere convertibile in modo implicito il `ParamArray` tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="8671e-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="8671e-124">Una matrice con lo stesso tipo di elemento come tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="8671e-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="8671e-125">In tutti i casi, il codice all'interno della routine considera la matrice di parametri come una matrice unidimensionale con gli elementi dello stesso tipo di dati come il `ParamArray` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="8671e-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8671e-126">Ogni volta che gestisce una matrice che può essere elevata per un periodo illimitato, c'è un rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8671e-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="8671e-127">Se si accetta una matrice di parametri, è necessario verificare le dimensioni della matrice passato al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8671e-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="8671e-128">Adottare se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8671e-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="8671e-129">Per ulteriori informazioni, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8671e-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8671e-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="8671e-130">Example</span></span>  
 <span data-ttu-id="8671e-131">Nell'esempio seguente definisce e chiama la funzione `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="8671e-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="8671e-132">Il `ParamArray` modificatore per il parametro `args` consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8671e-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 <span data-ttu-id="8671e-133">Nell'esempio seguente definisce una routine con una matrice di parametri e restituisce i valori di tutti gli elementi della matrice passati alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="8671e-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8671e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8671e-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="8671e-135">Routine</span><span class="sxs-lookup"><span data-stu-id="8671e-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8671e-136">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="8671e-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8671e-137">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="8671e-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="8671e-138">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="8671e-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="8671e-139">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="8671e-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="8671e-140">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="8671e-140">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="8671e-141">Array</span><span class="sxs-lookup"><span data-stu-id="8671e-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="8671e-142">Optional</span><span class="sxs-lookup"><span data-stu-id="8671e-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
