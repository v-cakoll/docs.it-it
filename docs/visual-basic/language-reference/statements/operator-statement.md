---
title: Istruzione Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
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
ms.openlocfilehash: c4fae40992fa665121aff637ae427ef0cafbf547
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582389"
---
# <a name="operator-statement"></a><span data-ttu-id="5aa02-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="5aa02-102">Operator Statement</span></span>

<span data-ttu-id="5aa02-103">Dichiara il simbolo dell'operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="5aa02-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="5aa02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5aa02-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="5aa02-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5aa02-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="5aa02-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa02-106">Optional.</span></span> <span data-ttu-id="5aa02-107">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="5aa02-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-108">Required.</span></span> <span data-ttu-id="5aa02-109">Indica che questa routine dell'operatore dispone di accesso [pubblico](../../../visual-basic/language-reference/modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="5aa02-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="5aa02-110">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa02-110">Optional.</span></span> <span data-ttu-id="5aa02-111">Vedere [Overload](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="5aa02-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-112">Required.</span></span> <span data-ttu-id="5aa02-113">Indica che questa routine dell'operatore è una procedura [condivisa](../../../visual-basic/language-reference/modifiers/shared.md) .</span><span class="sxs-lookup"><span data-stu-id="5aa02-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="5aa02-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa02-114">Optional.</span></span> <span data-ttu-id="5aa02-115">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="5aa02-116">Obbligatorio per un operatore di conversione, a meno che non si specifichi `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="5aa02-117">Indica che questa routine dell'operatore definisce una conversione verso un tipo di contenuto più [ampio](../../../visual-basic/language-reference/modifiers/widening.md) .</span><span class="sxs-lookup"><span data-stu-id="5aa02-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="5aa02-118">Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="5aa02-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="5aa02-119">Obbligatorio per un operatore di conversione, a meno che non si specifichi `Widening`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="5aa02-120">Indica che questa routine dell'operatore definisce una conversione verso un tipo di caratteri più [piccolo](../../../visual-basic/language-reference/modifiers/narrowing.md) .</span><span class="sxs-lookup"><span data-stu-id="5aa02-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="5aa02-121">Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="5aa02-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="5aa02-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-122">Required.</span></span> <span data-ttu-id="5aa02-123">Simbolo o identificatore dell'operatore definito da questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="5aa02-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="5aa02-124">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-124">Required.</span></span> <span data-ttu-id="5aa02-125">Il nome e il tipo del singolo operando di un operatore unario (incluso un operatore di conversione) o l'operando sinistro di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="5aa02-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="5aa02-126">Obbligatorio per gli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="5aa02-126">Required for binary operators.</span></span> <span data-ttu-id="5aa02-127">Nome e tipo dell'operando di destra di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="5aa02-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="5aa02-128">`operand1` e `operand2` hanno la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa02-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="5aa02-129">Parte</span><span class="sxs-lookup"><span data-stu-id="5aa02-129">Part</span></span>|<span data-ttu-id="5aa02-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5aa02-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="5aa02-131">Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="5aa02-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-132">Required.</span></span> <span data-ttu-id="5aa02-133">Nome della variabile che rappresenta questo operando.</span><span class="sxs-lookup"><span data-stu-id="5aa02-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="5aa02-134">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="5aa02-135">Facoltativo, a meno che non sia `On` `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="5aa02-136">Tipo di dati dell'operando.</span><span class="sxs-lookup"><span data-stu-id="5aa02-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="5aa02-137">Facoltativo, a meno che non sia `On` `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="5aa02-138">Tipo di dati del valore restituito dalla routine dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="5aa02-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="5aa02-139">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa02-139">Optional.</span></span> <span data-ttu-id="5aa02-140">Blocco di istruzioni eseguite dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5aa02-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="5aa02-141">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-141">Required.</span></span> <span data-ttu-id="5aa02-142">Valore restituito dalla routine Operator al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="5aa02-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="5aa02-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="5aa02-143">`End` `Operator`</span></span>  
<span data-ttu-id="5aa02-144">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa02-144">Required.</span></span> <span data-ttu-id="5aa02-145">Termina la definizione di questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="5aa02-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="5aa02-146">Note</span><span class="sxs-lookup"><span data-stu-id="5aa02-146">Remarks</span></span>

<span data-ttu-id="5aa02-147">È possibile utilizzare `Operator` solo in una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="5aa02-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="5aa02-148">Ciò significa che il *contesto di dichiarazione* per un operatore non può essere un file di origine, uno spazio dei nomi, un modulo, un'interfaccia, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="5aa02-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="5aa02-149">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="5aa02-150">Tutti gli operatori devono essere `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="5aa02-151">Non è possibile specificare `ByRef`, `Optional` o `ParamArray` per uno degli operandi.</span><span class="sxs-lookup"><span data-stu-id="5aa02-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="5aa02-152">Non è possibile usare il simbolo dell'operatore o l'identificatore per mantenere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="5aa02-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="5aa02-153">È necessario utilizzare l'istruzione `Return` ed è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="5aa02-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="5aa02-154">Qualsiasi numero di istruzioni `Return` può comparire in qualsiasi punto della procedura.</span><span class="sxs-lookup"><span data-stu-id="5aa02-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="5aa02-155">La definizione di un operatore in questo modo viene chiamata *Overload degli operatori*, indipendentemente dal fatto che si usi la parola chiave `Overloads`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="5aa02-156">La tabella seguente elenca gli operatori che è possibile definire.</span><span class="sxs-lookup"><span data-stu-id="5aa02-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="5aa02-157">Digitare</span><span class="sxs-lookup"><span data-stu-id="5aa02-157">Type</span></span>|<span data-ttu-id="5aa02-158">Operatori</span><span class="sxs-lookup"><span data-stu-id="5aa02-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="5aa02-159">Unario</span><span class="sxs-lookup"><span data-stu-id="5aa02-159">Unary</span></span>|<span data-ttu-id="5aa02-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="5aa02-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="5aa02-161">Binario</span><span class="sxs-lookup"><span data-stu-id="5aa02-161">Binary</span></span>|<span data-ttu-id="5aa02-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="5aa02-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="5aa02-163">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="5aa02-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="5aa02-164">Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="5aa02-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="5aa02-165">Quando si definiscono `CType`, è necessario specificare `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="5aa02-166">Coppie corrispondenti</span><span class="sxs-lookup"><span data-stu-id="5aa02-166">Matched Pairs</span></span>

<span data-ttu-id="5aa02-167">È necessario definire determinati operatori come coppie corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5aa02-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="5aa02-168">Se si definisce uno degli operatori di tale coppia, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="5aa02-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="5aa02-169">Le coppie corrispondenti sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa02-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="5aa02-170">`=` e `<>`</span><span class="sxs-lookup"><span data-stu-id="5aa02-170">`=` and `<>`</span></span>

- <span data-ttu-id="5aa02-171">`>` e `<`</span><span class="sxs-lookup"><span data-stu-id="5aa02-171">`>` and `<`</span></span>

- <span data-ttu-id="5aa02-172">`>=` e `<=`</span><span class="sxs-lookup"><span data-stu-id="5aa02-172">`>=` and `<=`</span></span>

- <span data-ttu-id="5aa02-173">`IsTrue` e `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="5aa02-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="5aa02-174">Restrizioni relative ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="5aa02-174">Data Type Restrictions</span></span>

<span data-ttu-id="5aa02-175">Ogni operatore definito deve coinvolgere la classe o la struttura in cui viene definita.</span><span class="sxs-lookup"><span data-stu-id="5aa02-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="5aa02-176">Ciò significa che la classe o la struttura deve essere visualizzata come tipo di dati degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa02-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="5aa02-177">Operando di un operatore unario.</span><span class="sxs-lookup"><span data-stu-id="5aa02-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="5aa02-178">Almeno uno degli operandi di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="5aa02-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="5aa02-179">L'operando o il tipo restituito di un operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="5aa02-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="5aa02-180">Alcuni operatori hanno restrizioni aggiuntive per i tipi di dati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5aa02-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="5aa02-181">Se si definiscono gli operatori `IsTrue` e `IsFalse`, devono entrambi restituire il tipo di `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="5aa02-182">Se si definiscono gli operatori `<<` e `>>`, è necessario specificare il tipo di `Integer` per la `operandtype` di `operand2`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="5aa02-183">Il tipo restituito non deve corrispondere al tipo di uno degli operandi.</span><span class="sxs-lookup"><span data-stu-id="5aa02-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="5aa02-184">Un operatore di confronto, ad esempio `=` o `<>` può restituire `Boolean` anche se nessuno degli operandi è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="5aa02-185">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="5aa02-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="5aa02-186">Gli operatori `And`, `Or`, `Not` e `Xor` possono eseguire operazioni logiche o bit per bit in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5aa02-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="5aa02-187">Tuttavia, se si definisce uno di questi operatori in una classe o una struttura, è possibile definire solo l'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="5aa02-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="5aa02-188">Non è possibile definire l'operatore `AndAlso` direttamente con un'istruzione `Operator`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="5aa02-189">Tuttavia, è possibile usare `AndAlso` se sono state soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa02-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="5aa02-190">È stato definito `And` per gli stessi tipi di operando che si desidera utilizzare per `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="5aa02-191">La definizione di `And` restituisce lo stesso tipo della classe o della struttura in cui è stata definita.</span><span class="sxs-lookup"><span data-stu-id="5aa02-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="5aa02-192">È stato definito l'operatore `IsFalse` sulla classe o sulla struttura in cui è stato definito `And`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="5aa02-193">Analogamente, è possibile utilizzare `OrElse` se è stato definito `Or` sugli stessi operandi, con il tipo restituito della classe o della struttura, ed è stato definito `IsTrue` sulla classe o sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="5aa02-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="5aa02-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="5aa02-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="5aa02-195">Una *conversione* verso un tipo di caratteri più ampio viene sempre eseguita in fase di esecuzione, mentre una conversione verso un tipo di caratteri più *piccolo* può avere esito negativo</span><span class="sxs-lookup"><span data-stu-id="5aa02-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="5aa02-196">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="5aa02-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="5aa02-197">Se si dichiara una procedura di conversione da `Widening`, il codice della procedura non deve generare errori.</span><span class="sxs-lookup"><span data-stu-id="5aa02-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="5aa02-198">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="5aa02-198">This means the following:</span></span>

- <span data-ttu-id="5aa02-199">Deve restituire sempre un valore valido di tipo `type`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="5aa02-200">Deve gestire tutte le possibili eccezioni e altre condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="5aa02-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="5aa02-201">Deve gestire eventuali ritorni degli errori da qualsiasi routine chiamata.</span><span class="sxs-lookup"><span data-stu-id="5aa02-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="5aa02-202">Se è possibile che una procedura di conversione potrebbe non riuscire o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="5aa02-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="5aa02-203">Example</span></span>

<span data-ttu-id="5aa02-204">Nell'esempio di codice seguente viene utilizzata l'istruzione `Operator` per definire il contorno di una struttura che include routine di operatore per gli operatori `And`, `Or`, `IsFalse` e `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="5aa02-205">`And` e `Or` accettano due operandi di tipo `abc` e il tipo restituito `abc`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="5aa02-206">`IsFalse` e `IsTrue` accettano un solo operando di tipo `abc` e restituiscono `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="5aa02-207">Queste definizioni consentono al codice chiamante di utilizzare `And`, `AndAlso`, `Or` e `OrElse` con operandi di tipo `abc`.</span><span class="sxs-lookup"><span data-stu-id="5aa02-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="5aa02-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5aa02-208">See also</span></span>

- [<span data-ttu-id="5aa02-209">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="5aa02-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="5aa02-210">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="5aa02-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="5aa02-211">Widening</span><span class="sxs-lookup"><span data-stu-id="5aa02-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="5aa02-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="5aa02-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="5aa02-213">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="5aa02-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="5aa02-214">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="5aa02-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="5aa02-215">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="5aa02-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="5aa02-216">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="5aa02-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="5aa02-217">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="5aa02-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="5aa02-218">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="5aa02-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
