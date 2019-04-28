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
ms.openlocfilehash: 4ae2366552426af0107c8d7a35bb5368fe30c8a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791963"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="658a8-102">Parametri facoltativi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="658a8-102">Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="658a8-103">È possibile specificare che un parametro di routine è facoltativo e non è necessario fornire alcun argomento quando la routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="658a8-103">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="658a8-104">*I parametri facoltativi* sono indicate dal `Optional` parola chiave nella definizione della procedura.</span><span class="sxs-lookup"><span data-stu-id="658a8-104">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="658a8-105">È necessario attenersi alle regole che seguono:</span><span class="sxs-lookup"><span data-stu-id="658a8-105">The following rules apply:</span></span>  
  
- <span data-ttu-id="658a8-106">È necessario che ciascun parametro facoltativo nella definizione della routine specifichi un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="658a8-106">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
- <span data-ttu-id="658a8-107">È necessario che tale valore predefinito per un parametro facoltativo sia un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="658a8-107">The default value for an optional parameter must be a constant expression.</span></span>  
  
- <span data-ttu-id="658a8-108">Ciascun parametro che segue un parametro facoltativo nella definizione della routine deve essere anch'esso facoltativo.</span><span class="sxs-lookup"><span data-stu-id="658a8-108">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="658a8-109">Nella sintassi seguente viene illustrata una dichiarazione di routine con un parametro facoltativo:</span><span class="sxs-lookup"><span data-stu-id="658a8-109">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="658a8-110">Chiamata di routine con parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="658a8-110">Calling Procedures with Optional Parameters</span></span>  
 <span data-ttu-id="658a8-111">Quando si chiama una routine con un parametro facoltativo, è possibile scegliere se fornire l'argomento o meno.</span><span class="sxs-lookup"><span data-stu-id="658a8-111">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="658a8-112">Se non lo si fornisce, la routine utilizza il valore predefinito dichiarato per quel parametro.</span><span class="sxs-lookup"><span data-stu-id="658a8-112">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="658a8-113">Quando si omettono uno o più argomenti facoltativi nell'elenco degli argomenti, utilizzare virgole in sequenza per contrassegnarne la posizione.</span><span class="sxs-lookup"><span data-stu-id="658a8-113">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="658a8-114">La chiamata di esempio che segue fornisce il primo e il quarto argomento, ma non il secondo o il terzo:</span><span class="sxs-lookup"><span data-stu-id="658a8-114">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="658a8-115">Nell'esempio riportato di seguito vengono effettuate diverse chiamate alla funzione `MsgBox`</span><span class="sxs-lookup"><span data-stu-id="658a8-115">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="658a8-116">`MsgBox` include un parametro obbligatorio e due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="658a8-116">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="658a8-117">Nella prima chiamata a `MsgBox` vengono forniti tutti e tre gli argomenti nell'ordine in cui sono definiti da `MsgBox`.</span><span class="sxs-lookup"><span data-stu-id="658a8-117">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="658a8-118">Nella seconda chiamata viene fornito solo l'argomento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="658a8-118">The second call supplies only the required argument.</span></span> <span data-ttu-id="658a8-119">Nella terza e quarta chiamata vengono forniti il primo e il terzo argomento.</span><span class="sxs-lookup"><span data-stu-id="658a8-119">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="658a8-120">Nella terza chiamata gli argomenti vengono forniti in base alla posizione, nella quarta in base al nome.</span><span class="sxs-lookup"><span data-stu-id="658a8-120">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#47)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="658a8-121">Determinazione dell'eventuale presenza di un argomento facoltativo</span><span class="sxs-lookup"><span data-stu-id="658a8-121">Determining Whether an Optional Argument Is Present</span></span>  
 <span data-ttu-id="658a8-122">Una routine non può rilevare, in fase di esecuzione, se un determinato argomento è stato omesso o se il codice di chiamata ha fornito in modo esplicito il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="658a8-122">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="658a8-123">Se è necessario fare questa distinzione, è possibile impostare come predefinito un valore improbabile.</span><span class="sxs-lookup"><span data-stu-id="658a8-123">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="658a8-124">La procedura seguente definisce il parametro facoltativo `office`e ne verifica il valore predefinito, `QJZ`, per vedere se è stato omesso nella chiamata:</span><span class="sxs-lookup"><span data-stu-id="658a8-124">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#46)]  
  
 <span data-ttu-id="658a8-125">Se il parametro facoltativo è un tipo di riferimento come `String`, è possibile utilizzare `Nothing` come valore predefinito, a meno che esso non sia un valore previsto per l'argomento.</span><span class="sxs-lookup"><span data-stu-id="658a8-125">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="658a8-126">Parametri facoltativi e overload</span><span class="sxs-lookup"><span data-stu-id="658a8-126">Optional Parameters and Overloading</span></span>  
 <span data-ttu-id="658a8-127">Un altro modo per definire una routine con parametri facoltativi consiste nell'utilizzare l'overload.</span><span class="sxs-lookup"><span data-stu-id="658a8-127">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="658a8-128">Nel caso di un parametro facoltativo, è possibile definire due versioni di overload della routine, una con il parametro e l'altra senza.</span><span class="sxs-lookup"><span data-stu-id="658a8-128">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="658a8-129">Questo metodo diventa più complesso con l'aumentare del numero dei parametri facoltativi,</span><span class="sxs-lookup"><span data-stu-id="658a8-129">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="658a8-130">tuttavia ha il vantaggio di assicurare che il programma di chiamata fornisca tutti gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="658a8-130">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658a8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="658a8-131">See also</span></span>

- [<span data-ttu-id="658a8-132">Routine</span><span class="sxs-lookup"><span data-stu-id="658a8-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="658a8-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="658a8-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="658a8-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="658a8-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="658a8-135">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="658a8-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="658a8-136">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="658a8-136">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="658a8-137">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="658a8-137">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="658a8-138">Optional</span><span class="sxs-lookup"><span data-stu-id="658a8-138">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="658a8-139">ParamArray</span><span class="sxs-lookup"><span data-stu-id="658a8-139">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
