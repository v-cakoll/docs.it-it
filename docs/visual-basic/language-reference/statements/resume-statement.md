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
ms.openlocfilehash: 7b8c2e123c04ff9720d690507ee41a6b52f40c3f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583268"
---
# <a name="resume-statement"></a><span data-ttu-id="5aa72-102">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="5aa72-102">Resume Statement</span></span>
<span data-ttu-id="5aa72-103">Riprende l'esecuzione al termine di una routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="5aa72-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="5aa72-104">Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata e le istruzioni `On Error` e `Resume`.</span><span class="sxs-lookup"><span data-stu-id="5aa72-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="5aa72-105">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5aa72-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa72-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5aa72-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="5aa72-107">Parti</span><span class="sxs-lookup"><span data-stu-id="5aa72-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="5aa72-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa72-108">Required.</span></span> <span data-ttu-id="5aa72-109">Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5aa72-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="5aa72-110">Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende in corrispondenza dell'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="5aa72-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="5aa72-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa72-111">Optional.</span></span> <span data-ttu-id="5aa72-112">Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5aa72-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="5aa72-113">Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di gestione degli errori (o `On Error Resume Next` istruzione).</span><span class="sxs-lookup"><span data-stu-id="5aa72-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="5aa72-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aa72-114">Optional.</span></span> <span data-ttu-id="5aa72-115">L'esecuzione riprende in corrispondenza della riga specificata nell'argomento `line` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5aa72-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="5aa72-116">L'argomento `line` è un'etichetta di riga o un numero di riga e deve essere nella stessa procedura del gestore degli errori.</span><span class="sxs-lookup"><span data-stu-id="5aa72-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa72-117">Note</span><span class="sxs-lookup"><span data-stu-id="5aa72-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5aa72-118">È consigliabile utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata e le istruzioni `On Error` e `Resume`.</span><span class="sxs-lookup"><span data-stu-id="5aa72-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="5aa72-119">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5aa72-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="5aa72-120">Se si usa un'istruzione `Resume` in un punto diverso da una routine di gestione degli errori, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="5aa72-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="5aa72-121">Non è possibile usare l'istruzione `Resume` in nessuna routine che contiene un'istruzione `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="5aa72-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aa72-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="5aa72-122">Example</span></span>  
 <span data-ttu-id="5aa72-123">In questo esempio viene utilizzata l'istruzione `Resume` per terminare la gestione degli errori in una stored procedure e quindi riprendere l'esecuzione con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5aa72-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="5aa72-124">Viene generato l'errore numero 55 per illustrare l'uso dell'istruzione `Resume`.</span><span class="sxs-lookup"><span data-stu-id="5aa72-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="5aa72-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5aa72-125">Requirements</span></span>  
 <span data-ttu-id="5aa72-126">**Spazio dei nomi:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="5aa72-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="5aa72-127">**Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="5aa72-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa72-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5aa72-128">See also</span></span>

- [<span data-ttu-id="5aa72-129">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="5aa72-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="5aa72-130">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="5aa72-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="5aa72-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="5aa72-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
