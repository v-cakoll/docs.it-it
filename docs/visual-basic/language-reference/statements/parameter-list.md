---
title: Elenco di parametri (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cc56d90db9a732928773fa549cb1456d368e1dbe
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="b40f5-102">Elenco dei parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b40f5-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="b40f5-103">Specifica i parametri di che una procedura prevede quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="b40f5-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="b40f5-104">Più parametri sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b40f5-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="b40f5-105">Di seguito è la sintassi per un parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b40f5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b40f5-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b40f5-107">Parti</span><span class="sxs-lookup"><span data-stu-id="b40f5-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="b40f5-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-108">Optional.</span></span> <span data-ttu-id="b40f5-109">Elenco di attributi che si applicano a questo parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="b40f5-110">È necessario racchiudere il [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").</span><span class="sxs-lookup"><span data-stu-id="b40f5-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="b40f5-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-111">Optional.</span></span> <span data-ttu-id="b40f5-112">Specifica che questo parametro non è necessario quando viene chiamata la routine.</span><span class="sxs-lookup"><span data-stu-id="b40f5-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="b40f5-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-113">Optional.</span></span> <span data-ttu-id="b40f5-114">Specifica che la procedura non possa sostituire o riassegnare l'elemento variabile sottostante all'argomento corrispondente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="b40f5-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="b40f5-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-115">Optional.</span></span> <span data-ttu-id="b40f5-116">Specifica che la routine può modificare l'elemento variabile sottostante nel codice chiamante allo stesso modo che il codice.</span><span class="sxs-lookup"><span data-stu-id="b40f5-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="b40f5-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-117">Optional.</span></span> <span data-ttu-id="b40f5-118">Specifica che l'ultimo parametro nell'elenco dei parametri è una matrice facoltativa di elementi del tipo di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="b40f5-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="b40f5-119">In questo modo il codice chiamante di passare un numero arbitrario di argomenti per la procedura.</span><span class="sxs-lookup"><span data-stu-id="b40f5-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="b40f5-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b40f5-120">Required.</span></span> <span data-ttu-id="b40f5-121">Nome della variabile locale che rappresenta il parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="b40f5-122">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="b40f5-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b40f5-123">Tipo di dati della variabile locale che rappresenta il parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="b40f5-124">Necessario per `Optional` i parametri.</span><span class="sxs-lookup"><span data-stu-id="b40f5-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="b40f5-125">Qualsiasi espressione costante o una costante che restituisce il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="b40f5-126">Se il tipo è `Object`, o una classe, interfaccia, una matrice o una struttura, il valore predefinito può essere solo `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b40f5-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b40f5-127">Note</span><span class="sxs-lookup"><span data-stu-id="b40f5-127">Remarks</span></span>  
 <span data-ttu-id="b40f5-128">I parametri sono racchiusi tra parentesi e separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b40f5-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="b40f5-129">Un parametro può essere dichiarato con qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b40f5-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="b40f5-130">Se non si specifica `parametertype`, l'impostazione predefinita è `Object`.</span><span class="sxs-lookup"><span data-stu-id="b40f5-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="b40f5-131">Quando si chiama la procedura, il codice chiamante passa un *argomento* per ogni parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b40f5-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="b40f5-132">Per ulteriori informazioni, vedere [le differenze tra parametri e argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="b40f5-133">L'argomento che il codice chiamante passa a ogni parametro è un puntatore a un elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="b40f5-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="b40f5-134">Se questo elemento è *variabile* (una costante, valore letterale, enumerazione o espressione), è Impossibile per il codice per modificarlo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="b40f5-135">In questo caso un *variabile* elemento (una variabile dichiarata, campo, proprietà, matrice o elemento di struttura), il codice chiamante può modificarlo.</span><span class="sxs-lookup"><span data-stu-id="b40f5-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="b40f5-136">Per ulteriori informazioni, vedere [le differenze tra modificabile e non modificabili argomenti](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="b40f5-137">Se viene passato un elemento variabile `ByRef`, la routine può modificare anche.</span><span class="sxs-lookup"><span data-stu-id="b40f5-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="b40f5-138">Per ulteriori informazioni, vedere [le differenze tra il passaggio di un argomento per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b40f5-139">Regole</span><span class="sxs-lookup"><span data-stu-id="b40f5-139">Rules</span></span>  
  
-   <span data-ttu-id="b40f5-140">**Parentesi.**</span><span class="sxs-lookup"><span data-stu-id="b40f5-140">**Parentheses.**</span></span> <span data-ttu-id="b40f5-141">Se si specifica un elenco di parametri, è necessario racchiuderlo tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="b40f5-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="b40f5-142">Se non sono presenti parametri, è comunque possibile utilizzare parentesi che racchiudono un elenco vuoto.</span><span class="sxs-lookup"><span data-stu-id="b40f5-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="b40f5-143">Per migliorare la leggibilità del codice indicando che l'elemento è una procedura.</span><span class="sxs-lookup"><span data-stu-id="b40f5-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="b40f5-144">**Parametri facoltativi.**</span><span class="sxs-lookup"><span data-stu-id="b40f5-144">**Optional Parameters.**</span></span> <span data-ttu-id="b40f5-145">Se si utilizza il `Optional` modificatore su un parametro, tutti i parametri successivi nell'elenco deve inoltre essere facoltativi ed essere dichiarati utilizzando il `Optional` modificatore.</span><span class="sxs-lookup"><span data-stu-id="b40f5-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="b40f5-146">Ogni dichiarazione di parametro facoltativo è necessario fornire il `defaultvalue` clausola.</span><span class="sxs-lookup"><span data-stu-id="b40f5-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="b40f5-147">Per ulteriori informazioni, vedere [parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="b40f5-148">**Matrici di parametri.**</span><span class="sxs-lookup"><span data-stu-id="b40f5-148">**Parameter Arrays.**</span></span> <span data-ttu-id="b40f5-149">È necessario specificare `ByVal` per un `ParamArray` parametro.</span><span class="sxs-lookup"><span data-stu-id="b40f5-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="b40f5-150">È possibile utilizzare sia `Optional` e `ParamArray` nello stesso elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="b40f5-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="b40f5-151">Per ulteriori informazioni, vedere [matrici di parametro](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="b40f5-152">**Meccanismo di passaggio.**</span><span class="sxs-lookup"><span data-stu-id="b40f5-152">**Passing Mechanism.**</span></span> <span data-ttu-id="b40f5-153">Il meccanismo predefinito per ogni argomento è `ByVal`, ovvero la procedura non può modificare l'elemento variabile sottostante.</span><span class="sxs-lookup"><span data-stu-id="b40f5-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="b40f5-154">Tuttavia, se l'elemento è un tipo di riferimento, la routine può modificare il contenuto o i membri dell'oggetto sottostante, anche se è possibile sostituire o riassegnare l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="b40f5-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="b40f5-155">**Nomi dei parametri.**</span><span class="sxs-lookup"><span data-stu-id="b40f5-155">**Parameter Names.**</span></span> <span data-ttu-id="b40f5-156">Se il tipo di dati del parametro è una matrice, seguire `parametername` parentesi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b40f5-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="b40f5-157">Per ulteriori informazioni sui nomi dei parametri, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b40f5-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b40f5-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="b40f5-158">Example</span></span>  
 <span data-ttu-id="b40f5-159">Nell'esempio seguente un `Function` routine che definisce due parametri.</span><span class="sxs-lookup"><span data-stu-id="b40f5-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 <span data-ttu-id="b40f5-160">[!code-vb[VbVbalrStatements n.&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b40f5-160">[!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40f5-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b40f5-161">See Also</span></span>  
 <span data-ttu-id="b40f5-162"><xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="b40f5-162"><xref:System.Runtime.InteropServices.DllImportAttribute></span></span>   
<span data-ttu-id="b40f5-163"> [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-163"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="b40f5-164"> [Sub (istruzione)](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-164"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="b40f5-165"> [Declare (istruzione)](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-165"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="b40f5-166"> [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-166"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="b40f5-167"> [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-167"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="b40f5-168"> [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="b40f5-168"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="b40f5-169"> [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="b40f5-169"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>
