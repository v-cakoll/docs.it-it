---
title: Sub Statement (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
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
ms.openlocfilehash: 61853a4f2321837683997b8e4241b688bc9f622c
ms.contentlocale: it-it
ms.lasthandoff: 05/15/2017

---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="8253a-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8253a-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="8253a-103">Dichiara il nome, parametri e il codice che definiscono un `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8253a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8253a-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="8253a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8253a-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="8253a-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-106">Optional.</span></span> <span data-ttu-id="8253a-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="8253a-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-108">Optional.</span></span> <span data-ttu-id="8253a-109">Indica la definizione di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="8253a-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="8253a-110">Vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="8253a-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-111">Optional.</span></span> <span data-ttu-id="8253a-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8253a-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="8253a-113">Public</span><span class="sxs-lookup"><span data-stu-id="8253a-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="8253a-114">Protected</span><span class="sxs-lookup"><span data-stu-id="8253a-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="8253a-115">Friend</span><span class="sxs-lookup"><span data-stu-id="8253a-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="8253a-116">Private</span><span class="sxs-lookup"><span data-stu-id="8253a-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="8253a-117">Vedere [livelli in Visual Basic di accesso](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-117">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="8253a-118">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-118">Optional.</span></span> <span data-ttu-id="8253a-119">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8253a-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="8253a-120">Overload</span><span class="sxs-lookup"><span data-stu-id="8253a-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="8253a-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="8253a-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="8253a-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="8253a-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="8253a-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="8253a-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="8253a-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="8253a-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="8253a-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-125">Optional.</span></span> <span data-ttu-id="8253a-126">Vedere [condivisi](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="8253a-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-127">Optional.</span></span> <span data-ttu-id="8253a-128">Vedere [ombreggiature](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="8253a-129">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-129">Optional.</span></span> <span data-ttu-id="8253a-130">Vedere [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="8253a-131">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8253a-131">Required.</span></span> <span data-ttu-id="8253a-132">Nome della routine.</span><span class="sxs-lookup"><span data-stu-id="8253a-132">Name of the procedure.</span></span> <span data-ttu-id="8253a-133">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="8253a-134">Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="8253a-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="8253a-135">Per ulteriori informazioni, vedere [la durata degli oggetti: come gli oggetti sono creare e distruggere](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="8253a-136">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-136">Optional.</span></span> <span data-ttu-id="8253a-137">Elenco di parametri di tipo per una procedura generica.</span><span class="sxs-lookup"><span data-stu-id="8253a-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="8253a-138">Vedere [digitare elenco](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="8253a-139">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-139">Optional.</span></span> <span data-ttu-id="8253a-140">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="8253a-141">Vedere [elenco parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="8253a-142">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-142">Optional.</span></span> <span data-ttu-id="8253a-143">Indica che questa procedura viene implementato uno o più `Sub` procedure, ognuna definita in un'interfaccia implementata dalla classe o struttura che contiene questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="8253a-144">Vedere [implementa istruzione](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="8253a-145">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="8253a-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="8253a-146">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="8253a-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="8253a-147">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8253a-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="8253a-148">Parte</span><span class="sxs-lookup"><span data-stu-id="8253a-148">Part</span></span>|<span data-ttu-id="8253a-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8253a-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="8253a-150">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8253a-150">Required.</span></span> <span data-ttu-id="8253a-151">Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="8253a-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="8253a-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8253a-152">Required.</span></span> <span data-ttu-id="8253a-153">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="8253a-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="8253a-154">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-154">Optional.</span></span> <span data-ttu-id="8253a-155">Indica che questa procedura può gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="8253a-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="8253a-156">Vedere [gestisce](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="8253a-157">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="8253a-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="8253a-158">Elenco di eventi gestiti dalla routine.</span><span class="sxs-lookup"><span data-stu-id="8253a-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="8253a-159">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8253a-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="8253a-160">Parte</span><span class="sxs-lookup"><span data-stu-id="8253a-160">Part</span></span>|<span data-ttu-id="8253a-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8253a-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="8253a-162">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8253a-162">Required.</span></span> <span data-ttu-id="8253a-163">Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="8253a-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="8253a-164">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8253a-164">Required.</span></span> <span data-ttu-id="8253a-165">Nome dell'evento gestito dalla routine.</span><span class="sxs-lookup"><span data-stu-id="8253a-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="8253a-166">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8253a-166">Optional.</span></span> <span data-ttu-id="8253a-167">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="8253a-168">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8253a-169">Note</span><span class="sxs-lookup"><span data-stu-id="8253a-169">Remarks</span></span>  
 <span data-ttu-id="8253a-170">Tutto il codice eseguibile deve essere all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="8253a-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="8253a-171">Utilizzare un `Sub` procedure quando non si desidera restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8253a-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="8253a-172">Utilizzare un `Function` procedura quando si desidera restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="8253a-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="8253a-173">Definizione di una routine Sub</span><span class="sxs-lookup"><span data-stu-id="8253a-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="8253a-174">È possibile definire un `Sub` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="8253a-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="8253a-175">Il contesto della dichiarazione per una routine sub deve, pertanto, essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="8253a-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="8253a-176">Per ulteriori informazioni, vedere [contesti delle dichiarazioni e livelli di accesso predefinito](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="8253a-177">`Sub`Per impostazione predefinita le procedure per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="8253a-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="8253a-178">È possibile regolare i livelli di accesso mediante i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="8253a-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="8253a-179">Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve avere un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8253a-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="8253a-180">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="8253a-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="8253a-181">Tuttavia, il nome con cui si definisce un'interfaccia di `Sub` (in `definedname`) non deve necessariamente corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="8253a-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="8253a-182">Restituzione da una routine Sub</span><span class="sxs-lookup"><span data-stu-id="8253a-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="8253a-183">Quando un `Sub` procedure restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo hanno chiamato.</span><span class="sxs-lookup"><span data-stu-id="8253a-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="8253a-184">Nell'esempio seguente viene illustrato un ritorno da una `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="8253a-185">Il `Exit Sub` e `Return` istruzioni uscire immediatamente da un `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="8253a-186">Un numero qualsiasi di `Exit Sub` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Sub` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8253a-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="8253a-187">Chiamare una routine Sub</span><span class="sxs-lookup"><span data-stu-id="8253a-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="8253a-188">Si chiama un `Sub` procedure utilizzando il nome della routine in un'istruzione e quindi seguendo questo nome con il relativo elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8253a-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="8253a-189">È possibile omettere le parentesi solo se non si fornisce alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="8253a-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="8253a-190">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="8253a-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="8253a-191">Oggetto `Sub` procedura e un `Function` procedura può avere parametri ed eseguire una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8253a-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="8253a-192">Tuttavia, un `Function` procedura restituisce un valore e un `Sub` non di procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="8253a-193">Pertanto, è possibile utilizzare un `Sub` procedure in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8253a-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="8253a-194">È possibile utilizzare il `Call` parola chiave quando si chiama un `Sub` procedura, ma la parola chiave non è consigliato per la maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="8253a-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="8253a-195">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="8253a-196">Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interna.</span><span class="sxs-lookup"><span data-stu-id="8253a-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="8253a-197">Per questo motivo, se all'elenco di argomenti sono incluse le espressioni che chiamano altre routine, non deve presupporre che le espressioni verranno chiamate in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="8253a-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="8253a-198">Async Sub (routine)</span><span class="sxs-lookup"><span data-stu-id="8253a-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="8253a-199">Utilizzando la funzionalità Async, è possibile richiamare funzioni asincrone senza utilizzare callback esplicito o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="8253a-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="8253a-200">Se si contrassegna una routine con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="8253a-201">Quando il controllo raggiunge un `Await` espressione la `Async` procedura, il controllo ritorna al chiamante e lo stato di avanzamento della procedura viene sospesa fino al completamento dell'attività di attesa.</span><span class="sxs-lookup"><span data-stu-id="8253a-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="8253a-202">Una volta completata l'attività, nella procedura possibile riprendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8253a-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8253a-203">Un `Async` restituito al chiamante quando viene rilevato un il primo oggetto atteso che non è ancora completo o alla fine della routine di `Async` procedura viene raggiunto, qualunque si verifichi prima.</span><span class="sxs-lookup"><span data-stu-id="8253a-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="8253a-204">È inoltre possibile contrassegnare un [istruzione Function](function-statement.md) con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="8253a-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="8253a-205">Un `Async` funzione può avere un tipo restituito <xref:System.Threading.Tasks.Task%601>o <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="8253a-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="8253a-206">Un esempio più avanti in questo argomento viene illustrato un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="8253a-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="8253a-207">`Async``Sub` procedure vengono utilizzate principalmente per i gestori eventi, in cui non può essere restituito un valore.</span><span class="sxs-lookup"><span data-stu-id="8253a-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="8253a-208">Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni che il `Sub` procedura genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8253a-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="8253a-209">Un `Async` procedura non può dichiarare [ByRef](../modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="8253a-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="8253a-210">Per ulteriori informazioni su `Async` procedure, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [Async restituire tipi](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="8253a-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8253a-211">Esempio</span><span class="sxs-lookup"><span data-stu-id="8253a-211">Example</span></span>  
 <span data-ttu-id="8253a-212">Nell'esempio seguente viene utilizzata la `Sub` istruzione per definire il nome, parametri e il codice che formano il corpo di un `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="8253a-213">[!code-vb[VbVbalrStatements&#58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8253a-213">[!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8253a-214">Esempio</span><span class="sxs-lookup"><span data-stu-id="8253a-214">Example</span></span>  
 <span data-ttu-id="8253a-215">Nell'esempio seguente, `DelayAsync` è un un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="8253a-215">In the following example, `DelayAsync` is an an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="8253a-216">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="8253a-216">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="8253a-217">Pertanto, la dichiarazione della funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="8253a-217">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="8253a-218">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione di `Await` espressione `DoSomethingAsync` produce un numero intero, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="8253a-218">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="8253a-219">Il `startButton_Click` procedura è un esempio di un `Async Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="8253a-219">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="8253a-220">Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere atteso, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="8253a-220">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="8253a-221">Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="8253a-221">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="8253a-222">[!code-vb[csAsyncMethod n.&1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8253a-222">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8253a-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8253a-223">See Also</span></span>  
 <span data-ttu-id="8253a-224">[Implements (istruzione)](implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-224">[Implements Statement](implements-statement.md) </span></span>  
<span data-ttu-id="8253a-225"> [Istruzione Function](function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-225"> [Function Statement](function-statement.md) </span></span>  
<span data-ttu-id="8253a-226"> [Elenco di parametri](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-226"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="8253a-227"> [Dim (istruzione)](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-227"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="8253a-228"> [Istruzione Call](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-228"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="8253a-229"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-229"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="8253a-230"> [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-230"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="8253a-231"> [Procedura: utilizzare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-231"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="8253a-232"> [Le procedure di risoluzione](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8253a-232"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="8253a-233"> [Metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span><span class="sxs-lookup"><span data-stu-id="8253a-233"> [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span></span>

