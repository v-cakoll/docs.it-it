---
title: Routine Sub (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 646d7d217891dc8ea5b78f7ce30fce19fab08316
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977578"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="f28ce-102">Routine Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f28ce-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="f28ce-103">Oggetto `Sub` routine è una serie di istruzioni di Visual Basic racchiuse tra il `Sub` e `End Sub` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f28ce-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="f28ce-104">Il `Sub` routine esegue un'attività e quindi restituisce il controllo al codice chiamante, ma non viene restituito un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="f28ce-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="f28ce-105">Ogni volta che la procedura viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Sub` istruzione e terminando con il primo `End Sub`, `Exit Sub`, o `Return` rilevata istruzione.</span><span class="sxs-lookup"><span data-stu-id="f28ce-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="f28ce-106">È possibile definire un `Sub` procedura in moduli, le classi e strutture.</span><span class="sxs-lookup"><span data-stu-id="f28ce-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="f28ce-107">Per impostazione predefinita, questo file è `Public`, ovvero è possibile chiamarlo da qualsiasi posizione nell'applicazione che dispone dell'accesso per il modulo, classe o struttura in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="f28ce-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="f28ce-108">Il termine *metodo*, viene descritto un `Sub` o `Function` procedure che si accede dall'esterno la definizione di modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="f28ce-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="f28ce-109">Per altre informazioni, vedere [Routine](./index.md).</span><span class="sxs-lookup"><span data-stu-id="f28ce-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="f28ce-110">Oggetto `Sub` procedure può accettare argomenti, ad esempio le costanti, variabili o espressioni che vengono passate al metodo dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="f28ce-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="f28ce-111">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="f28ce-111">Declaration Syntax</span></span>  
 <span data-ttu-id="f28ce-112">La sintassi per dichiarare un `Sub` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f28ce-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="f28ce-113">`[` *i modificatori* `] Sub` *subname* `[(` *elencoparametri* `)]`</span><span class="sxs-lookup"><span data-stu-id="f28ce-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="f28ce-114">Il `modifiers` può specificare il livello di accesso e le informazioni su l'overload, si esegue l'override, la condivisione e lo shadowing.</span><span class="sxs-lookup"><span data-stu-id="f28ce-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="f28ce-115">Per altre informazioni, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f28ce-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="f28ce-116">Dichiarazione di parametro</span><span class="sxs-lookup"><span data-stu-id="f28ce-116">Parameter Declaration</span></span>  
 <span data-ttu-id="f28ce-117">Ogni parametro di procedura in modo analogo al modo in cui si dichiara una variabile, che specifica il tipo di dati e nome del parametro viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="f28ce-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="f28ce-118">È anche possibile specificare il meccanismo di passaggio e indica se il parametro è facoltativo o una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="f28ce-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="f28ce-119">La sintassi per ogni parametro nell'elenco dei parametri è come segue:</span><span class="sxs-lookup"><span data-stu-id="f28ce-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="f28ce-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*datatype*</span><span class="sxs-lookup"><span data-stu-id="f28ce-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="f28ce-121">Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f28ce-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="f28ce-122">La sintassi per specificare un valore predefinito è come segue:</span><span class="sxs-lookup"><span data-stu-id="f28ce-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="f28ce-123">`Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="f28ce-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="f28ce-124">Parametri come variabili locali</span><span class="sxs-lookup"><span data-stu-id="f28ce-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="f28ce-125">Quando il controllo passa alla procedura, ogni parametro viene considerato come una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="f28ce-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="f28ce-126">Ciò significa che la sua durata è uguale a quello della procedura e il relativo ambito è l'intera procedura.</span><span class="sxs-lookup"><span data-stu-id="f28ce-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="f28ce-127">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="f28ce-127">Calling Syntax</span></span>  
 <span data-ttu-id="f28ce-128">Si richiama un `Sub` procedure in modo esplicito con un'istruzione di chiamata autonoma.</span><span class="sxs-lookup"><span data-stu-id="f28ce-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="f28ce-129">È possibile effettuare la chiamata utilizzando il nome in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f28ce-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="f28ce-130">È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="f28ce-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="f28ce-131">Se viene fornito alcun argomento, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="f28ce-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="f28ce-132">L'uso del `Call` la parola chiave è facoltativa, ma non consigliata.</span><span class="sxs-lookup"><span data-stu-id="f28ce-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="f28ce-133">La sintassi per una chiamata a un `Sub` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f28ce-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="f28ce-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="f28ce-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="f28ce-135">È possibile chiamare un `Sub` metodo dall'esterno della classe che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="f28ce-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="f28ce-136">In primo luogo, è necessario utilizzare il `New` (parola chiave) per creare un'istanza della classe o chiama un metodo che restituisce un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="f28ce-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="f28ce-137">Per altre informazioni, vedere [operatore New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f28ce-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="f28ce-138">Quindi, è possibile usare la sintassi seguente per chiamare il `Sub` metodo sull'oggetto dell'istanza:</span><span class="sxs-lookup"><span data-stu-id="f28ce-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="f28ce-139">*Oggetto*. *MethodName*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="f28ce-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="f28ce-140">Illustrazione di dichiarazione e di chiamata</span><span class="sxs-lookup"><span data-stu-id="f28ce-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="f28ce-141">Nell'esempio `Sub` procedure indica a quale attività l'applicazione sta per eseguire, l'operatore di computer e visualizza inoltre un timestamp.</span><span class="sxs-lookup"><span data-stu-id="f28ce-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="f28ce-142">Anziché ripetere questo codice all'inizio di ogni attività, l'applicazione chiama semplicemente `tellOperator` da diverse posizioni.</span><span class="sxs-lookup"><span data-stu-id="f28ce-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="f28ce-143">Ogni chiamata passa una stringa nel `task` argomento che identifica l'attività in corso l'avvio.</span><span class="sxs-lookup"><span data-stu-id="f28ce-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="f28ce-144">Nell'esempio seguente viene illustrata una tipica chiamata alla `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="f28ce-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f28ce-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f28ce-145">See also</span></span>
- [<span data-ttu-id="f28ce-146">Routine</span><span class="sxs-lookup"><span data-stu-id="f28ce-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f28ce-147">Routine Function</span><span class="sxs-lookup"><span data-stu-id="f28ce-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="f28ce-148">Routine Property</span><span class="sxs-lookup"><span data-stu-id="f28ce-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="f28ce-149">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f28ce-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f28ce-150">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="f28ce-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f28ce-151">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f28ce-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f28ce-152">Procedura: Chiamare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="f28ce-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="f28ce-153">Procedura: Chiamare un gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28ce-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
