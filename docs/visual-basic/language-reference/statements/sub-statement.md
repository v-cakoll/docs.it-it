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
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404174"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="8c160-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c160-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="8c160-103">Dichiara il nome, i parametri e il codice che definiscono una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="8c160-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c160-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c160-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="8c160-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8c160-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="8c160-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-106">Optional.</span></span> <span data-ttu-id="8c160-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="8c160-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-108">Optional.</span></span> <span data-ttu-id="8c160-109">Indica la definizione di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="8c160-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="8c160-110">Vedere [metodi parziali](../../programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-110">See [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="8c160-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-111">Optional.</span></span> <span data-ttu-id="8c160-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c160-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="8c160-113">Pubblica</span><span class="sxs-lookup"><span data-stu-id="8c160-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="8c160-114">Protetto</span><span class="sxs-lookup"><span data-stu-id="8c160-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="8c160-115">Amico</span><span class="sxs-lookup"><span data-stu-id="8c160-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="8c160-116">Privata</span><span class="sxs-lookup"><span data-stu-id="8c160-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="8c160-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8c160-117">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="8c160-118">Privato protetto</span><span class="sxs-lookup"><span data-stu-id="8c160-118">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="8c160-119">Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-119">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="8c160-120">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-120">Optional.</span></span> <span data-ttu-id="8c160-121">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c160-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="8c160-122">Overload</span><span class="sxs-lookup"><span data-stu-id="8c160-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="8c160-123">Override</span><span class="sxs-lookup"><span data-stu-id="8c160-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="8c160-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="8c160-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="8c160-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="8c160-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="8c160-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="8c160-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="8c160-127">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-127">Optional.</span></span> <span data-ttu-id="8c160-128">Vedere [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="8c160-129">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-129">Optional.</span></span> <span data-ttu-id="8c160-130">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="8c160-131">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-131">Optional.</span></span> <span data-ttu-id="8c160-132">Vedere [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="8c160-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c160-133">Required.</span></span> <span data-ttu-id="8c160-134">Nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-134">Name of the procedure.</span></span> <span data-ttu-id="8c160-135">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-135">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="8c160-136">Per creare una routine del costruttore per una classe, impostare il nome di una `Sub` stored procedure sulla `New` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="8c160-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="8c160-137">Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="8c160-138">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-138">Optional.</span></span> <span data-ttu-id="8c160-139">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="8c160-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="8c160-140">Vedere [elenco dei tipi](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="8c160-141">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-141">Optional.</span></span> <span data-ttu-id="8c160-142">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="8c160-143">Vedere [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="8c160-144">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-144">Optional.</span></span> <span data-ttu-id="8c160-145">Indica che questa procedura implementa una o più `Sub` procedure, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="8c160-146">Vedere [istruzione Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="8c160-147">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="8c160-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="8c160-148">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="8c160-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="8c160-149">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c160-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="8c160-150">Parte</span><span class="sxs-lookup"><span data-stu-id="8c160-150">Part</span></span>|<span data-ttu-id="8c160-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c160-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="8c160-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c160-152">Required.</span></span> <span data-ttu-id="8c160-153">Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="8c160-154">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c160-154">Required.</span></span> <span data-ttu-id="8c160-155">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="8c160-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="8c160-156">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-156">Optional.</span></span> <span data-ttu-id="8c160-157">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="8c160-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="8c160-158">Vedere [handle](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="8c160-159">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="8c160-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="8c160-160">Elenco di eventi gestiti da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="8c160-161">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c160-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="8c160-162">Parte</span><span class="sxs-lookup"><span data-stu-id="8c160-162">Part</span></span>|<span data-ttu-id="8c160-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c160-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="8c160-164">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c160-164">Required.</span></span> <span data-ttu-id="8c160-165">Variabile oggetto dichiarata con il tipo di dati della classe o della struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="8c160-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="8c160-166">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c160-166">Required.</span></span> <span data-ttu-id="8c160-167">Nome dell'evento gestito da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="8c160-168">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8c160-168">Optional.</span></span> <span data-ttu-id="8c160-169">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="8c160-170">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c160-171">Commenti</span><span class="sxs-lookup"><span data-stu-id="8c160-171">Remarks</span></span>

<span data-ttu-id="8c160-172">Tutto il codice eseguibile deve trovarsi all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="8c160-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="8c160-173">Utilizzare una `Sub` stored procedure quando non si desidera restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8c160-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="8c160-174">Utilizzare una `Function` procedura quando si desidera restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="8c160-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="8c160-175">Definizione di una routine Sub</span><span class="sxs-lookup"><span data-stu-id="8c160-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="8c160-176">È possibile definire una `Sub` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="8c160-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="8c160-177">Il contesto di dichiarazione per una routine Sub deve pertanto essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco.</span><span class="sxs-lookup"><span data-stu-id="8c160-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="8c160-178">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="8c160-179">`Sub`per impostazione predefinita, le procedure sono con accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="8c160-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="8c160-180">È possibile modificare i livelli di accesso usando i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="8c160-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="8c160-181">Se la routine usa la `Implements` parola chiave, la classe o la struttura contenitore deve avere un' `Implements` istruzione che segue immediatamente la relativa `Class` `Structure` istruzione o.</span><span class="sxs-lookup"><span data-stu-id="8c160-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="8c160-182">L' `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="8c160-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="8c160-183">Tuttavia, il nome con cui un'interfaccia definisce `Sub` (in `definedname` ) non deve corrispondere al nome di questa procedura (in `name` ).</span><span class="sxs-lookup"><span data-stu-id="8c160-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="8c160-184">Restituzione da una routine Sub</span><span class="sxs-lookup"><span data-stu-id="8c160-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="8c160-185">Quando una `Sub` procedura viene restituita al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="8c160-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="8c160-186">Nell'esempio seguente viene illustrato un ritorno da una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="8c160-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="8c160-187">Le `Exit Sub` `Return` istruzioni e generano un'uscita immediata da una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="8c160-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="8c160-188">Qualsiasi numero di `Exit Sub` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Sub` `Return` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="8c160-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="8c160-189">Chiamata a una procedura secondaria</span><span class="sxs-lookup"><span data-stu-id="8c160-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="8c160-190">Per chiamare una `Sub` stored procedure, utilizzare il nome della stored procedure in un'istruzione e quindi seguire tale nome con l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8c160-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="8c160-191">È possibile omettere le parentesi solo se non si forniscono argomenti.</span><span class="sxs-lookup"><span data-stu-id="8c160-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="8c160-192">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="8c160-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="8c160-193">Una `Sub` routine e una `Function` procedura possono avere parametri ed eseguire una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8c160-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="8c160-194">Tuttavia, una `Function` routine restituisce un valore e una `Sub` procedura non lo è.</span><span class="sxs-lookup"><span data-stu-id="8c160-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="8c160-195">Pertanto, non è possibile utilizzare una `Sub` stored procedure in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8c160-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="8c160-196">È possibile utilizzare la `Call` parola chiave quando si chiama una `Sub` routine, ma tale parola chiave non è consigliata per la maggior parte degli utilizzi.</span><span class="sxs-lookup"><span data-stu-id="8c160-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="8c160-197">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="8c160-198">Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna.</span><span class="sxs-lookup"><span data-stu-id="8c160-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="8c160-199">Per questo motivo, se nell'elenco di argomenti sono incluse espressioni che chiamano altre routine, non è necessario presupporre che tali espressioni verranno richiamate in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="8c160-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="8c160-200">Procedure secondarie asincrone</span><span class="sxs-lookup"><span data-stu-id="8c160-200">Async Sub Procedures</span></span>

<span data-ttu-id="8c160-201">Utilizzando la funzionalità asincrona, è possibile richiamare funzioni asincrone senza utilizzare callback espliciti o suddividere manualmente il codice tra più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="8c160-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="8c160-202">Se si contrassegna una routine con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nella procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="8c160-203">Quando il controllo raggiunge un' `Await` espressione nella `Async` routine, il controllo torna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="8c160-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="8c160-204">Al termine dell'attività, l'esecuzione può riprendere nella procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="8c160-205">Una `Async` routine viene restituita al chiamante quando viene rilevato il primo oggetto atteso che non è ancora completo o viene raggiunta la fine della `Async` procedura, a seconda di quale si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="8c160-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="8c160-206">È anche possibile contrassegnare un' [istruzione di funzione](function-statement.md) con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="8c160-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="8c160-207">Una `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="8c160-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="8c160-208">Un esempio più avanti in questo argomento illustra una `Async` funzione con tipo restituito <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="8c160-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="8c160-209">`Async``Sub`le stored procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="8c160-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="8c160-210">Una `Async` `Sub` routine non può essere attesa e il chiamante di una `Async` `Sub` stored procedure non può intercettare le eccezioni `Sub` generate dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="8c160-211">Una `Async` routine non può dichiarare parametri [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="8c160-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="8c160-212">Per altre informazioni sulle `Async` procedure, vedere [programmazione asincrona con Async e await](../../programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="8c160-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="8c160-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c160-213">Example</span></span>

<span data-ttu-id="8c160-214">Nell'esempio seguente viene utilizzata l' `Sub` istruzione per definire il nome, i parametri e il codice che formano il corpo di una `Sub` routine.</span><span class="sxs-lookup"><span data-stu-id="8c160-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="8c160-215">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c160-215">Example</span></span>

<span data-ttu-id="8c160-216">Nell'esempio seguente `DelayAsync` è un oggetto `Async` `Function` che ha un tipo restituito <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="8c160-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="8c160-217">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="8c160-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="8c160-218">La dichiarazione di funzione di `DelayAsync` deve pertanto avere un tipo restituito di `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="8c160-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="8c160-219">Poiché il tipo restituito è `Task(Of Integer)` , la valutazione dell' `Await` espressione in `DoSomethingAsync` produce un Integer, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="8c160-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="8c160-220">La `startButton_Click` procedura è un esempio di `Async Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8c160-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="8c160-221">Poiché `DoSomethingAsync` è una `Async` funzione, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="8c160-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="8c160-222">La `startButton_Click` `Sub` procedura deve essere definita con il `Async` modificatore perché contiene un' `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="8c160-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8c160-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c160-223">See also</span></span>

- [<span data-ttu-id="8c160-224">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="8c160-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="8c160-225">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="8c160-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="8c160-226">Elenco parametri</span><span class="sxs-lookup"><span data-stu-id="8c160-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="8c160-227">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="8c160-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="8c160-228">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="8c160-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="8c160-229">Di</span><span class="sxs-lookup"><span data-stu-id="8c160-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="8c160-230">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="8c160-230">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="8c160-231">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="8c160-231">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="8c160-232">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="8c160-232">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="8c160-233">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="8c160-233">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
