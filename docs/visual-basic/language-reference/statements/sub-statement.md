---
title: Istruzione Sub (Visual Basic)
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
ms.openlocfilehash: ab94865f4881b40b38f67eb40d2f9fa2e1982af8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817227"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="4a5b7-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a5b7-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="4a5b7-103">Dichiara il nome, parametri e il codice che definiscono un `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a5b7-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="4a5b7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4a5b7-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4a5b7-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-106">Optional.</span></span> <span data-ttu-id="4a5b7-107">Visualizzare [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="4a5b7-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-108">Optional.</span></span> <span data-ttu-id="4a5b7-109">Indica la definizione di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="4a5b7-110">Visualizzare [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4a5b7-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-111">Optional.</span></span> <span data-ttu-id="4a5b7-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a5b7-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4a5b7-113">Public</span><span class="sxs-lookup"><span data-stu-id="4a5b7-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="4a5b7-114">Protected</span><span class="sxs-lookup"><span data-stu-id="4a5b7-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="4a5b7-115">Friend</span><span class="sxs-lookup"><span data-stu-id="4a5b7-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="4a5b7-116">Private</span><span class="sxs-lookup"><span data-stu-id="4a5b7-116">Private</span></span>](../modifiers/private.md)  
  
    - [<span data-ttu-id="4a5b7-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="4a5b7-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="4a5b7-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="4a5b7-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="4a5b7-119">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="4a5b7-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-120">Optional.</span></span> <span data-ttu-id="4a5b7-121">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a5b7-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4a5b7-122">Overload</span><span class="sxs-lookup"><span data-stu-id="4a5b7-122">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4a5b7-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="4a5b7-123">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4a5b7-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="4a5b7-124">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4a5b7-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4a5b7-125">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4a5b7-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4a5b7-126">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4a5b7-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-127">Optional.</span></span> <span data-ttu-id="4a5b7-128">Visualizzare [condiviso](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-128">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4a5b7-129">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-129">Optional.</span></span> <span data-ttu-id="4a5b7-130">Visualizzare [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-130">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="4a5b7-131">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-131">Optional.</span></span> <span data-ttu-id="4a5b7-132">Visualizzare [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-132">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4a5b7-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-133">Required.</span></span> <span data-ttu-id="4a5b7-134">Nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-134">Name of the procedure.</span></span> <span data-ttu-id="4a5b7-135">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="4a5b7-136">Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="4a5b7-137">Per altre informazioni, vedere [durata degli oggetti: Come gli oggetti vengono creati e distrutti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="4a5b7-138">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-138">Optional.</span></span> <span data-ttu-id="4a5b7-139">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="4a5b7-140">Visualizzare [elenco dei tipi](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-140">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4a5b7-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-141">Optional.</span></span> <span data-ttu-id="4a5b7-142">Elenco di nomi delle variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="4a5b7-143">Visualizzare [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-143">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4a5b7-144">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-144">Optional.</span></span> <span data-ttu-id="4a5b7-145">Indica che questa procedura consente di implementare uno o più `Sub` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="4a5b7-146">Visualizzare [implementa istruzione](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-146">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4a5b7-147">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4a5b7-148">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-148">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="4a5b7-149">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a5b7-149">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4a5b7-150">Parte</span><span class="sxs-lookup"><span data-stu-id="4a5b7-150">Part</span></span>|<span data-ttu-id="4a5b7-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a5b7-151">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4a5b7-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-152">Required.</span></span> <span data-ttu-id="4a5b7-153">Classe o struttura contenente nome di un'interfaccia implementata da questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4a5b7-154">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-154">Required.</span></span> <span data-ttu-id="4a5b7-155">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-155">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="4a5b7-156">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-156">Optional.</span></span> <span data-ttu-id="4a5b7-157">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="4a5b7-158">Visualizzare [gestisce](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-158">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="4a5b7-159">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="4a5b7-160">Elenco di eventi che gestisce questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-160">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="4a5b7-161">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a5b7-161">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="4a5b7-162">Parte</span><span class="sxs-lookup"><span data-stu-id="4a5b7-162">Part</span></span>|<span data-ttu-id="4a5b7-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a5b7-163">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="4a5b7-164">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-164">Required.</span></span> <span data-ttu-id="4a5b7-165">Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="4a5b7-166">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-166">Required.</span></span> <span data-ttu-id="4a5b7-167">Nome dell'evento gestito da questa routine.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-167">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="4a5b7-168">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-168">Optional.</span></span> <span data-ttu-id="4a5b7-169">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-169">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="4a5b7-170">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-170">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a5b7-171">Note</span><span class="sxs-lookup"><span data-stu-id="4a5b7-171">Remarks</span></span>  
 <span data-ttu-id="4a5b7-172">Tutto il codice eseguibile deve essere all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="4a5b7-173">Usare un `Sub` procedure quando non si vuole restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="4a5b7-174">Usare un `Function` procedure quando si vuole restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-174">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="4a5b7-175">La definizione di una routine Sub</span><span class="sxs-lookup"><span data-stu-id="4a5b7-175">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="4a5b7-176">È possibile definire un `Sub` procedure solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="4a5b7-177">Il contesto della dichiarazione per una routine sub deve, pertanto, essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="4a5b7-178">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4a5b7-179">`Sub` Per impostazione predefinita le procedure per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="4a5b7-180">È possibile modificare i livelli di accesso usando i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-180">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="4a5b7-181">Se la procedura Usa il `Implements` parola chiave, alla classe o struttura deve avere un `Implements` istruzione che segue immediatamente relativo `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4a5b7-182">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="4a5b7-183">Tuttavia, il nome mediante il quale definisce un'interfaccia di `Sub` (in `definedname`) non deve necessariamente corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="4a5b7-184">Restituzione da una routine Sub</span><span class="sxs-lookup"><span data-stu-id="4a5b7-184">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="4a5b7-185">Quando un `Sub` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="4a5b7-186">Nell'esempio seguente viene illustrata la restituzione da una `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-186">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="4a5b7-187">Il `Exit Sub` e `Return` istruzioni uscire immediatamente da un `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="4a5b7-188">Un numero qualsiasi di `Exit Sub` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Sub` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="4a5b7-189">Chiamare una routine Sub</span><span class="sxs-lookup"><span data-stu-id="4a5b7-189">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="4a5b7-190">Si chiama un `Sub` procedura usando il nome della routine in un'istruzione e quindi seguire tale nome con il relativo elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="4a5b7-191">Solo se non si fornisce alcun argomento, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="4a5b7-192">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-192">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="4a5b7-193">Oggetto `Sub` procedure e un `Function` procedura può avere parametri ed eseguire una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="4a5b7-194">Tuttavia, un `Function` routine restituisce un valore e un `Sub` non di procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="4a5b7-195">Pertanto, è possibile utilizzare un `Sub` procedure in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="4a5b7-196">È possibile usare la `Call` parola chiave quando si chiama un `Sub` routine, ma tale parola chiave non è consigliato per la maggior parte degli utilizzi.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="4a5b7-197">Per altre informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-197">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="4a5b7-198">In alcuni casi, Visual Basic ridispone espressioni aritmetiche per aumentare l'efficienza interno.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="4a5b7-199">Per questo motivo, se all'elenco di argomenti sono incluse le espressioni che chiamano altre procedure, si dovrebbero evitare supposizioni che verranno chiamate tali espressioni in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="4a5b7-200">Routine Sub Async</span><span class="sxs-lookup"><span data-stu-id="4a5b7-200">Async Sub Procedures</span></span>  
 <span data-ttu-id="4a5b7-201">Usando la funzionalità Async, è possibile richiamare le funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="4a5b7-202">Se si contrassegna una procedura con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="4a5b7-203">Quando il controllo raggiunge un' `Await` espressione nel `Async` procedure, il controllo ritorna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="4a5b7-204">Una volta completata l'attività, l'esecuzione può riprendere la procedura.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-204">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a5b7-205">Un' `Async` routine restituisce al chiamante quando viene rilevato un il primo oggetto atteso che non è ancora completo o alla fine del `Async` procedure viene raggiunta, qualunque si verifichi prima.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="4a5b7-206">È inoltre possibile contrassegnare un [istruzione Function](function-statement.md) con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="4a5b7-207">Un' `Async` funzione può avere un tipo restituito <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="4a5b7-208">Un esempio più avanti in questo argomento viene illustrato un `Async` che presenta un tipo restituito della funzione <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="4a5b7-209">`Async` `Sub` le procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="4a5b7-210">Un' `Async` `Sub` routine non può essere atteso e il chiamante di un `Async` `Sub` procedure non può intercettare le eccezioni che il `Sub` routine genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="4a5b7-211">Un' `Async` routine non può dichiarare [ByRef](../modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="4a5b7-212">Per altre informazioni sulle `Async` procedure, vedere [programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="4a5b7-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5b7-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a5b7-213">Example</span></span>  
 <span data-ttu-id="4a5b7-214">L'esempio seguente usa il `Sub` istruzione per definire il nome, parametri e codice che costituiscono il corpo di un `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="4a5b7-215">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a5b7-215">Example</span></span>  
 <span data-ttu-id="4a5b7-216">Nell'esempio riportato di seguito `DelayAsync` è un `Async` `Function` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4a5b7-217">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="4a5b7-218">Pertanto, la dichiarazione della funzione di `DelayAsync` deve presentare un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="4a5b7-219">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione nella `DoSomethingAsync` genera un numero intero, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="4a5b7-220">Il `startButton_Click` procedure è un esempio di un `Async Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="4a5b7-221">In quanto `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="4a5b7-222">Il `startButton_Click` `Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="4a5b7-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4a5b7-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a5b7-223">See also</span></span>

- [<span data-ttu-id="4a5b7-224">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="4a5b7-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="4a5b7-225">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="4a5b7-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="4a5b7-226">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="4a5b7-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="4a5b7-227">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="4a5b7-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="4a5b7-228">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="4a5b7-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="4a5b7-229">Of</span><span class="sxs-lookup"><span data-stu-id="4a5b7-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="4a5b7-230">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="4a5b7-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="4a5b7-231">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="4a5b7-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="4a5b7-232">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="4a5b7-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="4a5b7-233">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="4a5b7-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
