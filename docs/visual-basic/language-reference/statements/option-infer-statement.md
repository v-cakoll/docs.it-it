---
title: Option Infer (istruzione)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a><span data-ttu-id="e097b-102">Option Infer (istruzione)</span><span class="sxs-lookup"><span data-stu-id="e097b-102">Option Infer Statement</span></span>
<span data-ttu-id="e097b-103">Abilita l'uso dell'inferenza del tipo di variabile locale nelle variabili dichiaranti.</span><span class="sxs-lookup"><span data-stu-id="e097b-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e097b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e097b-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="e097b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e097b-105">Parts</span></span>  
  
|<span data-ttu-id="e097b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e097b-106">Term</span></span>|<span data-ttu-id="e097b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e097b-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="e097b-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e097b-108">Optional.</span></span> <span data-ttu-id="e097b-109">Abilita l'inferenza del tipo di variabile locale.</span><span class="sxs-lookup"><span data-stu-id="e097b-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="e097b-110">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e097b-110">Optional.</span></span> <span data-ttu-id="e097b-111">Disabilita l'inferenza del tipo di variabile locale.</span><span class="sxs-lookup"><span data-stu-id="e097b-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e097b-112">Note</span><span class="sxs-lookup"><span data-stu-id="e097b-112">Remarks</span></span>  
 <span data-ttu-id="e097b-113">Per impostare `Option Infer` in un file, digitare `Option Infer On` oppure `Option Infer Off` all'inizio del file, prima di qualsiasi altro codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e097b-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="e097b-114">Se il valore impostato per `Option Infer` in un file è in conflitto con il valore impostato nell'IDE o sulla riga di comando, il valore nel file ha precedenza.</span><span class="sxs-lookup"><span data-stu-id="e097b-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="e097b-115">Quando si imposta `Option Infer` su `On`, è possibile dichiarare variabili locali senza dichiarare in modo esplicito un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e097b-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="e097b-116">Tramite l'inferenza, il compilatore deriva il tipo di dati di una variabile dal tipo della relativa espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e097b-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="e097b-117">Nella figura seguente, l'istruzione `Option Infer` è abilitata.</span><span class="sxs-lookup"><span data-stu-id="e097b-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="e097b-118">La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come Integer in base all'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="e097b-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="e097b-119">![Visualizzazione IntelliSense della dichiarazione. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="e097b-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="e097b-120">IntelliSense quando Option Infer è attivato</span><span class="sxs-lookup"><span data-stu-id="e097b-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="e097b-121">Nella figura seguente, l'istruzione `Option Infer` è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e097b-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="e097b-122">La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come `Object` in base all'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="e097b-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="e097b-123">In questo esempio, il **Option Strict** è impostata su **Off** sul [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e097b-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="e097b-124">![Visualizzazione IntelliSense della dichiarazione. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="e097b-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="e097b-125">IntelliSense quando Option Infer è disabilitato</span><span class="sxs-lookup"><span data-stu-id="e097b-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e097b-126">Quando una variabile viene dichiarata come `Object`, il tipo di runtime può essere modificato mentre il programma è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e097b-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="e097b-127">esegue operazioni chiamate *boxing* e *unboxing* per la conversione tra un `Object` e un tipo di valore, che rende l'esecuzione più lenta.</span><span class="sxs-lookup"><span data-stu-id="e097b-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="e097b-128">Per informazioni sulle conversioni boxing e unboxing, vedere il [specifiche del linguaggio Visual Basic](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e097b-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="e097b-129">L'inferenza del tipo si applica a livello di routine e non si applica all'esterno di una routine in una classe, una struttura, un modulo o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e097b-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="e097b-130">Per ulteriori informazioni, vedere [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="e097b-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="e097b-131">Quando non è presente un'istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="e097b-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="e097b-132">Se il codice sorgente non contiene un `Option Infer` istruzione, il **Option Infer** impostazione di [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e097b-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="e097b-133">Se viene utilizzato il compilatore della riga di comando, il [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) viene utilizzata l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e097b-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="e097b-134">Per impostare Option Infer nell'IDE</span><span class="sxs-lookup"><span data-stu-id="e097b-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="e097b-135">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="e097b-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="e097b-136">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e097b-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e097b-137">Per ulteriori informazioni, vedere [NIB: gestione di proprietà del progetto con la finestra di progettazione del progetto](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="e097b-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="e097b-138">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="e097b-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="e097b-139">Impostare il valore di **Option infer** casella.</span><span class="sxs-lookup"><span data-stu-id="e097b-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="e097b-140">Quando si crea un nuovo progetto, il **Option Infer** impostazione il **compilare** scheda è impostata sul **Option Infer** impostazione nel **valore predefinito è VB** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e097b-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="e097b-141">Per accedere al **VB per impostazione predefinita** della finestra di dialogo di **strumenti** menu, fare clic su **opzioni**.</span><span class="sxs-lookup"><span data-stu-id="e097b-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="e097b-142">Nel **opzioni** finestra di dialogo espandere **progetti e soluzioni**, quindi fare clic su **impostazioni predefinite di Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="e097b-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="e097b-143">L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è `On`.</span><span class="sxs-lookup"><span data-stu-id="e097b-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="e097b-144">Per impostare Option Infer nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="e097b-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="e097b-145">Includere il [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) opzione del compilatore nella **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="e097b-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="e097b-146">Tipi di dati e valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="e097b-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="e097b-147">Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.</span><span class="sxs-lookup"><span data-stu-id="e097b-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="e097b-148">Tipo di dati specificato?</span><span class="sxs-lookup"><span data-stu-id="e097b-148">Data type specified?</span></span>|<span data-ttu-id="e097b-149">Inizializzatore specificato?</span><span class="sxs-lookup"><span data-stu-id="e097b-149">Initializer specified?</span></span>|<span data-ttu-id="e097b-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="e097b-150">Example</span></span>|<span data-ttu-id="e097b-151">Risultato</span><span class="sxs-lookup"><span data-stu-id="e097b-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="e097b-152">No</span><span class="sxs-lookup"><span data-stu-id="e097b-152">No</span></span>|<span data-ttu-id="e097b-153">No</span><span class="sxs-lookup"><span data-stu-id="e097b-153">No</span></span>|`Dim qty`|<span data-ttu-id="e097b-154">Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e097b-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="e097b-155">Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e097b-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="e097b-156">No</span><span class="sxs-lookup"><span data-stu-id="e097b-156">No</span></span>|<span data-ttu-id="e097b-157">Sì</span><span class="sxs-lookup"><span data-stu-id="e097b-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="e097b-158">Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="e097b-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="e097b-159">Vedere [inferenza](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="e097b-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="e097b-160">Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.</span><span class="sxs-lookup"><span data-stu-id="e097b-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="e097b-161">Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e097b-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="e097b-162">Sì</span><span class="sxs-lookup"><span data-stu-id="e097b-162">Yes</span></span>|<span data-ttu-id="e097b-163">No</span><span class="sxs-lookup"><span data-stu-id="e097b-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="e097b-164">La variabile viene inizializzata sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e097b-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="e097b-165">Per ulteriori informazioni, vedere [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e097b-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="e097b-166">Sì</span><span class="sxs-lookup"><span data-stu-id="e097b-166">Yes</span></span>|<span data-ttu-id="e097b-167">Sì</span><span class="sxs-lookup"><span data-stu-id="e097b-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="e097b-168">Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e097b-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e097b-169">Esempio</span><span class="sxs-lookup"><span data-stu-id="e097b-169">Example</span></span>  
 <span data-ttu-id="e097b-170">Gli esempi seguenti illustrano come l'istruzione `Option Infer` permette di usare inferenza del tipo di variabile locale.</span><span class="sxs-lookup"><span data-stu-id="e097b-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="e097b-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="e097b-171">Example</span></span>  
 <span data-ttu-id="e097b-172">L'esempio seguente dimostra che il tipo di runtime può differire quando una variabile viene identificata come `Object`.</span><span class="sxs-lookup"><span data-stu-id="e097b-172">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e097b-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e097b-173">See Also</span></span>  
 [<span data-ttu-id="e097b-174">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="e097b-174">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="e097b-175">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="e097b-175">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="e097b-176">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="e097b-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="e097b-177">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="e097b-177">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="e097b-178">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="e097b-178">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="e097b-179">Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="e097b-179">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="e097b-180">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="e097b-180">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="e097b-181">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="e097b-181">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
