---
title: Elenco parametri
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404317"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="065c8-102">Elenco dei parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="065c8-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="065c8-103">Specifica i parametri che una routine prevede quando viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="065c8-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="065c8-104">Più parametri sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="065c8-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="065c8-105">Di seguito è riportata la sintassi per un parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="065c8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="065c8-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="065c8-107">Parti</span><span class="sxs-lookup"><span data-stu-id="065c8-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="065c8-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="065c8-108">Optional.</span></span> <span data-ttu-id="065c8-109">Elenco degli attributi che si applicano a questo parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="065c8-110">È necessario racchiudere l' [elenco degli attributi](attribute-list.md) tra parentesi angolari (" `<` " e " `>` ").</span><span class="sxs-lookup"><span data-stu-id="065c8-110">You must enclose the [Attribute List](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="065c8-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="065c8-111">Optional.</span></span> <span data-ttu-id="065c8-112">Specifica che questo parametro non è obbligatorio quando viene chiamata la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="065c8-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="065c8-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="065c8-113">Optional.</span></span> <span data-ttu-id="065c8-114">Specifica che la routine non può sostituire o riassegnare l'elemento della variabile sottostante all'argomento corrispondente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="065c8-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="065c8-115">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="065c8-115">Optional.</span></span> <span data-ttu-id="065c8-116">Specifica che la stored procedure può modificare l'elemento della variabile sottostante nel codice chiamante nello stesso modo in cui è possibile il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="065c8-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="065c8-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="065c8-117">Optional.</span></span> <span data-ttu-id="065c8-118">Specifica che l'ultimo parametro nell'elenco di parametri è una matrice facoltativa di elementi del tipo di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="065c8-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="065c8-119">Ciò consente al codice chiamante di passare un numero arbitrario di argomenti alla procedura.</span><span class="sxs-lookup"><span data-stu-id="065c8-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="065c8-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="065c8-120">Required.</span></span> <span data-ttu-id="065c8-121">Nome della variabile locale che rappresenta il parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="065c8-122">Obbligatorio se `Option Strict` è `On` .</span><span class="sxs-lookup"><span data-stu-id="065c8-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="065c8-123">Tipo di dati della variabile locale che rappresenta il parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="065c8-124">Obbligatorio per i `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="065c8-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="065c8-125">Qualsiasi costante o espressione costante che restituisce il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="065c8-126">Se il tipo è `Object` o una classe, un'interfaccia, una matrice o una struttura, il valore predefinito può essere solo `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="065c8-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="065c8-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="065c8-127">Remarks</span></span>

<span data-ttu-id="065c8-128">I parametri sono racchiusi tra parentesi e separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="065c8-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="065c8-129">Un parametro può essere dichiarato con qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="065c8-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="065c8-130">Se non si specifica `parametertype` , il valore predefinito è `Object` .</span><span class="sxs-lookup"><span data-stu-id="065c8-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="065c8-131">Quando il codice chiamante chiama la stored procedure, passa un *argomento* a ogni parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="065c8-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="065c8-132">Per ulteriori informazioni, vedere [differenze tra parametri e argomenti](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-132">For more information, see [Differences Between Parameters and Arguments](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="065c8-133">L'argomento che il codice chiamante passa a ogni parametro è un puntatore a un elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="065c8-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="065c8-134">Se questo elemento non è *variabile* (costante, valore letterale, enumerazione o espressione), non è possibile modificare il codice.</span><span class="sxs-lookup"><span data-stu-id="065c8-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="065c8-135">Se è un elemento *variabile* (una variabile dichiarata, un campo, una proprietà, un elemento di matrice o un elemento della struttura), il codice chiamante può modificarlo.</span><span class="sxs-lookup"><span data-stu-id="065c8-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="065c8-136">Per ulteriori informazioni, vedere [differenze tra argomenti modificabili e non modificabili](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="065c8-137">Se viene passato un elemento variabile `ByRef` , può essere modificato anche dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="065c8-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="065c8-138">Per ulteriori informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="065c8-139">Regole</span><span class="sxs-lookup"><span data-stu-id="065c8-139">Rules</span></span>

- <span data-ttu-id="065c8-140">**Parentesi.**</span><span class="sxs-lookup"><span data-stu-id="065c8-140">**Parentheses.**</span></span> <span data-ttu-id="065c8-141">Se si specifica un elenco di parametri, è necessario racchiuderlo tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="065c8-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="065c8-142">Se non sono presenti parametri, è comunque possibile usare le parentesi che racchiudono un elenco vuoto.</span><span class="sxs-lookup"><span data-stu-id="065c8-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="065c8-143">Ciò migliora la leggibilità del codice chiarendo che l'elemento è una routine.</span><span class="sxs-lookup"><span data-stu-id="065c8-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="065c8-144">**Parametri facoltativi.**</span><span class="sxs-lookup"><span data-stu-id="065c8-144">**Optional Parameters.**</span></span> <span data-ttu-id="065c8-145">Se si usa il `Optional` modificatore su un parametro, anche tutti i parametri successivi nell'elenco devono essere facoltativi e devono essere dichiarati usando il `Optional` modificatore.</span><span class="sxs-lookup"><span data-stu-id="065c8-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="065c8-146">Ogni dichiarazione di parametro facoltativa deve fornire la `defaultvalue` clausola.</span><span class="sxs-lookup"><span data-stu-id="065c8-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="065c8-147">Per ulteriori informazioni, vedere [parametri facoltativi](../../programming-guide/language-features/procedures/optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-147">For more information, see [Optional Parameters](../../programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="065c8-148">**Matrici di parametri.**</span><span class="sxs-lookup"><span data-stu-id="065c8-148">**Parameter Arrays.**</span></span> <span data-ttu-id="065c8-149">È necessario specificare `ByVal` per un `ParamArray` parametro.</span><span class="sxs-lookup"><span data-stu-id="065c8-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="065c8-150">Non è possibile utilizzare sia `Optional` che `ParamArray` nello stesso elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="065c8-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="065c8-151">Per altre informazioni, vedere [matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-151">For more information, see [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="065c8-152">**Passaggio del meccanismo.**</span><span class="sxs-lookup"><span data-stu-id="065c8-152">**Passing Mechanism.**</span></span> <span data-ttu-id="065c8-153">Il meccanismo predefinito per ogni argomento è `ByVal` , il che significa che la procedura non può modificare l'elemento della variabile sottostante.</span><span class="sxs-lookup"><span data-stu-id="065c8-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="065c8-154">Tuttavia, se l'elemento è un tipo di riferimento, la procedura può modificare il contenuto o i membri dell'oggetto sottostante, anche se non è in grado di sostituire o riassegnare l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="065c8-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="065c8-155">**Nomi dei parametri.**</span><span class="sxs-lookup"><span data-stu-id="065c8-155">**Parameter Names.**</span></span> <span data-ttu-id="065c8-156">Se il tipo di dati del parametro è una matrice, seguire `parametername` immediatamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="065c8-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="065c8-157">Per ulteriori informazioni sui nomi dei parametri, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="065c8-157">For more information on parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="065c8-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="065c8-158">Example</span></span>

<span data-ttu-id="065c8-159">Nell'esempio seguente viene illustrata una `Function` procedura che definisce due parametri.</span><span class="sxs-lookup"><span data-stu-id="065c8-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="065c8-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="065c8-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="065c8-161">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="065c8-161">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="065c8-162">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="065c8-162">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="065c8-163">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="065c8-163">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="065c8-164">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="065c8-164">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="065c8-165">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="065c8-165">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="065c8-166">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="065c8-166">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="065c8-167">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="065c8-167">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
