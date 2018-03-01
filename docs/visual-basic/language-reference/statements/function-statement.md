---
title: Istruzione Function (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52e9210f9e715b6055e6ed199ef1aa4b919c6dd6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="27961-102">Istruzione Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27961-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="27961-103">Dichiara il nome, parametri e il codice che definiscono un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27961-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27961-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="27961-105">Parti</span><span class="sxs-lookup"><span data-stu-id="27961-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="27961-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-106">Optional.</span></span> <span data-ttu-id="27961-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="27961-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="27961-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-108">Optional.</span></span> <span data-ttu-id="27961-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="27961-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="27961-110">Public</span><span class="sxs-lookup"><span data-stu-id="27961-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="27961-111">Protected</span><span class="sxs-lookup"><span data-stu-id="27961-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="27961-112">Friend</span><span class="sxs-lookup"><span data-stu-id="27961-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="27961-113">Private</span><span class="sxs-lookup"><span data-stu-id="27961-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="27961-114">Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="27961-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="27961-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-115">Optional.</span></span> <span data-ttu-id="27961-116">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="27961-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="27961-117">Overload</span><span class="sxs-lookup"><span data-stu-id="27961-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="27961-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="27961-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="27961-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="27961-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="27961-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="27961-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="27961-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="27961-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="27961-122">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-122">Optional.</span></span> <span data-ttu-id="27961-123">Vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="27961-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="27961-124">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-124">Optional.</span></span> <span data-ttu-id="27961-125">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="27961-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="27961-126">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-126">Optional.</span></span> <span data-ttu-id="27961-127">Vedere [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="27961-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="27961-128">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-128">Optional.</span></span> <span data-ttu-id="27961-129">Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="27961-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="27961-130">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27961-130">Required.</span></span> <span data-ttu-id="27961-131">Nome della routine.</span><span class="sxs-lookup"><span data-stu-id="27961-131">Name of the procedure.</span></span> <span data-ttu-id="27961-132">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="27961-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="27961-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-133">Optional.</span></span> <span data-ttu-id="27961-134">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="27961-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="27961-135">Vedere [digitare elenco](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="27961-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="27961-136">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-136">Optional.</span></span> <span data-ttu-id="27961-137">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="27961-138">Vedere [elenco parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="27961-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="27961-139">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="27961-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="27961-140">Tipo di dati del valore restituito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="27961-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-141">Optional.</span></span> <span data-ttu-id="27961-142">Indica che questa procedura consente di implementare una o più `Function` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="27961-143">Vedere [implementa istruzione](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="27961-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="27961-144">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="27961-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="27961-145">Elenco delle routine `Function` implementate.</span><span class="sxs-lookup"><span data-stu-id="27961-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="27961-146">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27961-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="27961-147">Parte</span><span class="sxs-lookup"><span data-stu-id="27961-147">Part</span></span>|<span data-ttu-id="27961-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27961-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="27961-149">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27961-149">Required.</span></span> <span data-ttu-id="27961-150">Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="27961-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="27961-151">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27961-151">Required.</span></span> <span data-ttu-id="27961-152">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="27961-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="27961-153">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-153">Optional.</span></span> <span data-ttu-id="27961-154">Indica che questa procedura è possibile gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="27961-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="27961-155">Vedere [gestisce](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="27961-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="27961-156">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="27961-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="27961-157">Elenco di eventi gestiti dalla routine.</span><span class="sxs-lookup"><span data-stu-id="27961-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="27961-158">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27961-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="27961-159">Parte</span><span class="sxs-lookup"><span data-stu-id="27961-159">Part</span></span>|<span data-ttu-id="27961-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27961-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="27961-161">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27961-161">Required.</span></span> <span data-ttu-id="27961-162">Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="27961-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="27961-163">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27961-163">Required.</span></span> <span data-ttu-id="27961-164">Nome dell'evento che gestisce questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="27961-165">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27961-165">Optional.</span></span> <span data-ttu-id="27961-166">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="27961-167">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27961-168">Note</span><span class="sxs-lookup"><span data-stu-id="27961-168">Remarks</span></span>  
 <span data-ttu-id="27961-169">Tutto il codice eseguibile deve essere all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="27961-170">Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, una struttura o un modulo a cui fa riferimento come classe, struttura o un modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="27961-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="27961-171">Per restituire un valore al codice chiamante, utilizzare un `Function` procedure; in caso contrario, utilizzare un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="27961-172">Definizione di una funzione</span><span class="sxs-lookup"><span data-stu-id="27961-172">Defining a Function</span></span>  
 <span data-ttu-id="27961-173">È possibile definire un `Function` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="27961-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="27961-174">Pertanto, il contesto della dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="27961-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="27961-175">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="27961-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="27961-176">`Function`procedure per impostazione predefinita l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="27961-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="27961-177">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="27961-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="27961-178">Oggetto `Function` routine consente di dichiarare il tipo di dati del valore che restituisce la procedura.</span><span class="sxs-lookup"><span data-stu-id="27961-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="27961-179">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="27961-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="27961-180">Se non si specifica il `returntype` , la procedura restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="27961-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="27961-181">Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve avere anche un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="27961-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="27961-182">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="27961-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="27961-183">Tuttavia, il nome con cui si definisce un'interfaccia di `Function` (in `definedname`) non deve necessariamente corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="27961-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27961-184">È possibile utilizzare espressioni lambda per definire le espressioni di funzione inline.</span><span class="sxs-lookup"><span data-stu-id="27961-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="27961-185">Per ulteriori informazioni, vedere [espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md) e [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="27961-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="27961-186">Restituzione da una funzione</span><span class="sxs-lookup"><span data-stu-id="27961-186">Returning from a Function</span></span>  
 <span data-ttu-id="27961-187">Quando il `Function` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la routine.</span><span class="sxs-lookup"><span data-stu-id="27961-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="27961-188">Per restituire un valore di una funzione, è possibile assegnare il valore per il nome della funzione o includerlo in un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="27961-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="27961-189">Il `Return` istruzione contemporaneamente assegna il valore restituito e chiude la funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="27961-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="27961-190">Nell'esempio seguente viene assegnato il valore restituito per il nome della funzione `myFunction` e quindi utilizza il `Exit Function` istruzione da restituire.</span><span class="sxs-lookup"><span data-stu-id="27961-190">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="27961-191">Il `Exit Function` e `Return` istruzioni uscire immediatamente da un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-191">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="27961-192">Un numero qualsiasi di `Exit Function` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Function` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="27961-192">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="27961-193">Se si utilizza `Exit Function` senza assegnare un valore a `name`, la procedura restituisce il valore predefinito per il tipo di dati specificato in `returntype`.</span><span class="sxs-lookup"><span data-stu-id="27961-193">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="27961-194">Se `returntype` non è specificato, la stored procedure restituisce `Nothing`, ovvero il valore predefinito per `Object`.</span><span class="sxs-lookup"><span data-stu-id="27961-194">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="27961-195">Chiamata di una funzione</span><span class="sxs-lookup"><span data-stu-id="27961-195">Calling a Function</span></span>  
 <span data-ttu-id="27961-196">Si chiama un `Function` procedure utilizzando il nome, seguito dall'elenco di argomenti tra parentesi, in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="27961-196">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="27961-197">È possibile omettere le parentesi solo se non si specificano argomenti.</span><span class="sxs-lookup"><span data-stu-id="27961-197">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="27961-198">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="27961-198">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="27961-199">Si chiama un `Function` routine di funzione, ad esempio nello stesso modo che qualsiasi libreria `Sqrt`, `Cos`, o `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="27961-199">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="27961-200">È inoltre possibile chiamare una funzione mediante il `Call` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="27961-200">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="27961-201">In tal caso, il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="27961-201">In that case, the return value is ignored.</span></span> <span data-ttu-id="27961-202">Utilizzare il `Call` (parola chiave) non è consigliata nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="27961-202">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="27961-203">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="27961-203">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="27961-204">Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interno.</span><span class="sxs-lookup"><span data-stu-id="27961-204">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="27961-205">Per questo motivo, è consigliabile utilizzare un `Function` procedure in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="27961-205">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="27961-206">Funzioni asincrone</span><span class="sxs-lookup"><span data-stu-id="27961-206">Async Functions</span></span>  
 <span data-ttu-id="27961-207">Il *Async* funzionalità consente di richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="27961-207">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="27961-208">Se si contrassegna una funzione con il [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore della funzione.</span><span class="sxs-lookup"><span data-stu-id="27961-208">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="27961-209">Quando il controllo raggiunge un' `Await` espressione il `Async` funzione, il controllo ritorna al chiamante e lo stato di avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="27961-209">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="27961-210">Quando l'attività viene completata, l'esecuzione può riprendere nella funzione.</span><span class="sxs-lookup"><span data-stu-id="27961-210">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27961-211">Un `Async` procedure restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine del `Async` procedure, a seconda del valore si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="27961-211">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="27961-212">Un `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="27961-212">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="27961-213">Un esempio di un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601> di seguito è disponibile.</span><span class="sxs-lookup"><span data-stu-id="27961-213">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="27961-214">Un `Async` funzione non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="27961-214">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="27961-215">A [istruzione Sub](sub-statement.md) può anche essere contrassegnata con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="27961-215">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="27961-216">Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="27961-216">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="27961-217">Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni generate dal `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-217">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="27961-218">Per ulteriori informazioni su `Async` funzioni, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="27961-218">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="27961-219">Funzioni di iteratore</span><span class="sxs-lookup"><span data-stu-id="27961-219">Iterator Functions</span></span>  
 <span data-ttu-id="27961-220">Un *iteratore* funzione esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o matrice.</span><span class="sxs-lookup"><span data-stu-id="27961-220">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="27961-221">Utilizza una funzione iterator il [Yield](yield-statement.md) istruzione per restituire ogni elemento uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="27961-221">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="27961-222">Quando un [Yield](yield-statement.md) istruzione viene raggiunto, la posizione corrente nel codice viene memorizzata.</span><span class="sxs-lookup"><span data-stu-id="27961-222">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="27961-223">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="27961-223">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="27961-224">Chiamare un iteratore dal codice client utilizzando un [For Each... Avanti](for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="27961-224">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="27961-225">Può essere il tipo restituito di una funzione iterator <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="27961-225">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="27961-226">Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="27961-226">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27961-227">Esempio</span><span class="sxs-lookup"><span data-stu-id="27961-227">Example</span></span>  
 <span data-ttu-id="27961-228">L'esempio seguente usa il `Function` istruzione per dichiarare il nome, parametri e il codice che formano il corpo di un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-228">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="27961-229">Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="27961-229">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="27961-230">Esempio</span><span class="sxs-lookup"><span data-stu-id="27961-230">Example</span></span>  
 <span data-ttu-id="27961-231">L'esempio seguente richiama la funzione dichiarata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="27961-231">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="27961-232">Esempio</span><span class="sxs-lookup"><span data-stu-id="27961-232">Example</span></span>  
 <span data-ttu-id="27961-233">Nell'esempio seguente, `DelayAsync` è un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="27961-233">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="27961-234">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="27961-234">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="27961-235">Pertanto la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="27961-235">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="27961-236">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione `DoSomethingAsync` genera un numero intero.</span><span class="sxs-lookup"><span data-stu-id="27961-236">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="27961-237">Come illustrato in questa istruzione: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="27961-237">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="27961-238">Il `startButton_Click` procedure è un esempio di un `Async Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="27961-238">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="27961-239">Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustra l'istruzione seguente: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="27961-239">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="27961-240">Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="27961-240">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="27961-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27961-241">See Also</span></span>  
 [<span data-ttu-id="27961-242">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="27961-242">Sub Statement</span></span>](sub-statement.md)  
 [<span data-ttu-id="27961-243">Routine Function</span><span class="sxs-lookup"><span data-stu-id="27961-243">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="27961-244">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="27961-244">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="27961-245">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="27961-245">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="27961-246">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="27961-246">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="27961-247">Of</span><span class="sxs-lookup"><span data-stu-id="27961-247">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="27961-248">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="27961-248">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="27961-249">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="27961-249">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="27961-250">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="27961-250">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="27961-251">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="27961-251">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="27961-252">Espressione di funzione</span><span class="sxs-lookup"><span data-stu-id="27961-252">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
