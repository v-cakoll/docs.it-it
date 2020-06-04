---
title: Operator Statement
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
ms.openlocfilehash: f9e6ffe5a49715592399321ab471d73826e05d8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404395"
---
# <a name="operator-statement"></a><span data-ttu-id="cd0c0-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="cd0c0-102">Operator Statement</span></span>

<span data-ttu-id="cd0c0-103">Dichiara il simbolo dell'operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd0c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd0c0-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="cd0c0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="cd0c0-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="cd0c0-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-106">Optional.</span></span> <span data-ttu-id="cd0c0-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-107">See [Attribute List](attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="cd0c0-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-108">Required.</span></span> <span data-ttu-id="cd0c0-109">Indica che questa routine dell'operatore dispone di accesso [pubblico](../modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-109">Indicates that this operator procedure has [Public](../modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="cd0c0-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-110">Optional.</span></span> <span data-ttu-id="cd0c0-111">Vedere [Overload](../modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-111">See [Overloads](../modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="cd0c0-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-112">Required.</span></span> <span data-ttu-id="cd0c0-113">Indica che questa routine dell'operatore è una procedura [condivisa](../modifiers/shared.md) .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-113">Indicates that this operator procedure is a [Shared](../modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="cd0c0-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-114">Optional.</span></span> <span data-ttu-id="cd0c0-115">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-115">See [Shadows](../modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="cd0c0-116">Obbligatorio per un operatore di conversione, a meno che non si specifichi `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="cd0c0-117">Indica che questa routine dell'operatore definisce una conversione verso un tipo di contenuto più [ampio](../modifiers/widening.md) .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-117">Indicates that this operator procedure defines a [Widening](../modifiers/widening.md) conversion.</span></span> <span data-ttu-id="cd0c0-118">Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="cd0c0-119">Obbligatorio per un operatore di conversione, a meno che non si specifichi `Widening` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="cd0c0-120">Indica che questa routine dell'operatore definisce una conversione verso un tipo di caratteri più [piccolo](../modifiers/narrowing.md) .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-120">Indicates that this operator procedure defines a [Narrowing](../modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="cd0c0-121">Vedere "conversioni verso un tipo di ampliamento e riduzione" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="cd0c0-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-122">Required.</span></span> <span data-ttu-id="cd0c0-123">Simbolo o identificatore dell'operatore definito da questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="cd0c0-124">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-124">Required.</span></span> <span data-ttu-id="cd0c0-125">Il nome e il tipo del singolo operando di un operatore unario (incluso un operatore di conversione) o l'operando sinistro di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="cd0c0-126">Obbligatorio per gli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-126">Required for binary operators.</span></span> <span data-ttu-id="cd0c0-127">Nome e tipo dell'operando di destra di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="cd0c0-128">`operand1`e `operand2` presentano la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="cd0c0-129">Parte</span><span class="sxs-lookup"><span data-stu-id="cd0c0-129">Part</span></span>|<span data-ttu-id="cd0c0-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd0c0-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="cd0c0-131">Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-131">Optional, but the passing mechanism must be [ByVal](../modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="cd0c0-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-132">Required.</span></span> <span data-ttu-id="cd0c0-133">Nome della variabile che rappresenta questo operando.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="cd0c0-134">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="cd0c0-135">Facoltativo a meno che non `Option Strict` sia `On` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="cd0c0-136">Tipo di dati dell'operando.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="cd0c0-137">Facoltativo a meno che non `Option Strict` sia `On` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="cd0c0-138">Tipo di dati del valore restituito dalla routine dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="cd0c0-139">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-139">Optional.</span></span> <span data-ttu-id="cd0c0-140">Blocco di istruzioni eseguite dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="cd0c0-141">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-141">Required.</span></span> <span data-ttu-id="cd0c0-142">Valore restituito dalla routine Operator al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="cd0c0-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-143">`End` `Operator`</span></span>  
<span data-ttu-id="cd0c0-144">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-144">Required.</span></span> <span data-ttu-id="cd0c0-145">Termina la definizione di questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd0c0-146">Commenti</span><span class="sxs-lookup"><span data-stu-id="cd0c0-146">Remarks</span></span>

<span data-ttu-id="cd0c0-147">È possibile utilizzare `Operator` solo in una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="cd0c0-148">Ciò significa che il *contesto di dichiarazione* per un operatore non può essere un file di origine, uno spazio dei nomi, un modulo, un'interfaccia, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="cd0c0-149">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-149">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="cd0c0-150">Tutti gli operatori devono essere `Public Shared` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="cd0c0-151">Non è possibile specificare `ByRef` , `Optional` o `ParamArray` per uno degli operandi.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="cd0c0-152">Non è possibile usare il simbolo dell'operatore o l'identificatore per mantenere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="cd0c0-153">È necessario utilizzare l' `Return` istruzione ed è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="cd0c0-154">Qualsiasi numero di `Return` istruzioni può comparire in qualsiasi punto della procedura.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="cd0c0-155">La definizione di un operatore in questo modo viene chiamata *Overload degli operatori*, indipendentemente dal fatto che si usi la `Overloads` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="cd0c0-156">La tabella seguente elenca gli operatori che è possibile definire.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="cd0c0-157">Type</span><span class="sxs-lookup"><span data-stu-id="cd0c0-157">Type</span></span>|<span data-ttu-id="cd0c0-158">Operatori</span><span class="sxs-lookup"><span data-stu-id="cd0c0-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="cd0c0-159">Unaria</span><span class="sxs-lookup"><span data-stu-id="cd0c0-159">Unary</span></span>|<span data-ttu-id="cd0c0-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="cd0c0-161">Binario</span><span class="sxs-lookup"><span data-stu-id="cd0c0-161">Binary</span></span>|<span data-ttu-id="cd0c0-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="cd0c0-163">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="cd0c0-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="cd0c0-164">Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="cd0c0-165">Quando si definisce `CType` , è necessario specificare `Widening` o `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="cd0c0-166">Coppie corrispondenti</span><span class="sxs-lookup"><span data-stu-id="cd0c0-166">Matched Pairs</span></span>

<span data-ttu-id="cd0c0-167">È necessario definire determinati operatori come coppie corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="cd0c0-168">Se si definisce uno degli operatori di tale coppia, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="cd0c0-169">Le coppie corrispondenti sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="cd0c0-170">`=` e `<>`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-170">`=` and `<>`</span></span>

- <span data-ttu-id="cd0c0-171">`>` e `<`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-171">`>` and `<`</span></span>

- <span data-ttu-id="cd0c0-172">`>=` e `<=`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-172">`>=` and `<=`</span></span>

- <span data-ttu-id="cd0c0-173">`IsTrue` e `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="cd0c0-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="cd0c0-174">Restrizioni relative ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="cd0c0-174">Data Type Restrictions</span></span>

<span data-ttu-id="cd0c0-175">Ogni operatore definito deve coinvolgere la classe o la struttura in cui viene definita.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="cd0c0-176">Ciò significa che la classe o la struttura deve essere visualizzata come tipo di dati degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="cd0c0-177">Operando di un operatore unario.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="cd0c0-178">Almeno uno degli operandi di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="cd0c0-179">L'operando o il tipo restituito di un operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="cd0c0-180">Alcuni operatori hanno restrizioni aggiuntive per i tipi di dati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="cd0c0-181">Se si definiscono gli `IsTrue` `IsFalse` operatori e, devono entrambi restituire il `Boolean` tipo.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="cd0c0-182">Se si definiscono gli `<<` `>>` operatori e, devono entrambi specificare il `Integer` tipo per l'oggetto `operandtype` di `operand2` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="cd0c0-183">Il tipo restituito non deve corrispondere al tipo di uno degli operandi.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="cd0c0-184">Un operatore di confronto, ad esempio, `=` `<>` può essere restituito `Boolean` anche se nessuno degli operandi è `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="cd0c0-185">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="cd0c0-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="cd0c0-186">Gli `And` `Or` operatori,, `Not` e `Xor` possono eseguire operazioni logiche o bit per bit in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="cd0c0-187">Tuttavia, se si definisce uno di questi operatori in una classe o una struttura, è possibile definire solo l'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="cd0c0-188">Non è possibile definire l' `AndAlso` operatore direttamente con un' `Operator` istruzione.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="cd0c0-189">Tuttavia, è possibile usare `AndAlso` se sono state soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="cd0c0-190">È stato definito lo `And` stesso tipo di operando che si desidera utilizzare per `AndAlso` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="cd0c0-191">La definizione di `And` restituisce lo stesso tipo della classe o della struttura in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="cd0c0-192">È stato definito l' `IsFalse` operatore sulla classe o sulla struttura in cui è stato definito `And` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="cd0c0-193">Analogamente, è possibile usare `OrElse` se è stato definito `Or` negli stessi operandi, con il tipo restituito della classe o della struttura, ed è stato definito `IsTrue` sulla classe o sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="cd0c0-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="cd0c0-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="cd0c0-195">Una *conversione* verso un tipo di caratteri più ampio viene sempre eseguita in fase di esecuzione, mentre una conversione verso un tipo di caratteri più *piccolo* può avere esito negativo</span><span class="sxs-lookup"><span data-stu-id="cd0c0-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="cd0c0-196">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c0-196">For more information, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="cd0c0-197">Se si dichiara una procedura di conversione `Widening` , il codice della procedura non deve generare errori.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="cd0c0-198">Ciò comporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd0c0-198">This means the following:</span></span>

- <span data-ttu-id="cd0c0-199">Deve sempre restituire un valore valido di tipo `type` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="cd0c0-200">Deve gestire tutte le possibili eccezioni e altre condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="cd0c0-201">Deve gestire eventuali ritorni degli errori da qualsiasi routine chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="cd0c0-202">Se è possibile che una procedura di conversione potrebbe non riuscire o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="cd0c0-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd0c0-203">Example</span></span>

<span data-ttu-id="cd0c0-204">Nell'esempio di codice seguente viene utilizzata l' `Operator` istruzione per definire il contorno di una struttura che include routine di operatore per gli `And` operatori, `Or` , `IsFalse` e `IsTrue` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="cd0c0-205">`And`e `Or` accettano due operandi di tipo `abc` e tipo restituito `abc` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="cd0c0-206">`IsFalse`e `IsTrue` accettano un solo operando di tipo `abc` e restituiscono `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="cd0c0-207">Queste definizioni consentono al codice chiamante di usare `And` , `AndAlso` , `Or` e `OrElse` con operandi di tipo `abc` .</span><span class="sxs-lookup"><span data-stu-id="cd0c0-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="cd0c0-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd0c0-208">See also</span></span>

- [<span data-ttu-id="cd0c0-209">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="cd0c0-209">IsFalse Operator</span></span>](../operators/isfalse-operator.md)
- [<span data-ttu-id="cd0c0-210">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="cd0c0-210">IsTrue Operator</span></span>](../operators/istrue-operator.md)
- [<span data-ttu-id="cd0c0-211">Widening</span><span class="sxs-lookup"><span data-stu-id="cd0c0-211">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="cd0c0-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="cd0c0-212">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="cd0c0-213">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="cd0c0-213">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="cd0c0-214">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="cd0c0-214">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="cd0c0-215">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="cd0c0-215">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="cd0c0-216">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="cd0c0-216">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="cd0c0-217">Procedura: chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="cd0c0-217">How to: Call an Operator Procedure</span></span>](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="cd0c0-218">Procedura: utilizzare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="cd0c0-218">How to: Use a Class that Defines Operators</span></span>](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
