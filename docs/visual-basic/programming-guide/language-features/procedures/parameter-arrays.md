---
title: Matrici di parametri
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
ms.openlocfilehash: dac0575d73ffd4159e89bff344915a33b9d0e5d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364279"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="bc782-102">Matrici di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc782-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="bc782-103">In genere, non è possibile chiamare una routine con più argomenti rispetto a quanto specificato nella dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="bc782-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="bc782-104">Quando è necessario un numero indefinito di argomenti, è possibile dichiarare una *matrice di parametri*, che consente a una routine di accettare una matrice di valori per un parametro.</span><span class="sxs-lookup"><span data-stu-id="bc782-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="bc782-105">Non è necessario individuare il numero di elementi nella matrice di parametri quando si definisce la procedura.</span><span class="sxs-lookup"><span data-stu-id="bc782-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="bc782-106">La dimensione della matrice viene determinata singolarmente da ogni chiamata alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bc782-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="bc782-107">Dichiarazione di un ParamArray</span><span class="sxs-lookup"><span data-stu-id="bc782-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="bc782-108">Usare la parola chiave [ParamArray](../../../language-reference/modifiers/paramarray.md) per indicare una matrice di parametri nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="bc782-108">You use the [ParamArray](../../../language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="bc782-109">Sono applicabili le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc782-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="bc782-110">Una routine può definire solo una matrice di parametri e deve essere l'ultimo parametro nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="bc782-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="bc782-111">La matrice di parametri deve essere passata per valore.</span><span class="sxs-lookup"><span data-stu-id="bc782-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="bc782-112">È consigliabile includere in modo esplicito la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="bc782-112">It is good programming practice to explicitly include the [ByVal](../../../language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="bc782-113">La matrice di parametri è automaticamente facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bc782-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="bc782-114">Il valore predefinito è una matrice unidimensionale vuota del tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="bc782-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="bc782-115">Tutti i parametri che precedono la matrice di parametri devono essere obbligatori.</span><span class="sxs-lookup"><span data-stu-id="bc782-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="bc782-116">La matrice di parametri deve essere l'unico parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bc782-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="bc782-117">Chiamata di un ParamArray</span><span class="sxs-lookup"><span data-stu-id="bc782-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="bc782-118">Quando si chiama una routine che definisce una matrice di parametri, è possibile fornire l'argomento in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc782-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="bc782-119">Niente, ovvero è possibile omettere l'argomento [ParamArray](../../../language-reference/modifiers/paramarray.md) .</span><span class="sxs-lookup"><span data-stu-id="bc782-119">Nothing — that is, you can omit the [ParamArray](../../../language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="bc782-120">In questo caso, alla routine viene passata una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="bc782-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="bc782-121">Se si passa in modo esplicito la parola chiave [Nothing](../../../language-reference/nothing.md) , alla routine viene passata una matrice null e può verificarsi un'eccezione NullReferenceException se la routine chiamata non verifica questa condizione.</span><span class="sxs-lookup"><span data-stu-id="bc782-121">If you explicitly pass the [Nothing](../../../language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="bc782-122">Elenco di un numero arbitrario di argomenti, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="bc782-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="bc782-123">Il tipo di dati di ogni argomento deve essere convertibile in modo implicito nel `ParamArray` tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="bc782-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="bc782-124">Matrice con lo stesso tipo di elemento del tipo di elemento della matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="bc782-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="bc782-125">In tutti i casi, il codice all'interno della routine considera la matrice di parametri come matrice unidimensionale con elementi dello stesso tipo di dati del `ParamArray` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="bc782-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bc782-126">Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc782-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="bc782-127">Se si accetta una matrice di parametri, è necessario verificare la dimensione della matrice passata al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="bc782-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="bc782-128">Eseguire le operazioni appropriate se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc782-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="bc782-129">Per altre informazioni, vedere [Matrici](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc782-129">For more information, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc782-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc782-130">Example</span></span>  
 <span data-ttu-id="bc782-131">Nell'esempio seguente viene definita e chiamata la funzione `calcSum` .</span><span class="sxs-lookup"><span data-stu-id="bc782-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="bc782-132">Il `ParamArray` modificatore per il parametro `args` consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="bc782-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="bc782-133">Nell'esempio seguente viene definita una procedura con una matrice di parametri e vengono restituiti i valori di tutti gli elementi della matrice passati alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="bc782-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="bc782-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc782-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="bc782-135">Procedure</span><span class="sxs-lookup"><span data-stu-id="bc782-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bc782-136">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="bc782-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bc782-137">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="bc782-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="bc782-138">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="bc782-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="bc782-139">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="bc782-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="bc782-140">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="bc782-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="bc782-141">Matrici</span><span class="sxs-lookup"><span data-stu-id="bc782-141">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="bc782-142">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="bc782-142">Optional</span></span>](../../../language-reference/modifiers/optional.md)
