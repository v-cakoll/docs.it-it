---
title: Operator Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b6be45fd0a606f43c14d57f3f8ae0955f256ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="operator-statement"></a><span data-ttu-id="7f382-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="7f382-102">Operator Statement</span></span>
<span data-ttu-id="7f382-103">Dichiara il simbolo di operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7f382-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f382-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f382-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="7f382-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7f382-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="7f382-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f382-106">Optional.</span></span> <span data-ttu-id="7f382-107">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="7f382-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-108">Required.</span></span> <span data-ttu-id="7f382-109">Indica che la routine di operatore esiste [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso.</span><span class="sxs-lookup"><span data-stu-id="7f382-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="7f382-110">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f382-110">Optional.</span></span> <span data-ttu-id="7f382-111">Vedere [overload](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="7f382-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-112">Required.</span></span> <span data-ttu-id="7f382-113">Indica che la routine di operatore è un [Shared](../../../visual-basic/language-reference/modifiers/shared.md) stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7f382-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="7f382-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f382-114">Optional.</span></span> <span data-ttu-id="7f382-115">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="7f382-116">Obbligatorio per un operatore di conversione, a meno che non si specifica `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="7f382-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="7f382-117">Indica che questa routine di operatore definisce un [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversione.</span><span class="sxs-lookup"><span data-stu-id="7f382-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="7f382-118">In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".</span><span class="sxs-lookup"><span data-stu-id="7f382-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="7f382-119">Obbligatorio per un operatore di conversione, a meno che non si specifica `Widening`.</span><span class="sxs-lookup"><span data-stu-id="7f382-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="7f382-120">Indica che questa routine di operatore definisce un [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversione.</span><span class="sxs-lookup"><span data-stu-id="7f382-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="7f382-121">In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".</span><span class="sxs-lookup"><span data-stu-id="7f382-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="7f382-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-122">Required.</span></span> <span data-ttu-id="7f382-123">Il simbolo o l'identificatore dell'operatore che definisce la routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="7f382-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="7f382-124">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-124">Required.</span></span> <span data-ttu-id="7f382-125">Il nome e tipo di operando singolo di un operatore unario (incluso un operatore di conversione) o l'operando sinistro dell'operatore binario.</span><span class="sxs-lookup"><span data-stu-id="7f382-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="7f382-126">Obbligatorio per gli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="7f382-126">Required for binary operators.</span></span> <span data-ttu-id="7f382-127">Nome e il tipo dell'operando di destra di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="7f382-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="7f382-128">`operand1`e `operand2` hanno la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f382-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="7f382-129">Parte</span><span class="sxs-lookup"><span data-stu-id="7f382-129">Part</span></span>|<span data-ttu-id="7f382-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f382-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="7f382-131">Parametro facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="7f382-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-132">Required.</span></span> <span data-ttu-id="7f382-133">Nome della variabile che rappresenta l'operando.</span><span class="sxs-lookup"><span data-stu-id="7f382-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="7f382-134">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="7f382-135">Facoltativo, a meno che `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="7f382-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="7f382-136">Tipo di dati di questo tipo di operando.</span><span class="sxs-lookup"><span data-stu-id="7f382-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="7f382-137">Facoltativo, a meno che `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="7f382-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="7f382-138">Restituisce il tipo di dati del valore di routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="7f382-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="7f382-139">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f382-139">Optional.</span></span> <span data-ttu-id="7f382-140">Blocco di istruzioni che esegue la routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="7f382-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="7f382-141">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-141">Required.</span></span> <span data-ttu-id="7f382-142">Il valore che la routine di operatore restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7f382-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="7f382-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="7f382-143">`End` `Operator`</span></span>  
 <span data-ttu-id="7f382-144">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f382-144">Required.</span></span> <span data-ttu-id="7f382-145">Termina la definizione di questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="7f382-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f382-146">Note</span><span class="sxs-lookup"><span data-stu-id="7f382-146">Remarks</span></span>  
 <span data-ttu-id="7f382-147">È possibile utilizzare `Operator` solo in una classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7f382-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="7f382-148">Ciò significa che il *contesto della dichiarazione* per un operatore non può essere un file di origine, lo spazio dei nomi, modulo, interfaccia, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="7f382-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="7f382-149">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="7f382-150">Tutti gli operatori devono essere `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="7f382-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="7f382-151">Non è possibile specificare `ByRef`, `Optional`, o `ParamArray` per degli operandi.</span><span class="sxs-lookup"><span data-stu-id="7f382-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="7f382-152">È possibile utilizzare il simbolo dell'operatore o l'identificatore per contenere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="7f382-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="7f382-153">È necessario utilizzare il `Return` istruzione e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="7f382-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="7f382-154">Un numero qualsiasi di `Return` istruzioni possono trovarsi in qualsiasi punto della procedura.</span><span class="sxs-lookup"><span data-stu-id="7f382-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="7f382-155">Definendo un operatore in questo modo viene chiamato *l'overload degli operatori*, se si utilizza il `Overloads` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="7f382-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="7f382-156">La tabella seguente elenca gli operatori che è possibile definire.</span><span class="sxs-lookup"><span data-stu-id="7f382-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="7f382-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="7f382-157">Type</span></span>|<span data-ttu-id="7f382-158">Operatori</span><span class="sxs-lookup"><span data-stu-id="7f382-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="7f382-159">Unario</span><span class="sxs-lookup"><span data-stu-id="7f382-159">Unary</span></span>|<span data-ttu-id="7f382-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="7f382-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="7f382-161">Binario</span><span class="sxs-lookup"><span data-stu-id="7f382-161">Binary</span></span>|<span data-ttu-id="7f382-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="7f382-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="7f382-163">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="7f382-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="7f382-164">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7f382-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="7f382-165">Quando si definisce `CType`, è necessario specificare `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="7f382-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="7f382-166">Coppie corrispondenti</span><span class="sxs-lookup"><span data-stu-id="7f382-166">Matched Pairs</span></span>  
 <span data-ttu-id="7f382-167">È necessario definire alcuni operatori come coppie associate.</span><span class="sxs-lookup"><span data-stu-id="7f382-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="7f382-168">Se si definisce un operatore di tale coppia, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="7f382-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="7f382-169">Le coppie sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f382-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="7f382-170">`=` e `<>`</span><span class="sxs-lookup"><span data-stu-id="7f382-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="7f382-171">`>` e `<`</span><span class="sxs-lookup"><span data-stu-id="7f382-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="7f382-172">`>=` e `<=`</span><span class="sxs-lookup"><span data-stu-id="7f382-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="7f382-173">`IsTrue` e `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="7f382-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="7f382-174">Restrizioni di tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7f382-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="7f382-175">Ogni operatore definito deve coinvolgere classe o della struttura nella quale è definita.</span><span class="sxs-lookup"><span data-stu-id="7f382-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="7f382-176">Ciò significa che la classe o struttura deve apparire come tipo di dati delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f382-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="7f382-177">L'operando dell'operatore unario.</span><span class="sxs-lookup"><span data-stu-id="7f382-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="7f382-178">Almeno uno degli operandi di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="7f382-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="7f382-179">L'operando o il tipo restituito di un operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="7f382-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="7f382-180">Alcuni operatori hanno dati aggiuntivi digitare restrizioni, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7f382-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="7f382-181">Se si definisce la `IsTrue` e `IsFalse` operatori, questi devono restituire entrambi il `Boolean` tipo.</span><span class="sxs-lookup"><span data-stu-id="7f382-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="7f382-182">Se si definisce la `<<` e `>>` operatori, questi devono entrambi specificare il `Integer` tipo per il `operandtype` di `operand2`.</span><span class="sxs-lookup"><span data-stu-id="7f382-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="7f382-183">Il tipo restituito non deve corrispondere al tipo degli operandi.</span><span class="sxs-lookup"><span data-stu-id="7f382-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="7f382-184">Ad esempio, un operatore di confronto, ad esempio `=` o `<>` può restituire `Boolean` anche se nessuno dei due operandi sono `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7f382-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="7f382-185">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="7f382-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="7f382-186">Il `And`, `Or`, `Not`, e `Xor` operatori in Visual Basic possono eseguire operazioni logiche o bit per bit.</span><span class="sxs-lookup"><span data-stu-id="7f382-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="7f382-187">Tuttavia, se si definisce uno di questi operatori in una classe o struttura, è possibile definire solo l'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="7f382-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="7f382-188">Non è possibile definire il `AndAlso` operatore direttamente con un `Operator` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7f382-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="7f382-189">Tuttavia, è possibile utilizzare `AndAlso` se si sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f382-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="7f382-190">È stato definito `And` sugli stessi tipi di operando da utilizzare per `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="7f382-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="7f382-191">La definizione di `And` restituisce lo stesso tipo della classe o struttura in cui sono definite.</span><span class="sxs-lookup"><span data-stu-id="7f382-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="7f382-192">È stato definito il `IsFalse` operatore nella classe o struttura in cui sono definite `And`.</span><span class="sxs-lookup"><span data-stu-id="7f382-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="7f382-193">Analogamente, è possibile utilizzare `OrElse` se sono stati definiti `Or` negli stessi operandi sono definite con il tipo restituito della classe o struttura e si `IsTrue` nella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7f382-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="7f382-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="7f382-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="7f382-195">Oggetto *conversione di ampliamento* ha sempre esito positivo in fase di esecuzione, mentre un *conversione di restrizione* può non riuscire in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f382-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="7f382-196">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="7f382-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="7f382-197">Se si dichiara una routine di conversione da `Widening`, il codice della routine non deve generare gli eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="7f382-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="7f382-198">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="7f382-198">This means the following:</span></span>  
  
-   <span data-ttu-id="7f382-199">Deve sempre restituire un valore valido di tipo `type`.</span><span class="sxs-lookup"><span data-stu-id="7f382-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="7f382-200">È necessario gestire tutte le eccezioni e altre condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="7f382-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="7f382-201">L'applicazione deve gestire qualsiasi errore restituito da qualsiasi routine che chiama.</span><span class="sxs-lookup"><span data-stu-id="7f382-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="7f382-202">Se vi è una possibilità che una routine di conversione potrebbe avere esito negativo o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="7f382-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f382-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f382-203">Example</span></span>  
 <span data-ttu-id="7f382-204">Nell'esempio di codice viene illustrato come utilizzare il `Operator` istruzione per definire la struttura di una struttura che include routine di operatore per il `And`, `Or`, `IsFalse`, e `IsTrue` operatori.</span><span class="sxs-lookup"><span data-stu-id="7f382-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="7f382-205">`And`e `Or` accettano due operandi di tipo `abc` e il tipo restituito `abc`.</span><span class="sxs-lookup"><span data-stu-id="7f382-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="7f382-206">`IsFalse`e `IsTrue` ognuna delle quali accetta un singolo operando di tipo `abc` e restituire `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7f382-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="7f382-207">Queste definizioni consentono al codice chiamante di usare `And`, `AndAlso`, `Or`, e `OrElse` con gli operandi di tipo `abc`.</span><span class="sxs-lookup"><span data-stu-id="7f382-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7f382-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f382-208">See Also</span></span>  
 [<span data-ttu-id="7f382-209">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="7f382-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="7f382-210">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="7f382-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="7f382-211">Widening</span><span class="sxs-lookup"><span data-stu-id="7f382-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="7f382-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="7f382-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="7f382-213">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="7f382-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="7f382-214">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="7f382-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="7f382-215">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="7f382-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="7f382-216">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="7f382-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="7f382-217">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="7f382-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="7f382-218">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="7f382-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
