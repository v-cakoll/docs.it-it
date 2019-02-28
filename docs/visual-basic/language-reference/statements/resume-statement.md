---
title: Riprendere l'istruzione (Visual Basic)
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
ms.openlocfilehash: fcb50a9c7e36bab046be25d7f82f91cfe0f9be8e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966918"
---
# <a name="resume-statement"></a><span data-ttu-id="b0171-102">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="b0171-102">Resume Statement</span></span>
<span data-ttu-id="b0171-103">Riprende l'esecuzione dopo aver completata una routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b0171-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="b0171-104">Si consiglia di usare Gestione strutturata delle eccezioni nel codice quando possibile, anziché utilizzare la gestione delle eccezioni non strutturati e la `On Error` e `Resume` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b0171-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="b0171-105">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b0171-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0171-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0171-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b0171-107">Parti</span><span class="sxs-lookup"><span data-stu-id="b0171-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="b0171-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0171-108">Required.</span></span> <span data-ttu-id="b0171-109">Se si è verificato l'errore nella stessa routine come il gestore degli errori, viene ripresa l'esecuzione con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="b0171-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="b0171-110">Se si è verificato l'errore in una routine chiamata, l'esecuzione riprende in corrispondenza dell'istruzione che ha richiamato la routine di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b0171-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="b0171-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0171-111">Optional.</span></span> <span data-ttu-id="b0171-112">Se si è verificato l'errore nella stessa routine come il gestore degli errori, viene ripresa l'esecuzione con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="b0171-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="b0171-113">Se si è verificato l'errore in una routine chiamata, viene ripresa l'esecuzione con l'istruzione immediatamente successiva all'istruzione che ha richiamato la routine di gestione degli errori (o `On Error Resume Next` istruzione).</span><span class="sxs-lookup"><span data-stu-id="b0171-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="b0171-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0171-114">Optional.</span></span> <span data-ttu-id="b0171-115">Riprende l'esecuzione alla riga specificata in richiesti `line` argomento.</span><span class="sxs-lookup"><span data-stu-id="b0171-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="b0171-116">Il `line` argomento è un'etichetta o un numero di riga e deve trovarsi nella stessa routine del gestore errori.</span><span class="sxs-lookup"><span data-stu-id="b0171-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0171-117">Note</span><span class="sxs-lookup"><span data-stu-id="b0171-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0171-118">È consigliabile usare Gestione strutturata delle eccezioni nel codice quando possibile, anziché utilizzare la gestione delle eccezioni non strutturati e la `On Error` e `Resume` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b0171-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="b0171-119">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b0171-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="b0171-120">Se si usa un `Resume` si verifica un errore di istruzione in un contesto diverso da una routine di gestione degli errori,.</span><span class="sxs-lookup"><span data-stu-id="b0171-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="b0171-121">Il `Resume` istruzione non può essere usata in tutte le procedure che contiene un `Try...Catch...Finally` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b0171-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0171-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0171-122">Example</span></span>  
 <span data-ttu-id="b0171-123">Questo esempio viene usato il `Resume` istruzione per terminare una routine di gestione degli errori e riprendere l'esecuzione con l'istruzione che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="b0171-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="b0171-124">Numero di errore 55 viene generato per illustrare l'utilizzo del `Resume` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b0171-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="b0171-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0171-125">Requirements</span></span>  
 <span data-ttu-id="b0171-126">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="b0171-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="b0171-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="b0171-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0171-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0171-128">See also</span></span>
- [<span data-ttu-id="b0171-129">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="b0171-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="b0171-130">Istruzione Error</span><span class="sxs-lookup"><span data-stu-id="b0171-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="b0171-131">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="b0171-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
