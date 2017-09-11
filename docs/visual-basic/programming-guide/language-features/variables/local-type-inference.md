---
title: Inferenza del tipo locale (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
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
ms.openlocfilehash: af8de63eb00db917771600f0fca8f200ec451afe
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="b192e-102">Inferenza del tipo di variabile locale (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b192e-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="b192e-103">Il compilatore Visual Basic utilizza *inferenza del tipo* per determinare i tipi di dati delle variabili locali dichiarate senza un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="b192e-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="b192e-104">Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="b192e-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="b192e-105">In questo modo è possibile dichiarare variabili senza dichiarare in modo esplicito un tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b192e-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="b192e-106">Come risultato le dichiarazioni, entrambi `num1` e `num2` sono fortemente tipizzati come integer.</span><span class="sxs-lookup"><span data-stu-id="b192e-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="b192e-107">[!code-vb[VbVbalrTypeInference n.&1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-107">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b192e-108">Se non si desidera `num2` nell'esempio precedente sia tipizzato come un `Integer`, è possibile specificare un altro tipo utilizzando una dichiarazione come `Dim num3 As Object = 3` o `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="b192e-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  
  
 <span data-ttu-id="b192e-109">Inferenza del tipo locale si applica a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="b192e-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="b192e-110">E non può essere utilizzato per dichiarare le variabili a livello di modulo (all'interno di una classe, struttura, modulo o interfaccia ma non all'interno di una routine o blocco).</span><span class="sxs-lookup"><span data-stu-id="b192e-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="b192e-111">Se `num2` nell'esempio precedente fosse un campo di una classe anziché una variabile locale in una procedura, la dichiarazione genererebbe un errore con `Option Strict` e classificherebbe `num2` come un `Object` con `Option Strict` off.</span><span class="sxs-lookup"><span data-stu-id="b192e-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="b192e-112">Analogamente, l'inferenza del tipo locale non si applica a variabili a livello di routine dichiarate come `Static`.</span><span class="sxs-lookup"><span data-stu-id="b192e-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="b192e-113">Inferenza del tipo e. L'associazione tardiva</span><span class="sxs-lookup"><span data-stu-id="b192e-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="b192e-114">Codice che utilizza l'inferenza del tipo è simile al codice che si basa sull'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="b192e-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="b192e-115">Tuttavia, l'inferenza del tipo tipizzare fortemente la variabile anziché lasciarla come `Object`.</span><span class="sxs-lookup"><span data-stu-id="b192e-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="b192e-116">Il compilatore utilizza l'inizializzatore di variabile per determinare il tipo della variabile in fase di compilazione per produrre codice con associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="b192e-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="b192e-117">Nell'esempio precedente, `num2`, come `num1`, tipizzato come un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b192e-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="b192e-118">Il comportamento delle variabili con associazione anticipata differisce da quello di variabili ad associazione tardiva, per cui il tipo è noto solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b192e-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="b192e-119">Sapere in anticipo il tipo consente al compilatore di identificare i problemi prima dell'esecuzione, in modo preciso della memoria ed eseguire altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b192e-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="b192e-120">Associazione anticipata consente inoltre l'ambiente di sviluppo integrato (IDE) di IntelliSense consentono di ottenere informazioni sui membri di un oggetto di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b192e-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="b192e-121">È preferibile per le prestazioni anche l'associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="b192e-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="b192e-122">In questo modo tutti i dati archiviati in una variabile ad associazione tardiva devono essere incluso come tipo `Object`, e l'accesso ai membri del tipo in fase di esecuzione rende più lento il programma.</span><span class="sxs-lookup"><span data-stu-id="b192e-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b192e-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="b192e-123">Examples</span></span>  
 <span data-ttu-id="b192e-124">L'inferenza del tipo si verifica quando una variabile locale viene dichiarata senza una `As` clausola ed è stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="b192e-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="b192e-125">Il compilatore utilizza il tipo di valore iniziale assegnato come il tipo della variabile.</span><span class="sxs-lookup"><span data-stu-id="b192e-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="b192e-126">Ad esempio, ognuna delle righe di codice seguente dichiara una variabile di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b192e-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 <span data-ttu-id="b192e-127">[!code-vb[VbVbalrTypeInference n.&2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-127">[!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span></span>  
  
 <span data-ttu-id="b192e-128">Il codice seguente illustra due modalità equivalenti per creare una matrice di interi.</span><span class="sxs-lookup"><span data-stu-id="b192e-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 <span data-ttu-id="b192e-129">[!code-vb[VbVbalrTypeInference n.&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-129">[!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span></span>  
  
 <span data-ttu-id="b192e-130">È consigliabile usare l'inferenza del tipo per determinare il tipo di una variabile di controllo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="b192e-130">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="b192e-131">Nel codice seguente, il compilatore deduce che `number` è un `Integer` poiché `someNumbers2` dell'esempio precedente è una matrice di interi.</span><span class="sxs-lookup"><span data-stu-id="b192e-131">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 <span data-ttu-id="b192e-132">[!code-vb[VbVbalrTypeInference n.&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-132">[!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span></span>  
  
 <span data-ttu-id="b192e-133">Inferenza del tipo locale può essere utilizzato `Using` istruzioni per stabilire il tipo del nome della risorsa, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b192e-133">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="b192e-134">[!code-vb[VbVbalrTypeInference&#7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-134">[!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span></span>  
  
 <span data-ttu-id="b192e-135">Il tipo di una variabile può essere dedotte anche dai valori restituiti delle funzioni, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b192e-135">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="b192e-136">Entrambi `pList1` e `pList2` sono costituiti da matrici di processi perché `Process.GetProcesses` restituisce una matrice di processi.</span><span class="sxs-lookup"><span data-stu-id="b192e-136">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 <span data-ttu-id="b192e-137">[!code-vb[VbVbalrTypeInference n.&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b192e-137">[!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span></span>  
  
## <a name="option-infer"></a><span data-ttu-id="b192e-138">Option Infer</span><span class="sxs-lookup"><span data-stu-id="b192e-138">Option Infer</span></span>  
 <span data-ttu-id="b192e-139">`Option Infer`Consente di specificare se l'inferenza del tipo locale è consentito in un determinato file.</span><span class="sxs-lookup"><span data-stu-id="b192e-139">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="b192e-140">Per consentire o bloccare l'opzione, digitare una delle seguenti istruzioni all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="b192e-140">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="b192e-141">Se non si specifica un valore per `Option Infer` nel codice, il valore predefinito del compilatore è `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="b192e-141">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="b192e-142">Per i progetti aggiornati da [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] o precedenti, il valore predefinito del compilatore è `Option Infer Off`.</span><span class="sxs-lookup"><span data-stu-id="b192e-142">For projects upgraded from [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="b192e-143">Se il valore impostato per `Option Infer` in un file è in conflitto con il valore impostato nell'IDE o sulla riga di comando, il valore nel file ha precedenza.</span><span class="sxs-lookup"><span data-stu-id="b192e-143">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="b192e-144">Per ulteriori informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) e [pagina Compila, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b192e-144">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="b192e-145">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="b192e-145">Restrictions</span></span>  
 <span data-ttu-id="b192e-146">L'inferenza del tipo può essere utilizzato solo per variabili locali statiche. non può essere usato per determinare il tipo di classe campi, proprietà o funzioni.</span><span class="sxs-lookup"><span data-stu-id="b192e-146">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b192e-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b192e-147">See Also</span></span>  
 <span data-ttu-id="b192e-148">[Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-148">[Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="b192e-149"> [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-149"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="b192e-150"> [Per ogni corso... Next (istruzione)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-150"> [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="b192e-151"> [For... Next (istruzione)](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-151"> [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="b192e-152"> [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-152"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="b192e-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="b192e-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="b192e-154"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="b192e-154"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
