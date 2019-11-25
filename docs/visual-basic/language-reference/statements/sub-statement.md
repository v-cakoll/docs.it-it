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
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="0b2dc-102">Istruzione Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b2dc-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="0b2dc-103">Declares the name, parameters, and code that define a `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b2dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b2dc-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="0b2dc-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0b2dc-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="0b2dc-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-106">Optional.</span></span> <span data-ttu-id="0b2dc-107">See [Attribute List](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="0b2dc-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-108">Optional.</span></span> <span data-ttu-id="0b2dc-109">Indicates definition of a partial method.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="0b2dc-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="0b2dc-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-111">Optional.</span></span> <span data-ttu-id="0b2dc-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b2dc-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="0b2dc-113">Public</span><span class="sxs-lookup"><span data-stu-id="0b2dc-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="0b2dc-114">Protected</span><span class="sxs-lookup"><span data-stu-id="0b2dc-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="0b2dc-115">Friend</span><span class="sxs-lookup"><span data-stu-id="0b2dc-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="0b2dc-116">Private</span><span class="sxs-lookup"><span data-stu-id="0b2dc-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="0b2dc-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="0b2dc-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="0b2dc-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0b2dc-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="0b2dc-119">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="0b2dc-120">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-120">Optional.</span></span> <span data-ttu-id="0b2dc-121">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b2dc-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="0b2dc-122">Overload</span><span class="sxs-lookup"><span data-stu-id="0b2dc-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="0b2dc-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="0b2dc-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="0b2dc-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="0b2dc-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="0b2dc-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="0b2dc-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="0b2dc-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="0b2dc-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="0b2dc-127">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-127">Optional.</span></span> <span data-ttu-id="0b2dc-128">See [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="0b2dc-129">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-129">Optional.</span></span> <span data-ttu-id="0b2dc-130">See [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="0b2dc-131">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-131">Optional.</span></span> <span data-ttu-id="0b2dc-132">See [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="0b2dc-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-133">Required.</span></span> <span data-ttu-id="0b2dc-134">Name of the procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-134">Name of the procedure.</span></span> <span data-ttu-id="0b2dc-135">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="0b2dc-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="0b2dc-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="0b2dc-138">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-138">Optional.</span></span> <span data-ttu-id="0b2dc-139">List of type parameters for a generic procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="0b2dc-140">See [Type List](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="0b2dc-141">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-141">Optional.</span></span> <span data-ttu-id="0b2dc-142">List of local variable names representing the parameters of this procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="0b2dc-143">See [Parameter List](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="0b2dc-144">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-144">Optional.</span></span> <span data-ttu-id="0b2dc-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="0b2dc-146">See [Implements Statement](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="0b2dc-147">Necessario se si fornisce `Implements`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="0b2dc-148">Elenco delle routine `Sub` implementate.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="0b2dc-149">Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b2dc-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="0b2dc-150">Parte</span><span class="sxs-lookup"><span data-stu-id="0b2dc-150">Part</span></span>|<span data-ttu-id="0b2dc-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b2dc-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="0b2dc-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-152">Required.</span></span> <span data-ttu-id="0b2dc-153">Name of an interface implemented by this procedure's containing class or structure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="0b2dc-154">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-154">Required.</span></span> <span data-ttu-id="0b2dc-155">Nome mediante il quale la routine viene definita in `interface`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="0b2dc-156">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-156">Optional.</span></span> <span data-ttu-id="0b2dc-157">Indicates that this procedure can handle one or more specific events.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="0b2dc-158">See [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="0b2dc-159">Necessario se si fornisce `Handles`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="0b2dc-160">List of events this procedure handles.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="0b2dc-161">Ogni `eventspecifier` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b2dc-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="0b2dc-162">Parte</span><span class="sxs-lookup"><span data-stu-id="0b2dc-162">Part</span></span>|<span data-ttu-id="0b2dc-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b2dc-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="0b2dc-164">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-164">Required.</span></span> <span data-ttu-id="0b2dc-165">Object variable declared with the data type of the class or structure that raises the event.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="0b2dc-166">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-166">Required.</span></span> <span data-ttu-id="0b2dc-167">Name of the event this procedure handles.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="0b2dc-168">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-168">Optional.</span></span> <span data-ttu-id="0b2dc-169">Block of statements to run within this procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="0b2dc-170">Terminates the definition of this procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b2dc-171">Note</span><span class="sxs-lookup"><span data-stu-id="0b2dc-171">Remarks</span></span>

<span data-ttu-id="0b2dc-172">All executable code must be inside a procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="0b2dc-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="0b2dc-174">Use a `Function` procedure when you want to return a value.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="0b2dc-175">Defining a Sub Procedure</span><span class="sxs-lookup"><span data-stu-id="0b2dc-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="0b2dc-176">You can define a `Sub` procedure only at the module level.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="0b2dc-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="0b2dc-178">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="0b2dc-179">`Sub` procedures default to public access.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="0b2dc-180">You can adjust their access levels by using the access modifiers.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="0b2dc-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="0b2dc-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="0b2dc-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="0b2dc-184">Returning from a Sub Procedure</span><span class="sxs-lookup"><span data-stu-id="0b2dc-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="0b2dc-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="0b2dc-186">The following example shows a return from a `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="0b2dc-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="0b2dc-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="0b2dc-189">Calling a Sub Procedure</span><span class="sxs-lookup"><span data-stu-id="0b2dc-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="0b2dc-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="0b2dc-191">You can omit the parentheses only if you don't supply any arguments.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="0b2dc-192">However, your code is more readable if you always include the parentheses.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="0b2dc-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="0b2dc-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="0b2dc-195">Therefore, you can't use a `Sub` procedure in an expression.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="0b2dc-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="0b2dc-197">For more information, see [Call Statement](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="0b2dc-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="0b2dc-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="0b2dc-200">Async Sub Procedures</span><span class="sxs-lookup"><span data-stu-id="0b2dc-200">Async Sub Procedures</span></span>

<span data-ttu-id="0b2dc-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="0b2dc-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="0b2dc-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="0b2dc-204">When the task is complete, execution can resume in the procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="0b2dc-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="0b2dc-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="0b2dc-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="0b2dc-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="0b2dc-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="0b2dc-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="0b2dc-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="0b2dc-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="0b2dc-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b2dc-213">Example</span></span>

<span data-ttu-id="0b2dc-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="0b2dc-215">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b2dc-215">Example</span></span>

<span data-ttu-id="0b2dc-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="0b2dc-217">`DelayAsync` ha un'istruzione `Return` che restituisce un numero intero.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="0b2dc-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="0b2dc-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="0b2dc-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="0b2dc-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="0b2dc-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="0b2dc-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b2dc-223">See also</span></span>

- [<span data-ttu-id="0b2dc-224">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="0b2dc-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="0b2dc-225">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="0b2dc-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="0b2dc-226">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="0b2dc-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="0b2dc-227">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="0b2dc-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="0b2dc-228">Istruzione Call</span><span class="sxs-lookup"><span data-stu-id="0b2dc-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="0b2dc-229">Of</span><span class="sxs-lookup"><span data-stu-id="0b2dc-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="0b2dc-230">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="0b2dc-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="0b2dc-231">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="0b2dc-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="0b2dc-232">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="0b2dc-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="0b2dc-233">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="0b2dc-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
