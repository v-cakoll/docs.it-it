---
title: Parametri facoltativi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: a438455668310769c5267a6d42a2e694bb7b01dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651609"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="d724b-102">Parametri facoltativi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d724b-102">Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="d724b-103">È possibile specificare che un parametro di routine è facoltativo e non è necessario fornire alcun argomento quando la routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="d724b-103">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="d724b-104">*Parametri facoltativi* sono indicate con la `Optional` parola chiave nella definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="d724b-104">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="d724b-105">È necessario attenersi alle regole che seguono:</span><span class="sxs-lookup"><span data-stu-id="d724b-105">The following rules apply:</span></span>  
  
-   <span data-ttu-id="d724b-106">È necessario che ciascun parametro facoltativo nella definizione della routine specifichi un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d724b-106">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
-   <span data-ttu-id="d724b-107">È necessario che tale valore predefinito per un parametro facoltativo sia un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="d724b-107">The default value for an optional parameter must be a constant expression.</span></span>  
  
-   <span data-ttu-id="d724b-108">Ciascun parametro che segue un parametro facoltativo nella definizione della routine deve essere anch'esso facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d724b-108">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="d724b-109">Nella sintassi seguente viene illustrata una dichiarazione di routine con un parametro facoltativo:</span><span class="sxs-lookup"><span data-stu-id="d724b-109">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="d724b-110">Chiamata di routine con parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="d724b-110">Calling Procedures with Optional Parameters</span></span>  
 <span data-ttu-id="d724b-111">Quando si chiama una routine con un parametro facoltativo, è possibile scegliere se fornire l'argomento o meno.</span><span class="sxs-lookup"><span data-stu-id="d724b-111">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="d724b-112">Se non lo si fornisce, la routine utilizza il valore predefinito dichiarato per quel parametro.</span><span class="sxs-lookup"><span data-stu-id="d724b-112">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="d724b-113">Quando si omettono uno o più argomenti facoltativi nell'elenco degli argomenti, utilizzare virgole in sequenza per contrassegnarne la posizione.</span><span class="sxs-lookup"><span data-stu-id="d724b-113">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="d724b-114">La chiamata di esempio che segue fornisce il primo e il quarto argomento, ma non il secondo o il terzo:</span><span class="sxs-lookup"><span data-stu-id="d724b-114">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="d724b-115">Nell'esempio riportato di seguito vengono effettuate diverse chiamate alla funzione `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="d724b-115">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="d724b-116">`MsgBox` include un parametro obbligatorio e due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d724b-116">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="d724b-117">Nella prima chiamata a `MsgBox` vengono forniti tutti e tre gli argomenti nell'ordine in cui sono definiti da `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="d724b-117">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="d724b-118">Nella seconda chiamata viene fornito solo l'argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d724b-118">The second call supplies only the required argument.</span></span> <span data-ttu-id="d724b-119">Nella terza e quarta chiamata vengono forniti il primo e il terzo argomento.</span><span class="sxs-lookup"><span data-stu-id="d724b-119">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="d724b-120">Nella terza chiamata gli argomenti vengono forniti in base alla posizione, nella quarta in base al nome.</span><span class="sxs-lookup"><span data-stu-id="d724b-120">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="d724b-121">Determinazione dell'eventuale presenza di un argomento facoltativo</span><span class="sxs-lookup"><span data-stu-id="d724b-121">Determining Whether an Optional Argument Is Present</span></span>  
 <span data-ttu-id="d724b-122">Una routine non può rilevare, in fase di esecuzione, se un determinato argomento è stato omesso o se il codice di chiamata ha fornito in modo esplicito il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d724b-122">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="d724b-123">Se è necessario fare questa distinzione, è possibile impostare come predefinito un valore improbabile.</span><span class="sxs-lookup"><span data-stu-id="d724b-123">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="d724b-124">La procedura seguente definisce il parametro facoltativo `office`e verifica il valore predefinito, `QJZ`, per vedere se è stato omesso nella chiamata:</span><span class="sxs-lookup"><span data-stu-id="d724b-124">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 <span data-ttu-id="d724b-125">Se il parametro facoltativo è un tipo di riferimento come `String`, è possibile utilizzare `Nothing` come valore predefinito, a meno che esso non sia un valore previsto per l'argomento.</span><span class="sxs-lookup"><span data-stu-id="d724b-125">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="d724b-126">Parametri facoltativi e overload</span><span class="sxs-lookup"><span data-stu-id="d724b-126">Optional Parameters and Overloading</span></span>  
 <span data-ttu-id="d724b-127">Un altro modo per definire una routine con parametri facoltativi consiste nell'utilizzare l'overload.</span><span class="sxs-lookup"><span data-stu-id="d724b-127">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="d724b-128">Nel caso di un parametro facoltativo, è possibile definire due versioni di overload della routine, una con il parametro e l'altra senza.</span><span class="sxs-lookup"><span data-stu-id="d724b-128">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="d724b-129">Questo metodo diventa più complesso con l'aumentare del numero dei parametri facoltativi,</span><span class="sxs-lookup"><span data-stu-id="d724b-129">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="d724b-130">tuttavia ha il vantaggio di assicurare che il programma di chiamata fornisca tutti gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d724b-130">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d724b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d724b-131">See Also</span></span>  
 [<span data-ttu-id="d724b-132">Routine</span><span class="sxs-lookup"><span data-stu-id="d724b-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d724b-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="d724b-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d724b-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="d724b-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d724b-135">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="d724b-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="d724b-136">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="d724b-136">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="d724b-137">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="d724b-137">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="d724b-138">Optional</span><span class="sxs-lookup"><span data-stu-id="d724b-138">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="d724b-139">ParamArray</span><span class="sxs-lookup"><span data-stu-id="d724b-139">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
