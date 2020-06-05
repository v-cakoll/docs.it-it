---
title: La funzione '<procedurename>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: edb2195f4e83c2315aa929936aff8af88ca8556c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374135"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="f2e6f-102">La funzione '\<procedurename>' non restituisce un valore in tutti i percorsi del codice</span><span class="sxs-lookup"><span data-stu-id="f2e6f-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="f2e6f-103">La funzione ' \<procedurename> ' non restituisce un valore in tutti i percorsi del codice.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="f2e6f-104">Manca un'istruzione ' Return '?</span><span class="sxs-lookup"><span data-stu-id="f2e6f-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="f2e6f-105">Una `Function` routine ha almeno un possibile percorso nel codice che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="f2e6f-106">È possibile restituire un valore da una `Function` routine in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2e6f-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="f2e6f-107">Includere il valore in un' [istruzione return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f2e6f-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="f2e6f-108">Assegnare il valore al `Function` nome della stored procedure, quindi eseguire un' `Exit Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="f2e6f-109">Assegnare il valore al `Function` nome della stored procedure, quindi eseguire l' `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="f2e6f-110">Se il controllo passa a `Exit Function` o `End Function` e non è stato assegnato alcun valore al nome della stored procedure, la stored procedure restituisce il valore predefinito del tipo di dati restituito.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="f2e6f-111">Per ulteriori informazioni, vedere "Behavior" nell' [istruzione Function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f2e6f-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="f2e6f-112">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-112">By default, this message is a warning.</span></span> <span data-ttu-id="f2e6f-113">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f2e6f-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f2e6f-114">**ID errore:** BC42105</span><span class="sxs-lookup"><span data-stu-id="f2e6f-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2e6f-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f2e6f-115">To correct this error</span></span>  
  
- <span data-ttu-id="f2e6f-116">Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="f2e6f-117">È più facile garantire che ogni ritorno dalla procedura restituisca un valore se si usa sempre l' `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="f2e6f-118">In tal caso, l'ultima istruzione prima `End Function` deve essere un' `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2e6f-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e6f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2e6f-119">See also</span></span>

- [<span data-ttu-id="f2e6f-120">Routine Function</span><span class="sxs-lookup"><span data-stu-id="f2e6f-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="f2e6f-121">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f2e6f-121">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="f2e6f-122">Compilazione (pagina), Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2e6f-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
