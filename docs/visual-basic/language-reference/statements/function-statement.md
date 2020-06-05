---
title: Istruzione Function
ms.date: 05/12/2018
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
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404628"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="f268a-102">Istruzione Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f268a-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="f268a-103">Dichiara il nome, i parametri e il codice che definiscono una `Function` routine.</span><span class="sxs-lookup"><span data-stu-id="f268a-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="f268a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f268a-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="f268a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f268a-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="f268a-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-106">Optional.</span></span> <span data-ttu-id="f268a-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="f268a-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-108">Optional.</span></span> <span data-ttu-id="f268a-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="f268a-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="f268a-110">Pubblica</span><span class="sxs-lookup"><span data-stu-id="f268a-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="f268a-111">Protetto</span><span class="sxs-lookup"><span data-stu-id="f268a-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="f268a-112">Amico</span><span class="sxs-lookup"><span data-stu-id="f268a-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="f268a-113">Privata</span><span class="sxs-lookup"><span data-stu-id="f268a-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="f268a-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f268a-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="f268a-115">Privato protetto</span><span class="sxs-lookup"><span data-stu-id="f268a-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="f268a-116">Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="f268a-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-117">Optional.</span></span> <span data-ttu-id="f268a-118">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="f268a-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="f268a-119">Overload</span><span class="sxs-lookup"><span data-stu-id="f268a-119">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="f268a-120">Override</span><span class="sxs-lookup"><span data-stu-id="f268a-120">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="f268a-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="f268a-121">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="f268a-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f268a-122">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="f268a-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f268a-123">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="f268a-124">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-124">Optional.</span></span> <span data-ttu-id="f268a-125">Vedere [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-125">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="f268a-126">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-126">Optional.</span></span> <span data-ttu-id="f268a-127">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-127">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="f268a-128">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-128">Optional.</span></span> <span data-ttu-id="f268a-129">Vedere [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-129">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="f268a-130">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-130">Optional.</span></span> <span data-ttu-id="f268a-131">Vedere [iteratore](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-131">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="f268a-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f268a-132">Required.</span></span> <span data-ttu-id="f268a-133">Nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-133">Name of the procedure.</span></span> <span data-ttu-id="f268a-134">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="f268a-135">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-135">Optional.</span></span> <span data-ttu-id="f268a-136">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="f268a-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="f268a-137">Vedere [elenco dei tipi](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="f268a-138">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-138">Optional.</span></span> <span data-ttu-id="f268a-139">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="f268a-140">Vedere [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="f268a-141">Obbligatorio se `Option Strict` è `On` .</span><span class="sxs-lookup"><span data-stu-id="f268a-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f268a-142">Tipo di dati del valore restituito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="f268a-143">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-143">Optional.</span></span> <span data-ttu-id="f268a-144">Indica che questa procedura implementa una o più `Function` procedure, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="f268a-145">Vedere [istruzione Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="f268a-146">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="f268a-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="f268a-147">Elenco delle routine `Function` implementate.</span><span class="sxs-lookup"><span data-stu-id="f268a-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="f268a-148">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f268a-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="f268a-149">Parte</span><span class="sxs-lookup"><span data-stu-id="f268a-149">Part</span></span>|<span data-ttu-id="f268a-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f268a-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="f268a-151">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f268a-151">Required.</span></span> <span data-ttu-id="f268a-152">Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="f268a-153">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f268a-153">Required.</span></span> <span data-ttu-id="f268a-154">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="f268a-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="f268a-155">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-155">Optional.</span></span> <span data-ttu-id="f268a-156">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="f268a-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="f268a-157">Vedere [handle](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="f268a-158">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="f268a-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="f268a-159">Elenco di eventi gestiti da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="f268a-160">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f268a-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="f268a-161">Parte</span><span class="sxs-lookup"><span data-stu-id="f268a-161">Part</span></span>|<span data-ttu-id="f268a-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f268a-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="f268a-163">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f268a-163">Required.</span></span> <span data-ttu-id="f268a-164">Variabile oggetto dichiarata con il tipo di dati della classe o della struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="f268a-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="f268a-165">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f268a-165">Required.</span></span> <span data-ttu-id="f268a-166">Nome dell'evento gestito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="f268a-167">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f268a-167">Optional.</span></span> <span data-ttu-id="f268a-168">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="f268a-169">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="f268a-170">Commenti</span><span class="sxs-lookup"><span data-stu-id="f268a-170">Remarks</span></span>

<span data-ttu-id="f268a-171">Tutto il codice eseguibile deve trovarsi all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="f268a-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="f268a-172">Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, di una struttura o di un modulo a cui viene fatto riferimento come classe, struttura o modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f268a-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="f268a-173">Per restituire un valore al codice chiamante, utilizzare una `Function` stored procedure; in caso contrario, utilizzare una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="f268a-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="f268a-174">Definizione di una funzione</span><span class="sxs-lookup"><span data-stu-id="f268a-174">Defining a Function</span></span>

<span data-ttu-id="f268a-175">È possibile definire una `Function` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="f268a-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="f268a-176">Pertanto, il contesto di dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco.</span><span class="sxs-lookup"><span data-stu-id="f268a-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="f268a-177">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="f268a-178">`Function`per impostazione predefinita, le procedure sono con accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="f268a-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="f268a-179">È possibile modificare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="f268a-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="f268a-180">Una `Function` procedura può dichiarare il tipo di dati del valore restituito dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f268a-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="f268a-181">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f268a-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="f268a-182">Se non si specifica il `returntype` parametro, la procedura restituisce `Object` .</span><span class="sxs-lookup"><span data-stu-id="f268a-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="f268a-183">Se questa routine usa la `Implements` parola chiave, la classe o la struttura contenitore deve avere anche un' `Implements` istruzione che segue immediatamente la relativa `Class` `Structure` istruzione o.</span><span class="sxs-lookup"><span data-stu-id="f268a-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="f268a-184">L' `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="f268a-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="f268a-185">Tuttavia, il nome con cui un'interfaccia definisce `Function` (in `definedname` ) non deve corrispondere al nome di questa procedura (in `name` ).</span><span class="sxs-lookup"><span data-stu-id="f268a-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="f268a-186">È possibile utilizzare le espressioni lambda per definire espressioni di funzione inline.</span><span class="sxs-lookup"><span data-stu-id="f268a-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="f268a-187">Per altre informazioni, vedere [espressione di funzione](../operators/function-expression.md) ed [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-187">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="f268a-188">Restituzione da una funzione</span><span class="sxs-lookup"><span data-stu-id="f268a-188">Returning from a Function</span></span>

<span data-ttu-id="f268a-189">Quando la `Function` procedura viene restituita al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="f268a-190">Per restituire un valore da una funzione, è possibile assegnare il valore al nome della funzione o includerlo in un' `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f268a-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="f268a-191">L' `Return` istruzione assegna simultaneamente il valore restituito e chiude la funzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f268a-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="f268a-192">Nell'esempio seguente viene assegnato il valore restituito al nome della funzione `myFunction` e quindi viene utilizzata l' `Exit Function` istruzione per restituire.</span><span class="sxs-lookup"><span data-stu-id="f268a-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="f268a-193">Le `Exit Function` `Return` istruzioni e generano un'uscita immediata da una `Function` routine.</span><span class="sxs-lookup"><span data-stu-id="f268a-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="f268a-194">Qualsiasi numero di `Exit Function` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Function` `Return` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="f268a-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="f268a-195">Se si utilizza `Exit Function` senza assegnare un valore a `name` , la stored procedure restituisce il valore predefinito per il tipo di dati specificato in `returntype` .</span><span class="sxs-lookup"><span data-stu-id="f268a-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="f268a-196">Se `returntype` non è specificato, la procedura restituisce `Nothing` , che rappresenta il valore predefinito per `Object` .</span><span class="sxs-lookup"><span data-stu-id="f268a-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="f268a-197">Chiamata di una funzione</span><span class="sxs-lookup"><span data-stu-id="f268a-197">Calling a Function</span></span>

<span data-ttu-id="f268a-198">È possibile chiamare una `Function` stored procedure utilizzando il nome della procedura, seguito dall'elenco di argomenti tra parentesi, in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f268a-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="f268a-199">È possibile omettere le parentesi solo se non si forniscono argomenti.</span><span class="sxs-lookup"><span data-stu-id="f268a-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="f268a-200">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="f268a-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="f268a-201">È possibile chiamare una `Function` stored procedure nello stesso modo in cui si chiama qualsiasi funzione di libreria, ad esempio `Sqrt` , `Cos` o `ChrW` .</span><span class="sxs-lookup"><span data-stu-id="f268a-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="f268a-202">È anche possibile chiamare una funzione usando la `Call` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="f268a-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="f268a-203">In tal caso, il valore restituito viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="f268a-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="f268a-204">`Call`Nella maggior parte dei casi non è consigliabile usare la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="f268a-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="f268a-205">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="f268a-206">Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna.</span><span class="sxs-lookup"><span data-stu-id="f268a-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="f268a-207">Per questo motivo, non è consigliabile utilizzare una `Function` stored procedure in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="f268a-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="f268a-208">Funzioni asincrone</span><span class="sxs-lookup"><span data-stu-id="f268a-208">Async Functions</span></span>

<span data-ttu-id="f268a-209">La *funzionalità asincrona consente* di richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="f268a-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="f268a-210">Se si contrassegna una funzione con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nella funzione.</span><span class="sxs-lookup"><span data-stu-id="f268a-210">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="f268a-211">Quando il controllo raggiunge un' `Await` espressione nella `Async` funzione, il controllo torna al chiamante e l'avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="f268a-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="f268a-212">Al termine dell'attività, l'esecuzione può riprendere nella funzione.</span><span class="sxs-lookup"><span data-stu-id="f268a-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="f268a-213">Una `Async` routine restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine della `Async` procedura, a seconda di quale si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="f268a-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="f268a-214">Una `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="f268a-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="f268a-215">Di seguito è riportato un esempio di una `Async` funzione con un tipo restituito <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="f268a-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="f268a-216">Una `Async` funzione non può dichiarare parametri [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="f268a-216">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="f268a-217">Un' [istruzione Sub](sub-statement.md) può anche essere contrassegnata con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="f268a-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="f268a-218">Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="f268a-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="f268a-219">Una `Async` `Sub` routine non può essere attesa e il chiamante di una `Async` `Sub` routine non può intercettare le eccezioni generate dalla `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="f268a-220">Per altre informazioni sulle `Async` funzioni, vedere [programmazione asincrona con Async e await](../../programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="f268a-221">Funzioni iteratore</span><span class="sxs-lookup"><span data-stu-id="f268a-221">Iterator Functions</span></span>

<span data-ttu-id="f268a-222">Una funzione *iteratore* esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice.</span><span class="sxs-lookup"><span data-stu-id="f268a-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="f268a-223">Una funzione iteratore usa l'istruzione [yield](yield-statement.md) per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="f268a-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="f268a-224">Quando viene raggiunta un'istruzione [yield](yield-statement.md) , viene memorizzata la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="f268a-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="f268a-225">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="f268a-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="f268a-226">È possibile chiamare un iteratore dal codice client usando un [per ogni... Istruzione successiva](for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="f268a-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="f268a-227">Il tipo restituito di una funzione iteratore può essere <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="f268a-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="f268a-228">Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="f268a-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="f268a-229">Esempio</span><span class="sxs-lookup"><span data-stu-id="f268a-229">Example</span></span>

<span data-ttu-id="f268a-230">Nell'esempio seguente viene utilizzata l' `Function` istruzione per dichiarare il nome, i parametri e il codice che formano il corpo di una `Function` routine.</span><span class="sxs-lookup"><span data-stu-id="f268a-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="f268a-231">Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="f268a-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="f268a-232">Esempio</span><span class="sxs-lookup"><span data-stu-id="f268a-232">Example</span></span>

<span data-ttu-id="f268a-233">Nell'esempio seguente viene richiamata la funzione dichiarata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f268a-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="f268a-234">Esempio</span><span class="sxs-lookup"><span data-stu-id="f268a-234">Example</span></span>

<span data-ttu-id="f268a-235">Nell'esempio seguente `DelayAsync` è un oggetto `Async` `Function` che ha un tipo restituito <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="f268a-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f268a-236">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="f268a-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="f268a-237">La dichiarazione di funzione di `DelayAsync` deve quindi avere un tipo restituito `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="f268a-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="f268a-238">Poiché il tipo restituito è `Task(Of Integer)` , la valutazione dell' `Await` espressione in `DoSomethingAsync` genera un numero intero.</span><span class="sxs-lookup"><span data-stu-id="f268a-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="f268a-239">Questa operazione viene illustrata in questa istruzione: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="f268a-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="f268a-240">La `startButton_Click` procedura è un esempio di `Async Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="f268a-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="f268a-241">Poiché `DoSomethingAsync` è una `Async` funzione, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="f268a-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="f268a-242">La `startButton_Click` `Sub` procedura deve essere definita con il `Async` modificatore perché contiene un' `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="f268a-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f268a-243">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f268a-243">See also</span></span>

- [<span data-ttu-id="f268a-244">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f268a-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="f268a-245">Routine Function</span><span class="sxs-lookup"><span data-stu-id="f268a-245">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="f268a-246">Elenco parametri</span><span class="sxs-lookup"><span data-stu-id="f268a-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="f268a-247">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="f268a-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="f268a-248">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="f268a-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="f268a-249">Di</span><span class="sxs-lookup"><span data-stu-id="f268a-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="f268a-250">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="f268a-250">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="f268a-251">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="f268a-251">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="f268a-252">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="f268a-252">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="f268a-253">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="f268a-253">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="f268a-254">Espressione di funzione</span><span class="sxs-lookup"><span data-stu-id="f268a-254">Function Expression</span></span>](../operators/function-expression.md)
