---
title: Istruzione Sub (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Sub
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
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a2d0d5ffdca857a3a5ca58cd38b0930f254526f
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="58186-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58186-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="58186-103">Dichiara il nome, parametri e il codice che definiscono un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58186-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58186-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="58186-105">Parti</span><span class="sxs-lookup"><span data-stu-id="58186-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="58186-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-106">Optional.</span></span> <span data-ttu-id="58186-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="58186-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="58186-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-108">Optional.</span></span> <span data-ttu-id="58186-109">Indica la definizione di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="58186-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="58186-110">Vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="58186-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="58186-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-111">Optional.</span></span> <span data-ttu-id="58186-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="58186-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="58186-113">Public</span><span class="sxs-lookup"><span data-stu-id="58186-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="58186-114">Protected</span><span class="sxs-lookup"><span data-stu-id="58186-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="58186-115">Friend</span><span class="sxs-lookup"><span data-stu-id="58186-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="58186-116">Private</span><span class="sxs-lookup"><span data-stu-id="58186-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="58186-117">Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="58186-117">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="58186-118">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-118">Optional.</span></span> <span data-ttu-id="58186-119">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="58186-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="58186-120">Overload</span><span class="sxs-lookup"><span data-stu-id="58186-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="58186-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="58186-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="58186-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="58186-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="58186-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="58186-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="58186-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="58186-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="58186-125">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-125">Optional.</span></span> <span data-ttu-id="58186-126">Vedere [condiviso](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="58186-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="58186-127">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-127">Optional.</span></span> <span data-ttu-id="58186-128">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="58186-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="58186-129">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-129">Optional.</span></span> <span data-ttu-id="58186-130">Vedere [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="58186-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="58186-131">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58186-131">Required.</span></span> <span data-ttu-id="58186-132">Nome della routine.</span><span class="sxs-lookup"><span data-stu-id="58186-132">Name of the procedure.</span></span> <span data-ttu-id="58186-133">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="58186-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="58186-134">Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="58186-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="58186-135">Per ulteriori informazioni, vedere [durata degli oggetti: come gli oggetti sono di creare e distruggere](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="58186-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="58186-136">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-136">Optional.</span></span> <span data-ttu-id="58186-137">Elenco di parametri di tipo per una routine generica.</span><span class="sxs-lookup"><span data-stu-id="58186-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="58186-138">Vedere [digitare elenco](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="58186-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="58186-139">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-139">Optional.</span></span> <span data-ttu-id="58186-140">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="58186-141">Vedere [elenco parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="58186-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="58186-142">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-142">Optional.</span></span> <span data-ttu-id="58186-143">Indica che questa procedura consente di implementare una o più `Sub` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="58186-144">Vedere [implementa istruzione](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="58186-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="58186-145">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="58186-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="58186-146">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="58186-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="58186-147">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="58186-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="58186-148">Parte</span><span class="sxs-lookup"><span data-stu-id="58186-148">Part</span></span>|<span data-ttu-id="58186-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58186-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="58186-150">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58186-150">Required.</span></span> <span data-ttu-id="58186-151">Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="58186-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="58186-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58186-152">Required.</span></span> <span data-ttu-id="58186-153">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="58186-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="58186-154">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-154">Optional.</span></span> <span data-ttu-id="58186-155">Indica che questa procedura è possibile gestire uno o più eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="58186-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="58186-156">Vedere [gestisce](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="58186-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="58186-157">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="58186-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="58186-158">Elenco di eventi gestiti dalla routine.</span><span class="sxs-lookup"><span data-stu-id="58186-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="58186-159">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="58186-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="58186-160">Parte</span><span class="sxs-lookup"><span data-stu-id="58186-160">Part</span></span>|<span data-ttu-id="58186-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58186-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="58186-162">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58186-162">Required.</span></span> <span data-ttu-id="58186-163">Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="58186-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="58186-164">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58186-164">Required.</span></span> <span data-ttu-id="58186-165">Nome dell'evento che gestisce questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="58186-166">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58186-166">Optional.</span></span> <span data-ttu-id="58186-167">Blocco di istruzioni da eseguire all'interno di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="58186-168">Termina la definizione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58186-169">Note</span><span class="sxs-lookup"><span data-stu-id="58186-169">Remarks</span></span>  
 <span data-ttu-id="58186-170">Tutto il codice eseguibile deve essere all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="58186-171">Utilizzare un `Sub` procedure quando non si desidera restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="58186-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="58186-172">Utilizzare un `Function` procedura quando si desidera restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="58186-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="58186-173">Definizione di una routine Sub</span><span class="sxs-lookup"><span data-stu-id="58186-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="58186-174">È possibile definire un `Sub` procedura solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="58186-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="58186-175">Il contesto della dichiarazione per una routine sub, pertanto, deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="58186-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="58186-176">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="58186-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="58186-177">`Sub`procedure per impostazione predefinita l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="58186-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="58186-178">È possibile regolare i livelli di accesso tramite i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="58186-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="58186-179">Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve avere un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="58186-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="58186-180">Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="58186-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="58186-181">Tuttavia, il nome con cui si definisce un'interfaccia di `Sub` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).</span><span class="sxs-lookup"><span data-stu-id="58186-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="58186-182">Restituzione da una routine Sub</span><span class="sxs-lookup"><span data-stu-id="58186-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="58186-183">Quando un `Sub` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo hanno chiamato.</span><span class="sxs-lookup"><span data-stu-id="58186-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="58186-184">Nell'esempio seguente viene restituito da un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="58186-185">Il `Exit Sub` e `Return` istruzioni uscire immediatamente da un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="58186-186">Un numero qualsiasi di `Exit Sub` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Sub` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="58186-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="58186-187">La chiamata a una routine Sub</span><span class="sxs-lookup"><span data-stu-id="58186-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="58186-188">Si chiama un `Sub` procedure utilizzando il nome della stored procedure in un'istruzione e quindi seguendo questo nome con il relativo elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="58186-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="58186-189">È possibile omettere le parentesi solo se non si specifica alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="58186-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="58186-190">Tuttavia, il codice è più leggibile se si includono sempre le parentesi.</span><span class="sxs-lookup"><span data-stu-id="58186-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="58186-191">Oggetto `Sub` procedure e un `Function` procedura può avere parametri ed eseguire una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="58186-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="58186-192">Tuttavia, un `Function` stored procedure restituisce un valore e un `Sub` non di procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="58186-193">Pertanto, è possibile utilizzare un `Sub` procedure in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="58186-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="58186-194">È possibile utilizzare il `Call` (parola chiave) quando si chiama un `Sub` routine, ma tale parola chiave non è consigliato per la maggior parte degli utilizzi.</span><span class="sxs-lookup"><span data-stu-id="58186-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="58186-195">Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="58186-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="58186-196">Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interno.</span><span class="sxs-lookup"><span data-stu-id="58186-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="58186-197">Per questo motivo, se all'elenco di argomenti include espressioni che chiamano altre procedure, non deve presupporre che le espressioni verranno chiamate in un ordine particolare.</span><span class="sxs-lookup"><span data-stu-id="58186-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="58186-198">Async Sub (routine)</span><span class="sxs-lookup"><span data-stu-id="58186-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="58186-199">Tramite la funzionalità Async, è possibile richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="58186-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="58186-200">Se si contrassegna una procedura con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="58186-201">Quando il controllo raggiunge un' `Await` espressione il `Async` procedure, il controllo ritorna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="58186-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="58186-202">Quando l'attività viene completata, l'esecuzione può riprendere nella procedura.</span><span class="sxs-lookup"><span data-stu-id="58186-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58186-203">Un `Async` routine restituisce al chiamante quando viene rilevato un il primo oggetto atteso che non è ancora completo o alla fine del `Async` stored procedure viene raggiunto, qualunque si verifichi prima.</span><span class="sxs-lookup"><span data-stu-id="58186-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="58186-204">È inoltre possibile contrassegnare un [istruzione Function](function-statement.md) con il `Async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="58186-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="58186-205">Un `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="58186-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="58186-206">Un esempio più avanti in questo argomento viene illustrato un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="58186-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="58186-207">`Async``Sub` procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="58186-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="58186-208">Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni che il `Sub` genera stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="58186-209">Un `Async` procedura non può dichiarare [ByRef](../modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="58186-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="58186-210">Per ulteriori informazioni su `Async` procedure, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="58186-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58186-211">Esempio</span><span class="sxs-lookup"><span data-stu-id="58186-211">Example</span></span>  
 <span data-ttu-id="58186-212">L'esempio seguente usa il `Sub` istruzione per definire il nome, parametri e il codice che formano il corpo di un `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="58186-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="58186-213">Example</span></span>  
 <span data-ttu-id="58186-214">Nell'esempio seguente, `DelayAsync` è un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="58186-214">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="58186-215">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="58186-215">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="58186-216">Pertanto, la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="58186-216">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="58186-217">Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione `DoSomethingAsync` genera un numero intero, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="58186-217">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="58186-218">Il `startButton_Click` procedure è un esempio di un `Async Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="58186-218">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="58186-219">Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="58186-219">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="58186-220">Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.</span><span class="sxs-lookup"><span data-stu-id="58186-220">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="58186-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58186-221">See Also</span></span>  
 [<span data-ttu-id="58186-222">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="58186-222">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="58186-223">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="58186-223">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="58186-224">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="58186-224">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="58186-225">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="58186-225">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="58186-226">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="58186-226">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="58186-227">Of</span><span class="sxs-lookup"><span data-stu-id="58186-227">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="58186-228">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="58186-228">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="58186-229">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="58186-229">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="58186-230">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="58186-230">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="58186-231">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="58186-231">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
