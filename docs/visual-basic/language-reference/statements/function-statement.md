---
title: Funzione Statement (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: d875fe6df3ef7ac9390346588b1c2d48497d7116
ms.contentlocale: it-it
ms.lasthandoff: 05/15/2017

---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="4e556-102">Istruzione Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e556-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="4e556-103">Dichiara il nome, parametri e il codice che definiscono un `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e556-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e556-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="4e556-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4e556-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4e556-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-106">Optional.</span></span> <span data-ttu-id="4e556-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4e556-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-108">Optional.</span></span> <span data-ttu-id="4e556-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e556-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4e556-110">Public</span><span class="sxs-lookup"><span data-stu-id="4e556-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="4e556-111">Protected</span><span class="sxs-lookup"><span data-stu-id="4e556-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="4e556-112">Friend</span><span class="sxs-lookup"><span data-stu-id="4e556-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="4e556-113">Private</span><span class="sxs-lookup"><span data-stu-id="4e556-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="4e556-114">Vedere [livelli in Visual Basic di accesso](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="4e556-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-115">Optional.</span></span> <span data-ttu-id="4e556-116">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e556-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4e556-117">Overload</span><span class="sxs-lookup"><span data-stu-id="4e556-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4e556-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="4e556-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4e556-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="4e556-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4e556-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4e556-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4e556-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4e556-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4e556-122">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-122">Optional.</span></span> <span data-ttu-id="4e556-123">Vedere [condivisi](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4e556-124">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-124">Optional.</span></span> <span data-ttu-id="4e556-125">Vedere [ombreggiature](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="4e556-126">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-126">Optional.</span></span> <span data-ttu-id="4e556-127">Vedere [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="4e556-128">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-128">Optional.</span></span> <span data-ttu-id="4e556-129">Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4e556-130">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e556-130">Required.</span></span> <span data-ttu-id="4e556-131">Nome della routine.</span><span class="sxs-lookup"><span data-stu-id="4e556-131">Name of the procedure.</span></span> <span data-ttu-id="4e556-132">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="4e556-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-133">Optional.</span></span> <span data-ttu-id="4e556-134">Elenco di parametri di tipo per una procedura generica.</span><span class="sxs-lookup"><span data-stu-id="4e556-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="4e556-135">Vedere [digitare elenco](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4e556-136">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-136">Optional.</span></span> <span data-ttu-id="4e556-137">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="4e556-138">Vedere [elenco parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="4e556-139">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="4e556-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="4e556-140">Tipo di dati del valore restituito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4e556-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-141">Optional.</span></span> <span data-ttu-id="4e556-142">Indica che questa procedura viene implementato uno o più `Function` procedure, ognuna definita in un'interfaccia implementata dalla classe o struttura che contiene questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="4e556-143">Vedere [implementa istruzione](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4e556-144">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="4e556-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4e556-145">Elenco delle routine `Function` implementate.</span><span class="sxs-lookup"><span data-stu-id="4e556-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="4e556-146">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e556-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4e556-147">Parte</span><span class="sxs-lookup"><span data-stu-id="4e556-147">Part</span></span>|<span data-ttu-id="4e556-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e556-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4e556-149">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e556-149">Required.</span></span> <span data-ttu-id="4e556-150">Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="4e556-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4e556-151">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e556-151">Required.</span></span> <span data-ttu-id="4e556-152">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="4e556-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="4e556-153">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-153">Optional.</span></span> <span data-ttu-id="4e556-154">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="4e556-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="4e556-155">Vedere [gestisce](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="4e556-156">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="4e556-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="4e556-157">Elenco di eventi gestiti dalla routine.</span><span class="sxs-lookup"><span data-stu-id="4e556-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="4e556-158">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e556-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="4e556-159">Parte</span><span class="sxs-lookup"><span data-stu-id="4e556-159">Part</span></span>|<span data-ttu-id="4e556-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e556-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="4e556-161">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e556-161">Required.</span></span> <span data-ttu-id="4e556-162">Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="4e556-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="4e556-163">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4e556-163">Required.</span></span> <span data-ttu-id="4e556-164">Nome dell'evento gestito dalla routine.</span><span class="sxs-lookup"><span data-stu-id="4e556-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="4e556-165">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e556-165">Optional.</span></span> <span data-ttu-id="4e556-166">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="4e556-167">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e556-168">Note</span><span class="sxs-lookup"><span data-stu-id="4e556-168">Remarks</span></span>  
 <span data-ttu-id="4e556-169">Tutto il codice eseguibile deve essere all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="4e556-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="4e556-170">Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, una struttura o un modulo che viene definito la classe, struttura o un modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4e556-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="4e556-171">Per restituire un valore al codice chiamante, utilizzare un `Function` procedura; in caso contrario, utilizzare un `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="4e556-172">Definizione di una funzione</span><span class="sxs-lookup"><span data-stu-id="4e556-172">Defining a Function</span></span>  
 <span data-ttu-id="4e556-173">È possibile definire un `Function` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="4e556-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="4e556-174">Pertanto, il contesto della dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="4e556-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="4e556-175">Per ulteriori informazioni, vedere [contesti delle dichiarazioni e livelli di accesso predefinito](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4e556-176">`Function`Per impostazione predefinita le procedure per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="4e556-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="4e556-177">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="4e556-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="4e556-178">Oggetto `Function` routine consente di dichiarare il tipo di dati del valore che restituisce la procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="4e556-179">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4e556-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="4e556-180">Se non si specifica il `returntype` , la procedura restituisce `Object`.</span><span class="sxs-lookup"><span data-stu-id="4e556-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="4e556-181">Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve inoltre disporre un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4e556-182">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4e556-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="4e556-183">Tuttavia, il nome con cui si definisce un'interfaccia di `Function` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="4e556-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e556-184">È possibile utilizzare espressioni lambda per definire espressioni di funzione inline.</span><span class="sxs-lookup"><span data-stu-id="4e556-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="4e556-185">Per ulteriori informazioni, vedere [espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md) e [le espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="4e556-186">Restituzione da una funzione</span><span class="sxs-lookup"><span data-stu-id="4e556-186">Returning from a Function</span></span>  
 <span data-ttu-id="4e556-187">Quando il `Function` procedure restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la routine.</span><span class="sxs-lookup"><span data-stu-id="4e556-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="4e556-188">Per restituire un valore di una funzione, è possibile assegnare il valore per il nome della funzione o includerlo in un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="4e556-189">Il `Return` istruzione contemporaneamente assegna il valore restituito ed esce dalla funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4e556-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 <span data-ttu-id="4e556-190">[!code-vb[VbVbalrStatements&#24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e556-190">[!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="4e556-191">Nell'esempio seguente assegna il valore restituito per il nome della funzione `myFunction` e quindi utilizza il `Exit Function` istruzione per la restituzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-191">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 <span data-ttu-id="4e556-192">[!code-vb[VbVbalrStatements&#23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e556-192">[!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="4e556-193">Il `Exit Function` e `Return` istruzioni uscire immediatamente da un `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="4e556-194">Un numero qualsiasi di `Exit Function` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Function` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4e556-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="4e556-195">Se si utilizza `Exit Function` senza assegnare un valore a `name`, la procedura restituisce il valore predefinito per il tipo di dati specificato in `returntype`.</span><span class="sxs-lookup"><span data-stu-id="4e556-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="4e556-196">Se `returntype` non è specificato, la stored procedure restituisce `Nothing`, ovvero il valore predefinito per `Object`.</span><span class="sxs-lookup"><span data-stu-id="4e556-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="4e556-197">Chiamata di una funzione</span><span class="sxs-lookup"><span data-stu-id="4e556-197">Calling a Function</span></span>  
 <span data-ttu-id="4e556-198">Si chiama un `Function` procedure utilizzando il nome, seguito dall'elenco di argomenti racchiuso tra parentesi, in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4e556-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="4e556-199">È possibile omettere le parentesi solo se non si specificano argomenti.</span><span class="sxs-lookup"><span data-stu-id="4e556-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="4e556-200">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="4e556-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="4e556-201">Si chiama un `Function` procedura simile a quello di chiamare qualsiasi libreria funzione, ad esempio `Sqrt`, `Cos`, o `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="4e556-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="4e556-202">È inoltre possibile chiamare una funzione utilizzando il `Call` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="4e556-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="4e556-203">In tal caso, il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="4e556-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="4e556-204">Utilizzare il `Call` (parola chiave) non è consigliata nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="4e556-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="4e556-205">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="4e556-206">Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interna.</span><span class="sxs-lookup"><span data-stu-id="4e556-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="4e556-207">Per questo motivo, è consigliabile utilizzare un `Function` procedure in un'espressione aritmetica se la funzione modifica il valore delle variabili nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="4e556-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="4e556-208">Funzioni asincrone</span><span class="sxs-lookup"><span data-stu-id="4e556-208">Async Functions</span></span>  
 <span data-ttu-id="4e556-209">Il *Async* funzionalità consente di richiamare le funzioni asincrone senza utilizzare callback esplicito o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4e556-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="4e556-210">Se si contrassegna una funzione con la [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore della funzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="4e556-211">Quando il controllo raggiunge un `Await` espressione il `Async` funzione, il controllo ritorna al chiamante e lo stato di avanzamento nella funzione viene sospesa fino al completamento dell'attività di attesa.</span><span class="sxs-lookup"><span data-stu-id="4e556-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="4e556-212">Una volta completata l'attività, è possibile riprendere esecuzione nella funzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e556-213">Un `Async` procedura restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine della `Async` procedura, qualunque si verifichi prima.</span><span class="sxs-lookup"><span data-stu-id="4e556-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="4e556-214">Un `Async` funzione può avere un tipo restituito <xref:System.Threading.Tasks.Task%601>o <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="4e556-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="4e556-215">Un esempio di un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601>viene fornito di seguito.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="4e556-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="4e556-216">Un `Async` funzione non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="4e556-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="4e556-217">Oggetto [Sub (istruzione)](sub-statement.md) può anche essere contrassegnato con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="4e556-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="4e556-218">Viene utilizzato principalmente per i gestori eventi, in cui non può essere restituito un valore.</span><span class="sxs-lookup"><span data-stu-id="4e556-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="4e556-219">Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni generate dalla `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-219">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="4e556-220">Per ulteriori informazioni su `Async` funzioni, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [Async restituire tipi](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="4e556-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="4e556-221">Funzioni di iteratore</span><span class="sxs-lookup"><span data-stu-id="4e556-221">Iterator Functions</span></span>  
 <span data-ttu-id="4e556-222">Un *iteratore* funzione esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice.</span><span class="sxs-lookup"><span data-stu-id="4e556-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="4e556-223">Utilizza una funzione iteratore di [Yield](yield-statement.md) istruzione per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="4e556-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="4e556-224">Quando un [Yield](yield-statement.md) viene raggiunta l'istruzione, viene memorizzata la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="4e556-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="4e556-225">L'esecuzione viene riavviata da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="4e556-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="4e556-226">Un iteratore viene chiamato dal codice client utilizzando un [For Each... Avanti](for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="4e556-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="4e556-227">Il tipo restituito di una funzione iteratore può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="4e556-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="4e556-228">Per altre informazioni, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="4e556-228">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e556-229">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e556-229">Example</span></span>  
 <span data-ttu-id="4e556-230">Nell'esempio seguente viene utilizzata la `Function` istruzione per dichiarare il nome, parametri e il codice che formano il corpo di un `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="4e556-231">Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4e556-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 <span data-ttu-id="4e556-232">[!code-vb[VbVbalrStatements&#25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e556-232">[!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e556-233">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e556-233">Example</span></span>  
 <span data-ttu-id="4e556-234">Nell'esempio seguente richiama la funzione dichiarata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4e556-234">The following example invokes the function declared in the preceding example.</span></span>  
  
 <span data-ttu-id="4e556-235">[!code-vb[&#26; VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e556-235">[!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e556-236">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e556-236">Example</span></span>  
 <span data-ttu-id="4e556-237">Nell'esempio seguente, `DelayAsync` è un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="4e556-237">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4e556-238">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="4e556-238">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="4e556-239">Pertanto la dichiarazione della funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="4e556-239">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="4e556-240">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione di `Await` espressione `DoSomethingAsync` produce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="4e556-240">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="4e556-241">Questa funzionalità viene illustrata questa istruzione: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="4e556-241">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="4e556-242">Il `startButton_Click` procedura è un esempio di un `Async Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="4e556-242">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="4e556-243">Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere atteso, come illustrato di seguito l'istruzione seguente: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="4e556-243">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="4e556-244">Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="4e556-244">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="4e556-245">[!code-vb[csAsyncMethod n.&1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e556-245">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e556-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e556-246">See Also</span></span>  
 <span data-ttu-id="4e556-247">[Sub (istruzione)](sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-247">[Sub Statement](sub-statement.md) </span></span>  
<span data-ttu-id="4e556-248"> [Routine di funzione](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-248"> [Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="4e556-249"> [Elenco di parametri](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-249"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="4e556-250"> [Dim (istruzione)](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-250"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="4e556-251"> [Istruzione Call](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-251"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="4e556-252"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-252"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="4e556-253"> [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-253"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="4e556-254"> [Procedura: utilizzare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-254"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="4e556-255"> [Le procedure di risoluzione](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-255"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="4e556-256"> [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="4e556-256"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="4e556-257"> [Espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md)</span><span class="sxs-lookup"><span data-stu-id="4e556-257"> [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)</span></span>

