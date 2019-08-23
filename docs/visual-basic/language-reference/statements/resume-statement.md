---
title: Istruzione Resume (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 884bdaa0c19508b5a6bf6377568a53acc6880518
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957684"
---
# <a name="resume-statement"></a><span data-ttu-id="ae097-102">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="ae097-102">Resume Statement</span></span>
<span data-ttu-id="ae097-103">Riprende l'esecuzione al termine di una routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ae097-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="ae097-104">Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata `Resume` e le `On Error` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="ae097-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ae097-105">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae097-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae097-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae097-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ae097-107">Parti</span><span class="sxs-lookup"><span data-stu-id="ae097-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="ae097-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="ae097-108">Required.</span></span> <span data-ttu-id="ae097-109">Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="ae097-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="ae097-110">Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende in corrispondenza dell'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ae097-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="ae097-111">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ae097-111">Optional.</span></span> <span data-ttu-id="ae097-112">Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="ae097-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="ae097-113">Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di `On Error Resume Next` gestione degli errori (o istruzione).</span><span class="sxs-lookup"><span data-stu-id="ae097-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="ae097-114">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ae097-114">Optional.</span></span> <span data-ttu-id="ae097-115">L'esecuzione riprende in corrispondenza della riga specificata nell'argomento `line` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ae097-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="ae097-116">L' `line` argomento è un'etichetta di riga o un numero di riga e deve essere nella stessa procedura del gestore degli errori.</span><span class="sxs-lookup"><span data-stu-id="ae097-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae097-117">Note</span><span class="sxs-lookup"><span data-stu-id="ae097-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae097-118">Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata `Resume` e le `On Error` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="ae097-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ae097-119">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae097-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="ae097-120">Se si utilizza un' `Resume` istruzione in un punto qualsiasi di una routine di gestione degli errori, si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="ae097-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="ae097-121">L' `Resume` istruzione non può essere utilizzata in nessuna routine che contiene `Try...Catch...Finally` un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ae097-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae097-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae097-122">Example</span></span>  
 <span data-ttu-id="ae097-123">In questo esempio viene `Resume` utilizzata l'istruzione per terminare la gestione degli errori in una stored procedure e quindi riprendere l'esecuzione con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="ae097-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="ae097-124">Viene generato l'errore numero 55 per illustrare l' `Resume` uso dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ae097-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="ae097-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae097-125">Requirements</span></span>  
 <span data-ttu-id="ae097-126">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="ae097-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="ae097-127">**Assembly** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="ae097-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae097-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae097-128">See also</span></span>

- [<span data-ttu-id="ae097-129">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="ae097-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="ae097-130">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="ae097-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="ae097-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="ae097-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
