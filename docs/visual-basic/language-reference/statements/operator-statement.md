---
title: Istruzione operator (Visual Basic)
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
ms.openlocfilehash: 184970d33aae4af135153f9d6f6755770bdf84f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818592"
---
# <a name="operator-statement"></a><span data-ttu-id="0edac-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0edac-102">Operator Statement</span></span>
<span data-ttu-id="0edac-103">Dichiara il simbolo dell'operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0edac-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0edac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0edac-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="0edac-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0edac-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="0edac-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0edac-106">Optional.</span></span> <span data-ttu-id="0edac-107">Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="0edac-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-108">Required.</span></span> <span data-ttu-id="0edac-109">Indica che la routine di operatore abbia [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso.</span><span class="sxs-lookup"><span data-stu-id="0edac-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="0edac-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0edac-110">Optional.</span></span> <span data-ttu-id="0edac-111">Visualizzare [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="0edac-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-112">Required.</span></span> <span data-ttu-id="0edac-113">Indica che la routine di operatore è un [condiviso](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span><span class="sxs-lookup"><span data-stu-id="0edac-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="0edac-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0edac-114">Optional.</span></span> <span data-ttu-id="0edac-115">Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="0edac-116">Obbligatorio per un operatore di conversione solo se si specifica `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0edac-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="0edac-117">Indica che la routine di operatore definisce una [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversione.</span><span class="sxs-lookup"><span data-stu-id="0edac-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="0edac-118">In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".</span><span class="sxs-lookup"><span data-stu-id="0edac-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="0edac-119">Obbligatorio per un operatore di conversione solo se si specifica `Widening`.</span><span class="sxs-lookup"><span data-stu-id="0edac-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="0edac-120">Indica che la routine di operatore definisce una [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversione.</span><span class="sxs-lookup"><span data-stu-id="0edac-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="0edac-121">In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".</span><span class="sxs-lookup"><span data-stu-id="0edac-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="0edac-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-122">Required.</span></span> <span data-ttu-id="0edac-123">Il simbolo o l'identificatore dell'operatore che definisce questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="0edac-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="0edac-124">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-124">Required.</span></span> <span data-ttu-id="0edac-125">Il nome e tipo di operando sinistro dell'operatore binario o l'unico operando dell'operatore unario (incluso un operatore di conversione).</span><span class="sxs-lookup"><span data-stu-id="0edac-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="0edac-126">Obbligatorio per gli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="0edac-126">Required for binary operators.</span></span> <span data-ttu-id="0edac-127">Il nome e il tipo dell'operando destro dell'operatore binario.</span><span class="sxs-lookup"><span data-stu-id="0edac-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="0edac-128">`operand1` e `operand2` hanno la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0edac-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="0edac-129">Parte</span><span class="sxs-lookup"><span data-stu-id="0edac-129">Part</span></span>|<span data-ttu-id="0edac-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0edac-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="0edac-131">Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="0edac-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-132">Required.</span></span> <span data-ttu-id="0edac-133">Nome della variabile che rappresenta l'operando.</span><span class="sxs-lookup"><span data-stu-id="0edac-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="0edac-134">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="0edac-135">Facoltativo, a meno che `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="0edac-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0edac-136">Tipo di dati di operando.</span><span class="sxs-lookup"><span data-stu-id="0edac-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="0edac-137">Facoltativo, a meno che `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="0edac-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0edac-138">Restituisce il tipo di dati del valore della routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="0edac-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="0edac-139">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0edac-139">Optional.</span></span> <span data-ttu-id="0edac-140">Blocco di istruzioni che esegue la routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="0edac-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="0edac-141">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-141">Required.</span></span> <span data-ttu-id="0edac-142">Il valore che la routine di operatore restituisce al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="0edac-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="0edac-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="0edac-143">`End` `Operator`</span></span>  
 <span data-ttu-id="0edac-144">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0edac-144">Required.</span></span> <span data-ttu-id="0edac-145">Termina la definizione di questa routine di operatore.</span><span class="sxs-lookup"><span data-stu-id="0edac-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0edac-146">Note</span><span class="sxs-lookup"><span data-stu-id="0edac-146">Remarks</span></span>  
 <span data-ttu-id="0edac-147">È possibile usare `Operator` solo in una classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0edac-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="0edac-148">Ciò significa che il *contesto della dichiarazione* per un operatore non può essere un file di origine, lo spazio dei nomi, modulo, interfaccia, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="0edac-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="0edac-149">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="0edac-150">Tutti gli operatori devono essere `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="0edac-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="0edac-151">Non è possibile specificare `ByRef`, `Optional`, o `ParamArray` per degli operandi.</span><span class="sxs-lookup"><span data-stu-id="0edac-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="0edac-152">È possibile usare il simbolo dell'operatore o l'identificatore per contenere un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="0edac-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="0edac-153">È necessario usare il `Return` istruzione che è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="0edac-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="0edac-154">Un numero qualsiasi di `Return` istruzioni possono trovarsi in qualsiasi punto della procedura.</span><span class="sxs-lookup"><span data-stu-id="0edac-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="0edac-155">La definizione di un operatore in questo modo viene definita *overload degli operatori*, se si utilizza il `Overloads` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="0edac-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="0edac-156">La tabella seguente elenca gli operatori che è possibile definire.</span><span class="sxs-lookup"><span data-stu-id="0edac-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="0edac-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="0edac-157">Type</span></span>|<span data-ttu-id="0edac-158">Operatori</span><span class="sxs-lookup"><span data-stu-id="0edac-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="0edac-159">Unario</span><span class="sxs-lookup"><span data-stu-id="0edac-159">Unary</span></span>|<span data-ttu-id="0edac-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="0edac-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="0edac-161">Binario</span><span class="sxs-lookup"><span data-stu-id="0edac-161">Binary</span></span>|<span data-ttu-id="0edac-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="0edac-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="0edac-163">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="0edac-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="0edac-164">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0edac-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="0edac-165">Quando si definiscono `CType`, è necessario specificare `Widening` o `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0edac-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="0edac-166">Coppie appaiate</span><span class="sxs-lookup"><span data-stu-id="0edac-166">Matched Pairs</span></span>  
 <span data-ttu-id="0edac-167">È necessario definire determinati operatori come coppie associate.</span><span class="sxs-lookup"><span data-stu-id="0edac-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="0edac-168">Se si definisce l'operatore di una coppia di questo tipo, è necessario definire anche a altro.</span><span class="sxs-lookup"><span data-stu-id="0edac-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="0edac-169">Le coppie appaiate sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0edac-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="0edac-170">`=` e `<>`</span><span class="sxs-lookup"><span data-stu-id="0edac-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="0edac-171">`>` e `<`</span><span class="sxs-lookup"><span data-stu-id="0edac-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="0edac-172">`>=` e `<=`</span><span class="sxs-lookup"><span data-stu-id="0edac-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="0edac-173">`IsTrue` e `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="0edac-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="0edac-174">Restrizioni sul tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0edac-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="0edac-175">Ogni operatore definito deve comportare la classe o struttura in cui si definiscono.</span><span class="sxs-lookup"><span data-stu-id="0edac-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="0edac-176">Ciò significa che la classe o struttura deve essere visualizzato come il tipo di dati delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0edac-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="0edac-177">L'operando dell'operatore unario.</span><span class="sxs-lookup"><span data-stu-id="0edac-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="0edac-178">Almeno uno degli operandi di un operatore binario.</span><span class="sxs-lookup"><span data-stu-id="0edac-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="0edac-179">L'operando o il tipo restituito di un operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="0edac-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="0edac-180">Alcuni operatori hanno dati aggiuntivi digitare restrizioni, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0edac-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="0edac-181">Se si definiscono i `IsTrue` e `IsFalse` operatori, devono entrambe restituire il `Boolean` tipo.</span><span class="sxs-lookup"><span data-stu-id="0edac-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="0edac-182">Se si definisce la `<<` e `>>` operatori, devono entrambe specificare il `Integer` tipo per il `operandtype` di `operand2`.</span><span class="sxs-lookup"><span data-stu-id="0edac-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="0edac-183">Il tipo restituito non devono corrispondere al tipo degli operandi.</span><span class="sxs-lookup"><span data-stu-id="0edac-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="0edac-184">Ad esempio, un operatore di confronto, ad esempio `=` oppure `<>` può restituire `Boolean` anche se nessuno dei due operandi `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0edac-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="0edac-185">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="0edac-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="0edac-186">Il `And`, `Or`, `Not`, e `Xor` gli operatori possono eseguire operazioni logiche o bit per bit in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0edac-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="0edac-187">Tuttavia, se si definisce uno di questi operatori in una classe o struttura, è possibile definire solo l'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="0edac-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="0edac-188">Non è possibile definire le `AndAlso` operatore direttamente con un `Operator` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0edac-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="0edac-189">Tuttavia, è possibile usare `AndAlso` se si sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0edac-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="0edac-190">Sono stati definiti `And` sugli stessi tipi di operando da usare per `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="0edac-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="0edac-191">La definizione di `And` restituisce lo stesso tipo della classe o struttura in cui si è definita.</span><span class="sxs-lookup"><span data-stu-id="0edac-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="0edac-192">Sono stati definiti i `IsFalse` operatore nella classe o struttura in cui hanno definito `And`.</span><span class="sxs-lookup"><span data-stu-id="0edac-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="0edac-193">Analogamente, è possibile usare `OrElse` se è stata definita `Or` sugli operandi stesso, sono definiti con il tipo restituito della classe o struttura e si `IsTrue` nella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0edac-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="0edac-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0edac-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="0edac-195">Oggetto *conversione di ampliamento* avrà sempre esito positivo in fase di esecuzione, mentre un *conversione di narrowing* può non riuscire in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0edac-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="0edac-196">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="0edac-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="0edac-197">Se si dichiara una routine di conversione sia `Widening`, il codice di procedure non deve generare gli eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="0edac-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="0edac-198">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="0edac-198">This means the following:</span></span>  
  
-   <span data-ttu-id="0edac-199">App deve sempre restituire un valore valido di tipo `type`.</span><span class="sxs-lookup"><span data-stu-id="0edac-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="0edac-200">È necessario gestire tutte le eccezioni e altre condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="0edac-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="0edac-201">L'applicazione deve gestire qualsiasi errore restituito da qualsiasi routine che chiama.</span><span class="sxs-lookup"><span data-stu-id="0edac-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="0edac-202">Se vi è una possibilità che una routine di conversione potrebbe avere esito negativo o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="0edac-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0edac-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="0edac-203">Example</span></span>  
 <span data-ttu-id="0edac-204">Il codice seguente viene illustrato come utilizzare il `Operator` istruzione per definire la struttura di una struttura che include routine di operatore per il `And`, `Or`, `IsFalse`, e `IsTrue` operatori.</span><span class="sxs-lookup"><span data-stu-id="0edac-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="0edac-205">`And` e `Or` ognuno accettano due operandi di tipo `abc` e il tipo restituito `abc`.</span><span class="sxs-lookup"><span data-stu-id="0edac-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="0edac-206">`IsFalse` e `IsTrue` ognuna delle quali accetta un singolo operando di tipo `abc` e restituire `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0edac-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="0edac-207">Queste definizioni consentono al codice chiamante di usare `And`, `AndAlso`, `Or`, e `OrElse` con gli operandi di tipo `abc`.</span><span class="sxs-lookup"><span data-stu-id="0edac-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]  
  
## <a name="see-also"></a><span data-ttu-id="0edac-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0edac-208">See also</span></span>

- [<span data-ttu-id="0edac-209">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="0edac-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="0edac-210">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="0edac-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="0edac-211">Widening</span><span class="sxs-lookup"><span data-stu-id="0edac-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="0edac-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0edac-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="0edac-213">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="0edac-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="0edac-214">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0edac-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="0edac-215">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="0edac-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="0edac-216">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="0edac-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="0edac-217">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0edac-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="0edac-218">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="0edac-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
