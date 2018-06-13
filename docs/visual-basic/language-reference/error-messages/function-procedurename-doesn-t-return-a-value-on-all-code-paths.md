---
title: Funzione &#39; &lt;nomeroutine&gt; &#39; &#39;t restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 4c18c6229eb170e8a688aaa2734ae8fbfa081061
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589984"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="970bf-102">Funzione &#39; &lt;nomeroutine&gt; &#39; &#39;t restituisce un valore in tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="970bf-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="970bf-103">Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi di codice.</span><span class="sxs-lookup"><span data-stu-id="970bf-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="970bf-104">Probabilmente manca un'istruzione 'Return'.</span><span class="sxs-lookup"><span data-stu-id="970bf-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="970bf-105">Oggetto `Function` procedura contiene almeno un possibile percorso all'interno del codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="970bf-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="970bf-106">È possibile restituire un valore da un `Function` procedura in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="970bf-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="970bf-107">Includere il valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="970bf-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="970bf-108">Assegnare il valore per il `Function` procedure un nome e quindi eseguire un `Exit Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="970bf-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="970bf-109">Assegnare il valore per il `Function` procedure un nome e quindi eseguire il `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="970bf-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="970bf-110">Se il controllo passa al `Exit Function` o `End Function` e non, è stato assegnato alcun valore per il nome della stored procedure, la procedura restituisce il valore predefinito del tipo di dati restituito.</span><span class="sxs-lookup"><span data-stu-id="970bf-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="970bf-111">Per ulteriori informazioni, vedere "Comportamento" in [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="970bf-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="970bf-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="970bf-112">By default, this message is a warning.</span></span> <span data-ttu-id="970bf-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="970bf-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="970bf-114">**ID errore:** BC42105</span><span class="sxs-lookup"><span data-stu-id="970bf-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="970bf-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="970bf-115">To correct this error</span></span>  
  
-   <span data-ttu-id="970bf-116">Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.</span><span class="sxs-lookup"><span data-stu-id="970bf-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="970bf-117">È più semplice garantire che ogni restituito dalla routine restituisce un valore se si utilizza sempre il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="970bf-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="970bf-118">In questo caso, l'ultima istruzione prima `End Function` deve essere un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="970bf-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970bf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970bf-119">See Also</span></span>  
 [<span data-ttu-id="970bf-120">Routine Function</span><span class="sxs-lookup"><span data-stu-id="970bf-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="970bf-121">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="970bf-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="970bf-122">Pagina Compilazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="970bf-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
