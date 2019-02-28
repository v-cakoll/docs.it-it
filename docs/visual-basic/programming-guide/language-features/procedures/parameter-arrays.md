---
title: Matrici di parametri (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: e059f471f78262320f1968c12192de710876aef4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966580"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="947c9-102">Matrici di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="947c9-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="947c9-103">In genere, non è possibile chiamare una routine con più argomenti di dichiarazione di routine specifica.</span><span class="sxs-lookup"><span data-stu-id="947c9-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="947c9-104">Quando è necessario un numero indefinito di argomenti, è possibile dichiarare un *matrice di parametri*, che consente a una routine accettare una matrice di valori per un parametro.</span><span class="sxs-lookup"><span data-stu-id="947c9-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="947c9-105">Non è necessario conoscere il numero di elementi nella matrice del parametro quando si definisce la procedura.</span><span class="sxs-lookup"><span data-stu-id="947c9-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="947c9-106">La dimensione della matrice viene determinata singolarmente per ogni chiamata alla procedura.</span><span class="sxs-lookup"><span data-stu-id="947c9-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="947c9-107">La dichiarazione di un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="947c9-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="947c9-108">Si utilizza il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) (parola chiave) per indicare una matrice di parametri nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="947c9-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="947c9-109">È necessario attenersi alle regole che seguono:</span><span class="sxs-lookup"><span data-stu-id="947c9-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="947c9-110">Una routine può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="947c9-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="947c9-111">La matrice di parametri deve essere passata per valore.</span><span class="sxs-lookup"><span data-stu-id="947c9-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="947c9-112">È buona norma includere in modo esplicito il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) parola chiave nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="947c9-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="947c9-113">La matrice di parametri è automaticamente facoltativa.</span><span class="sxs-lookup"><span data-stu-id="947c9-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="947c9-114">Il valore predefinito è una matrice unidimensionale vuota del tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="947c9-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="947c9-115">Tutti i parametri che precedono la matrice di parametri devono essere obbligatori.</span><span class="sxs-lookup"><span data-stu-id="947c9-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="947c9-116">La matrice di parametri deve essere l'unico parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="947c9-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="947c9-117">La chiamata a un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="947c9-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="947c9-118">Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="947c9-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="947c9-119">Nothing, vale a dire, è possibile omettere il [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="947c9-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="947c9-120">In questo caso, una matrice vuota viene passata alla routine.</span><span class="sxs-lookup"><span data-stu-id="947c9-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="947c9-121">È anche possibile passare il [Nothing](../../../../visual-basic/language-reference/nothing.md) (parola chiave), con lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="947c9-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="947c9-122">Elenco di un numero arbitrario di argomenti, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="947c9-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="947c9-123">Il tipo di dati di ogni argomento deve essere convertibile in modo implicito per il `ParamArray` tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="947c9-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="947c9-124">Una matrice con lo stesso tipo di elemento come tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="947c9-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="947c9-125">In tutti i casi, il codice all'interno della routine considera la matrice di parametri come una matrice unidimensionale con gli elementi dello stesso tipo di dati come il `ParamArray` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="947c9-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="947c9-126">Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="947c9-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="947c9-127">Se si accetta una matrice di parametri, è necessario testare per la dimensione della matrice che il codice chiamante è passato ad esso.</span><span class="sxs-lookup"><span data-stu-id="947c9-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="947c9-128">Se è troppo grande per l'applicazione, eseguire i passaggi appropriati.</span><span class="sxs-lookup"><span data-stu-id="947c9-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="947c9-129">Per altre informazioni, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="947c9-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="947c9-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="947c9-130">Example</span></span>  
 <span data-ttu-id="947c9-131">Nell'esempio seguente definisce e chiama la funzione `calcSum`.</span><span class="sxs-lookup"><span data-stu-id="947c9-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="947c9-132">Il `ParamArray` modificatore del parametro `args` consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="947c9-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="947c9-133">Nell'esempio seguente definisce una routine con una matrice di parametri e restituisce i valori di tutti gli elementi della matrice passati alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="947c9-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="947c9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="947c9-134">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="947c9-135">Routine</span><span class="sxs-lookup"><span data-stu-id="947c9-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="947c9-136">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="947c9-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="947c9-137">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="947c9-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="947c9-138">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="947c9-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="947c9-139">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="947c9-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="947c9-140">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="947c9-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="947c9-141">Matrici</span><span class="sxs-lookup"><span data-stu-id="947c9-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="947c9-142">Optional</span><span class="sxs-lookup"><span data-stu-id="947c9-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
