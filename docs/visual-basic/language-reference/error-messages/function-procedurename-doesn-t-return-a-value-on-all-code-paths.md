---
title: Funzione &quot;&lt;NomeProcedura&gt;&quot; non restituisce un valore in tutti i percorsi di codice | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: cec047644bfbf82c5c3c206b23af6b0fc37f834d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="8a286-102">Funzione '&lt;NomeProcedura&gt;' non restituisce un valore in tutti i percorsi di codice</span><span class="sxs-lookup"><span data-stu-id="8a286-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="8a286-103">Funzione '\<NomeProcedura >' non restituisce un valore in tutti i percorsi di codice.</span><span class="sxs-lookup"><span data-stu-id="8a286-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="8a286-104">Manca un'istruzione 'Return'?</span><span class="sxs-lookup"><span data-stu-id="8a286-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="8a286-105">Oggetto `Function` procedura ha almeno un percorso possibile tramite il codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="8a286-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="8a286-106">È possibile restituire un valore da un `Function` procedura in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a286-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="8a286-107">Includere il valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8a286-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="8a286-108">Assegnare il valore per il `Function` procedure un nome e quindi eseguire un `Exit Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8a286-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="8a286-109">Assegnare il valore per il `Function` procedure un nome e quindi eseguire il `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8a286-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="8a286-110">Se il controllo passa al `Exit Function` o `End Function` e non è stato assegnato alcun valore per il nome della procedura, la procedura restituisce il valore predefinito del tipo di dati restituito.</span><span class="sxs-lookup"><span data-stu-id="8a286-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="8a286-111">Per ulteriori informazioni, vedere "Comportamento" in [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8a286-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="8a286-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="8a286-112">By default, this message is a warning.</span></span> <span data-ttu-id="8a286-113">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8a286-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8a286-114">**ID errore:** BC42105</span><span class="sxs-lookup"><span data-stu-id="8a286-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8a286-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8a286-115">To correct this error</span></span>  
  
-   <span data-ttu-id="8a286-116">Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che provoca una restituzione.</span><span class="sxs-lookup"><span data-stu-id="8a286-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="8a286-117">È più semplice garantire che ogni restituito dalla routine restituisce un valore se si utilizza sempre il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8a286-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="8a286-118">In questo caso, l'ultima istruzione prima `End Function` deve essere un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8a286-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a286-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a286-119">See Also</span></span>  
 <span data-ttu-id="8a286-120">[Routine di funzione](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8a286-120">[Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="8a286-121"> [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8a286-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="8a286-122"> [Pagina Compilazione, Creazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="8a286-122"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
