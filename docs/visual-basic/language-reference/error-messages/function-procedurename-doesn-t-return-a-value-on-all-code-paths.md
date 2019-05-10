---
title: La funzione '<procedurename>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 5564f95048f6b44a48229c7e5be9331839803439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662108"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="4dabc-102">Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="4dabc-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="4dabc-103">Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi del codice.</span><span class="sxs-lookup"><span data-stu-id="4dabc-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="4dabc-104">Probabilmente manca un'istruzione 'Return'.</span><span class="sxs-lookup"><span data-stu-id="4dabc-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="4dabc-105">Oggetto `Function` procedure dispone di almeno un possibile percorso all'interno del codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="4dabc-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="4dabc-106">È possibile restituire un valore da un `Function` procedure in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dabc-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="4dabc-107">Includere il valore in una [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4dabc-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="4dabc-108">Assegnare il valore per il `Function` procedure assegnare un nome e quindi eseguire un `Exit Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4dabc-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="4dabc-109">Assegnare il valore per il `Function` procedure assegnare un nome e quindi eseguire il `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4dabc-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="4dabc-110">Se il controllo passa al `Exit Function` o `End Function` e non è stato assegnato alcun valore per il nome della routine, la procedura restituisce il valore predefinito del tipo di dati restituito.</span><span class="sxs-lookup"><span data-stu-id="4dabc-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="4dabc-111">Per altre informazioni, vedere "Comportamento di" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4dabc-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="4dabc-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="4dabc-112">By default, this message is a warning.</span></span> <span data-ttu-id="4dabc-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4dabc-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4dabc-114">**ID errore:** BC42105</span><span class="sxs-lookup"><span data-stu-id="4dabc-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4dabc-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4dabc-115">To correct this error</span></span>  
  
- <span data-ttu-id="4dabc-116">Controllare la logica del flusso di controllo e assicurarsi che si assegna un valore prima di ogni istruzione che provoca un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4dabc-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="4dabc-117">È più semplice garantire che ogni restituito dalla routine restituisce un valore se si usano sempre il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4dabc-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="4dabc-118">Se si esegue questa operazione, l'ultima istruzione che precede `End Function` deve essere un `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4dabc-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dabc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dabc-119">See also</span></span>

- [<span data-ttu-id="4dabc-120">Routine Function</span><span class="sxs-lookup"><span data-stu-id="4dabc-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="4dabc-121">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="4dabc-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4dabc-122">Pagina Compilazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dabc-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
