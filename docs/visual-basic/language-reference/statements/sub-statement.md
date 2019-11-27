---
title: Istruzione Sub
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346446"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="1432a-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1432a-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="1432a-103">Dichiara il nome, i parametri e il codice che definiscono una procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1432a-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="1432a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1432a-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="1432a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1432a-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="1432a-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-106">Optional.</span></span> <span data-ttu-id="1432a-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="1432a-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-108">Optional.</span></span> <span data-ttu-id="1432a-109">Indica la definizione di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="1432a-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="1432a-110">Vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="1432a-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-111">Optional.</span></span> <span data-ttu-id="1432a-112">Può essere uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1432a-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="1432a-113">Public</span><span class="sxs-lookup"><span data-stu-id="1432a-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="1432a-114">Protected</span><span class="sxs-lookup"><span data-stu-id="1432a-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="1432a-115">Friend</span><span class="sxs-lookup"><span data-stu-id="1432a-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="1432a-116">Private</span><span class="sxs-lookup"><span data-stu-id="1432a-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="1432a-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="1432a-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="1432a-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="1432a-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="1432a-119">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="1432a-120">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-120">Optional.</span></span> <span data-ttu-id="1432a-121">Può essere uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1432a-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="1432a-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="1432a-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="1432a-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="1432a-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="1432a-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="1432a-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="1432a-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1432a-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="1432a-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1432a-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="1432a-127">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-127">Optional.</span></span> <span data-ttu-id="1432a-128">Vedere [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="1432a-129">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-129">Optional.</span></span> <span data-ttu-id="1432a-130">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="1432a-131">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-131">Optional.</span></span> <span data-ttu-id="1432a-132">Vedere [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="1432a-133">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1432a-133">Required.</span></span> <span data-ttu-id="1432a-134">Nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-134">Name of the procedure.</span></span> <span data-ttu-id="1432a-135">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="1432a-136">Per creare una routine del costruttore per una classe, impostare il nome di una routine `Sub` sulla parola chiave `New`.</span><span class="sxs-lookup"><span data-stu-id="1432a-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="1432a-137">Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="1432a-138">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-138">Optional.</span></span> <span data-ttu-id="1432a-139">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="1432a-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="1432a-140">Vedere [elenco dei tipi](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="1432a-141">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-141">Optional.</span></span> <span data-ttu-id="1432a-142">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="1432a-143">Vedere [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="1432a-144">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-144">Optional.</span></span> <span data-ttu-id="1432a-145">Indica che questa procedura implementa una o più `Sub` procedure, ognuna definita in un'interfaccia implementata dalla classe o dalla struttura che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1432a-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="1432a-146">Vedere [istruzione Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="1432a-147">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="1432a-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="1432a-148">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="1432a-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="1432a-149">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1432a-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="1432a-150">Parte</span><span class="sxs-lookup"><span data-stu-id="1432a-150">Part</span></span>|<span data-ttu-id="1432a-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1432a-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="1432a-152">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1432a-152">Required.</span></span> <span data-ttu-id="1432a-153">Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="1432a-154">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1432a-154">Required.</span></span> <span data-ttu-id="1432a-155">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="1432a-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="1432a-156">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-156">Optional.</span></span> <span data-ttu-id="1432a-157">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="1432a-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="1432a-158">Vedere [handle](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="1432a-159">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="1432a-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="1432a-160">Elenco di eventi gestiti da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="1432a-161">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1432a-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="1432a-162">Parte</span><span class="sxs-lookup"><span data-stu-id="1432a-162">Part</span></span>|<span data-ttu-id="1432a-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1432a-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="1432a-164">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1432a-164">Required.</span></span> <span data-ttu-id="1432a-165">Variabile oggetto dichiarata con il tipo di dati della classe o della struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="1432a-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="1432a-166">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1432a-166">Required.</span></span> <span data-ttu-id="1432a-167">Nome dell'evento gestito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="1432a-168">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1432a-168">Optional.</span></span> <span data-ttu-id="1432a-169">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="1432a-170">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="1432a-171">Note</span><span class="sxs-lookup"><span data-stu-id="1432a-171">Remarks</span></span>

<span data-ttu-id="1432a-172">Tutto il codice eseguibile deve trovarsi all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="1432a-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="1432a-173">Usare una procedura `Sub` quando non si vuole restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="1432a-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="1432a-174">Utilizzare una procedura `Function` quando si desidera restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="1432a-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="1432a-175">Definizione di una routine Sub</span><span class="sxs-lookup"><span data-stu-id="1432a-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="1432a-176">È possibile definire una procedura di `Sub` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="1432a-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="1432a-177">Il contesto di dichiarazione per una routine Sub deve pertanto essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco.</span><span class="sxs-lookup"><span data-stu-id="1432a-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="1432a-178">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="1432a-179">per impostazione predefinita, `Sub` procedure per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="1432a-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="1432a-180">È possibile modificare i livelli di accesso usando i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="1432a-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="1432a-181">Se nella routine viene utilizzata la parola chiave `Implements`, la classe o la struttura che lo contiene deve disporre di un'istruzione `Implements` che segue immediatamente il `Class` o l'istruzione `Structure`.</span><span class="sxs-lookup"><span data-stu-id="1432a-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="1432a-182">L'istruzione `Implements` deve includere ogni interfaccia specificata nel `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="1432a-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="1432a-183">Tuttavia, il nome con cui un'interfaccia definisce il `Sub` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="1432a-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="1432a-184">Restituzione da una routine Sub</span><span class="sxs-lookup"><span data-stu-id="1432a-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="1432a-185">Quando una `Sub` procedura restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="1432a-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="1432a-186">Nell'esempio seguente viene illustrato un ritorno da una routine `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1432a-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="1432a-187">Le istruzioni `Exit Sub` e `Return` generano un'uscita immediata da una procedura di `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1432a-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="1432a-188">Un numero qualsiasi di istruzioni `Exit Sub` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Sub` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1432a-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="1432a-189">Chiamata a una procedura secondaria</span><span class="sxs-lookup"><span data-stu-id="1432a-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="1432a-190">È possibile chiamare una procedura `Sub` usando il nome della stored procedure in un'istruzione e quindi seguendo tale nome con l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="1432a-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="1432a-191">È possibile omettere le parentesi solo se non si forniscono argomenti.</span><span class="sxs-lookup"><span data-stu-id="1432a-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="1432a-192">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="1432a-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="1432a-193">Una routine `Sub` e una procedura `Function` possono avere parametri ed eseguire una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1432a-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="1432a-194">Tuttavia, una routine di `Function` restituisce un valore e non una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="1432a-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="1432a-195">Pertanto, non è possibile utilizzare una stored procedure `Sub` in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="1432a-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="1432a-196">È possibile utilizzare la parola chiave `Call` quando si chiama una routine `Sub`, ma tale parola chiave non è consigliata per la maggior parte degli utilizzi.</span><span class="sxs-lookup"><span data-stu-id="1432a-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="1432a-197">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="1432a-198">Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna.</span><span class="sxs-lookup"><span data-stu-id="1432a-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="1432a-199">Per questo motivo, se nell'elenco di argomenti sono incluse espressioni che chiamano altre routine, non è necessario presupporre che tali espressioni verranno richiamate in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="1432a-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="1432a-200">Procedure secondarie asincrone</span><span class="sxs-lookup"><span data-stu-id="1432a-200">Async Sub Procedures</span></span>

<span data-ttu-id="1432a-201">Utilizzando la funzionalità asincrona, è possibile richiamare funzioni asincrone senza utilizzare callback espliciti o suddividere manualmente il codice tra più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="1432a-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="1432a-202">Se si contrassegna una routine con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../../../visual-basic/language-reference/operators/await-operator.md) nella procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="1432a-203">Quando il controllo raggiunge un'espressione `Await` nella procedura `Async`, il controllo torna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="1432a-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="1432a-204">Al termine dell'attività, l'esecuzione può riprendere nella procedura.</span><span class="sxs-lookup"><span data-stu-id="1432a-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1432a-205">Una procedura `Async` restituisce al chiamante quando viene rilevato il primo oggetto atteso che non è ancora completo o viene raggiunta la fine della `Async` routine, a seconda di quale si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="1432a-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="1432a-206">È anche possibile contrassegnare un' [istruzione di funzione](function-statement.md) con il modificatore `Async`.</span><span class="sxs-lookup"><span data-stu-id="1432a-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="1432a-207">Una funzione `Async` può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="1432a-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="1432a-208">Un esempio più avanti in questo argomento illustra una funzione `Async` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="1432a-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="1432a-209">`Async` `Sub` procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="1432a-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="1432a-210">Non è possibile attendere un `Async` `Sub` routine e il chiamante di una procedura di `Sub` `Async` non può rilevare eccezioni generate dalla procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1432a-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="1432a-211">Una `Async` routine non può dichiarare alcun parametro [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="1432a-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="1432a-212">Per altre informazioni sulle procedure di `Async`, vedere [programmazione asincrona con Async e await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="1432a-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="1432a-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="1432a-213">Example</span></span>

<span data-ttu-id="1432a-214">Nell'esempio seguente viene utilizzata l'istruzione `Sub` per definire il nome, i parametri e il codice che formano il corpo di una routine di `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1432a-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="1432a-215">Esempio</span><span class="sxs-lookup"><span data-stu-id="1432a-215">Example</span></span>

<span data-ttu-id="1432a-216">Nell'esempio seguente `DelayAsync` è un `Async` `Function` il cui tipo restituito è <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="1432a-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="1432a-217">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="1432a-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="1432a-218">Pertanto, la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="1432a-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="1432a-219">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione dell'espressione `Await` in `DoSomethingAsync` produce un Integer, come illustrato nella seguente istruzione: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="1432a-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="1432a-220">La procedura `startButton_Click` è un esempio di `Async Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="1432a-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="1432a-221">Poiché `DoSomethingAsync` è una funzione `Async`, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nella seguente istruzione: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="1432a-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="1432a-222">Il `startButton_Click` `Sub` routine deve essere definito con il modificatore di `Async` perché contiene un'espressione `Await`.</span><span class="sxs-lookup"><span data-stu-id="1432a-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1432a-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1432a-223">See also</span></span>

- [<span data-ttu-id="1432a-224">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="1432a-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="1432a-225">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1432a-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="1432a-226">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="1432a-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="1432a-227">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="1432a-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="1432a-228">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="1432a-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="1432a-229">Of</span><span class="sxs-lookup"><span data-stu-id="1432a-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="1432a-230">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="1432a-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="1432a-231">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="1432a-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="1432a-232">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="1432a-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="1432a-233">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="1432a-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
