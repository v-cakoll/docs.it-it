---
title: 'Procedura: cambiare il valore di un argomento di routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 46cf9062d01e248b6e90882a923a48210780f7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388504"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="6fee1-102">Procedura: cambiare il valore di un argomento di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fee1-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="6fee1-103">Quando si chiama una routine, ogni argomento fornito corrisponde a uno dei parametri definiti nella stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6fee1-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="6fee1-104">In alcuni casi, il codice della procedura può modificare il valore sottostante un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="6fee1-105">In altri casi, la procedura può modificare solo la copia locale di un argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="6fee1-106">Quando si chiama la stored procedure, Visual Basic esegue una copia locale di ogni argomento passato [ByVal](../../../language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="6fee1-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="6fee1-107">Per ogni argomento passato [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic assegna al codice della procedura un riferimento diretto all'elemento di programmazione sottostante l'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-107">For each argument passed [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="6fee1-108">Se l'elemento sottostante nel codice chiamante è un elemento modificabile e l'argomento viene passato `ByRef` , il codice della procedura può utilizzare il riferimento diretto per modificare il valore dell'elemento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="6fee1-109">Modifica del valore sottostante</span><span class="sxs-lookup"><span data-stu-id="6fee1-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="6fee1-110">Per modificare il valore sottostante di un argomento di routine nel codice chiamante</span><span class="sxs-lookup"><span data-stu-id="6fee1-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="6fee1-111">Nella dichiarazione di routine specificare [ByRef](../../../language-reference/modifiers/byref.md) per il parametro corrispondente all'argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-111">In the procedure declaration, specify [ByRef](../../../language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="6fee1-112">Nel codice chiamante passare un elemento di programmazione modificabile come argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="6fee1-113">Nel codice chiamante, non racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="6fee1-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="6fee1-114">Nel codice della procedura usare il nome del parametro per assegnare un valore all'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="6fee1-115">Per una dimostrazione, vedere l'esempio più avanti.</span><span class="sxs-lookup"><span data-stu-id="6fee1-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="6fee1-116">Modifica di copie locali</span><span class="sxs-lookup"><span data-stu-id="6fee1-116">Changing Local Copies</span></span>  
 <span data-ttu-id="6fee1-117">Se l'elemento sottostante nel codice chiamante è un elemento non modificabile o se l'argomento viene passato `ByVal` , la procedura non può modificarne il valore nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="6fee1-118">Tuttavia, la procedura può modificare la copia locale di tale argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="6fee1-119">Per modificare la copia di un argomento di routine nel codice della procedura</span><span class="sxs-lookup"><span data-stu-id="6fee1-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="6fee1-120">Nella dichiarazione di routine specificare [ByVal](../../../language-reference/modifiers/byval.md) per il parametro corrispondente all'argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-120">In the procedure declaration, specify [ByVal](../../../language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="6fee1-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="6fee1-121">-or-</span></span>  
  
     <span data-ttu-id="6fee1-122">Nel codice chiamante racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="6fee1-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="6fee1-123">Questa operazione impone Visual Basic di passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef` .</span><span class="sxs-lookup"><span data-stu-id="6fee1-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="6fee1-124">Nel codice della procedura usare il nome del parametro per assegnare un valore alla copia locale dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="6fee1-125">Il valore sottostante nel codice chiamante non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6fee1-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fee1-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fee1-126">Example</span></span>  
 <span data-ttu-id="6fee1-127">Nell'esempio seguente vengono illustrate due procedure che accettano una variabile di matrice e operano sui relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="6fee1-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="6fee1-128">La `increase` procedura aggiunge semplicemente una a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="6fee1-129">La `replace` procedura assegna una nuova matrice al parametro `a()` e quindi ne aggiunge una a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="6fee1-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="6fee1-130">La prima `MsgBox` chiamata Visualizza "After increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="6fee1-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="6fee1-131">Poiché la matrice `n` è un tipo di riferimento, `replace` può modificare i relativi membri, anche se il meccanismo di passaggio è `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="6fee1-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="6fee1-132">La seconda `MsgBox` chiamata Visualizza "dopo Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="6fee1-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="6fee1-133">Poiché `n` viene passato `ByRef` , `replace` può modificare la variabile `n` nel codice chiamante e assegnarvi una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="6fee1-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="6fee1-134">Poiché `n` è un tipo di riferimento, `replace` può anche modificare i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="6fee1-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="6fee1-135">È possibile impedire la modifica della variabile nel codice chiamante da parte della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6fee1-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="6fee1-136">Vedere [procedura: proteggere un argomento di routine in base alle modifiche del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="6fee1-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="6fee1-137">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="6fee1-137">Compile the code</span></span>  
 <span data-ttu-id="6fee1-138">Quando si passa una variabile in base al riferimento, è necessario usare la `ByRef` parola chiave per specificare questo meccanismo.</span><span class="sxs-lookup"><span data-stu-id="6fee1-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="6fee1-139">Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="6fee1-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="6fee1-140">Tuttavia, è consigliabile includere la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con tutti i parametri dichiarati.</span><span class="sxs-lookup"><span data-stu-id="6fee1-140">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="6fee1-141">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="6fee1-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6fee1-142">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6fee1-142">.NET Framework Security</span></span>  
 <span data-ttu-id="6fee1-143">Esiste sempre un potenziale rischio nel consentire a una procedura di modificare il valore sottostante un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="6fee1-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="6fee1-144">Verificare che questo valore sia stato modificato e che sia stato preparato per verificarne la validità prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="6fee1-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fee1-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fee1-145">See also</span></span>

- [<span data-ttu-id="6fee1-146">Procedure</span><span class="sxs-lookup"><span data-stu-id="6fee1-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6fee1-147">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="6fee1-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6fee1-148">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="6fee1-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="6fee1-149">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="6fee1-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="6fee1-150">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="6fee1-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="6fee1-151">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="6fee1-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="6fee1-152">Procedura: impedire la modifica del valore di un argomento di una routine</span><span class="sxs-lookup"><span data-stu-id="6fee1-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="6fee1-153">Procedura: forzare il passaggio di un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="6fee1-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="6fee1-154">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="6fee1-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="6fee1-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="6fee1-155">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
