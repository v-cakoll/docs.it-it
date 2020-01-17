---
title: Sub (routine)
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
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163813"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="6fce1-102">Procedure secondarie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fce1-102">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="6fce1-103">Una `Sub` routine è una serie di istruzioni Visual Basic racchiuse tra le istruzioni `Sub` e `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="6fce1-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="6fce1-104">La procedura `Sub` esegue un'attività e quindi restituisce il controllo al codice chiamante, ma non restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fce1-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="6fce1-105">Ogni volta che viene chiamata la stored procedure, le istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo l'istruzione `Sub` e terminando con la prima istruzione `End Sub`, `Exit Sub`o `Return` rilevata.</span><span class="sxs-lookup"><span data-stu-id="6fce1-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="6fce1-106">È possibile definire una procedura di `Sub` in moduli, classi e strutture.</span><span class="sxs-lookup"><span data-stu-id="6fce1-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="6fce1-107">Per impostazione predefinita, è `Public`, quindi è possibile chiamarlo da qualsiasi punto dell'applicazione che abbia accesso al modulo, alla classe o alla struttura in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="6fce1-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="6fce1-108">Il termine *Metodo* descrive un `Sub` o `Function` routine a cui si accede dall'esterno del modulo, della classe o della struttura che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="6fce1-108">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="6fce1-109">Per altre informazioni, vedere [Routine](./index.md).</span><span class="sxs-lookup"><span data-stu-id="6fce1-109">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="6fce1-110">Una procedura `Sub` può assumere argomenti, ad esempio costanti, variabili o espressioni, che vengono passati al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fce1-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="6fce1-111">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="6fce1-111">Declaration syntax</span></span>

<span data-ttu-id="6fce1-112">La sintassi per la dichiarazione di una procedura `Sub` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6fce1-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="6fce1-113">Il `modifiers` può specificare il livello di accesso e le informazioni sull'overload, l'override, la condivisione e l'ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="6fce1-113">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="6fce1-114">Per ulteriori informazioni, vedere [istruzione secondaria](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6fce1-114">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="6fce1-115">Dichiarazione di parametro</span><span class="sxs-lookup"><span data-stu-id="6fce1-115">Parameter declaration</span></span>

<span data-ttu-id="6fce1-116">Dichiarare ogni parametro di routine in modo analogo a come si dichiara una variabile, specificando il nome del parametro e il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="6fce1-116">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="6fce1-117">È anche possibile specificare il meccanismo di passaggio e se il parametro è facoltativo o una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="6fce1-117">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="6fce1-118">La sintassi per ogni parametro nell'elenco di parametri è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6fce1-118">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="6fce1-119">Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="6fce1-119">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="6fce1-120">La sintassi per specificare un valore predefinito è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6fce1-120">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="6fce1-121">Parametri come variabili locali</span><span class="sxs-lookup"><span data-stu-id="6fce1-121">Parameters as local variables</span></span>

<span data-ttu-id="6fce1-122">Quando il controllo passa alla routine, ogni parametro viene considerato come variabile locale.</span><span class="sxs-lookup"><span data-stu-id="6fce1-122">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="6fce1-123">Ciò significa che la durata è identica a quella della procedura e il suo ambito è l'intera routine.</span><span class="sxs-lookup"><span data-stu-id="6fce1-123">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="6fce1-124">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="6fce1-124">Calling syntax</span></span>

<span data-ttu-id="6fce1-125">Si richiama in modo esplicito una routine di `Sub` con un'istruzione di chiamata autonoma.</span><span class="sxs-lookup"><span data-stu-id="6fce1-125">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="6fce1-126">Non è possibile chiamarlo utilizzandone il nome in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="6fce1-126">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="6fce1-127">È necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="6fce1-127">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="6fce1-128">Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="6fce1-128">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="6fce1-129">L'uso della parola chiave `Call` è facoltativo ma non consigliato.</span><span class="sxs-lookup"><span data-stu-id="6fce1-129">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="6fce1-130">La sintassi per una chiamata a una procedura `Sub` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6fce1-130">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="6fce1-131">È possibile chiamare un metodo di `Sub` dall'esterno della classe che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="6fce1-131">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="6fce1-132">Prima di tutto, è necessario usare la parola chiave `New` per creare un'istanza della classe o chiamare un metodo che restituisce un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="6fce1-132">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="6fce1-133">Per ulteriori informazioni, vedere [operatore New](../../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6fce1-133">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="6fce1-134">Quindi, è possibile utilizzare la sintassi seguente per chiamare il metodo `Sub` sull'oggetto istanza:</span><span class="sxs-lookup"><span data-stu-id="6fce1-134">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="6fce1-135">Illustrazione della dichiarazione e della chiamata</span><span class="sxs-lookup"><span data-stu-id="6fce1-135">Illustration of declaration and call</span></span>

<span data-ttu-id="6fce1-136">La seguente procedura `Sub` indica all'operatore computer l'attività che l'applicazione sta per eseguire e visualizza anche un timestamp.</span><span class="sxs-lookup"><span data-stu-id="6fce1-136">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="6fce1-137">Anziché duplicare questo codice all'inizio di ogni attività, l'applicazione chiama solo `tellOperator` da diverse posizioni.</span><span class="sxs-lookup"><span data-stu-id="6fce1-137">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="6fce1-138">Ogni chiamata passa una stringa nell'argomento `task` che identifica l'attività avviata.</span><span class="sxs-lookup"><span data-stu-id="6fce1-138">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="6fce1-139">Nell'esempio seguente viene illustrata una tipica chiamata a `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="6fce1-139">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="6fce1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fce1-140">See also</span></span>

- [<span data-ttu-id="6fce1-141">Routine</span><span class="sxs-lookup"><span data-stu-id="6fce1-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6fce1-142">Routine Function</span><span class="sxs-lookup"><span data-stu-id="6fce1-142">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="6fce1-143">Routine Property</span><span class="sxs-lookup"><span data-stu-id="6fce1-143">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6fce1-144">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="6fce1-144">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="6fce1-145">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="6fce1-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6fce1-146">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="6fce1-146">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="6fce1-147">Procedura: Chiamare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="6fce1-147">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="6fce1-148">Procedura: chiamare un gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fce1-148">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
