---
title: Istruzione end (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: a2c211e5ebfd00a639644243312cbe25f71f4cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593706"
---
# <a name="end-statement"></a><span data-ttu-id="aac61-102">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="aac61-102">End Statement</span></span>
<span data-ttu-id="aac61-103">Termina l'esecuzione immediatamente.</span><span class="sxs-lookup"><span data-stu-id="aac61-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aac61-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="aac61-105">Note</span><span class="sxs-lookup"><span data-stu-id="aac61-105">Remarks</span></span>  
 <span data-ttu-id="aac61-106">È possibile inserire il `End` istruzione in un punto qualsiasi in una procedura per forzare l'intera applicazione per arrestare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aac61-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="aac61-107">`End` Chiude tutti i file aperti con un `Open` istruzione e Cancella tutte le variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aac61-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="aac61-108">L'applicazione viene chiusa non appena non sono presenti altri programmi che contiene riferimenti a oggetti e non del relativo codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aac61-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aac61-109">Il `End` istruzione interrompe l'esecuzione di codice in modo anomalo e non richiama i `Dispose` o `Finalize` metodo o qualsiasi altro codice di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aac61-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="aac61-110">Riferimenti a oggetti attivati da altri programmi vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="aac61-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="aac61-111">Se un' `End` viene rilevata l'istruzione all'interno di un `Try` oppure `Catch` blocco di controllo non viene passato al corrispondente `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="aac61-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="aac61-112">Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o cancellare le variabili di qualsiasi tipo, a meno che non si è verificato in un file eseguibile compilato (.exe).</span><span class="sxs-lookup"><span data-stu-id="aac61-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="aac61-113">Poiché `End` termina l'applicazione senza tenere conto di tutte le risorse che potrebbero essere aperte, è consigliabile provare a chiudere correttamente l'applicazione prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="aac61-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="aac61-114">Ad esempio, se l'applicazione presenta i form aperti, è necessario chiuderli prima che venga raggiunta la `End` istruzione.</span><span class="sxs-lookup"><span data-stu-id="aac61-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="aac61-115">È consigliabile usare `End` sporadicamente e solo quando è necessario arrestare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="aac61-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="aac61-116">Le modalità usuali per interrompere una routine ([istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) e [Esci da istruzione](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo la routine, ma anche offrire l'opportunità di chiudere correttamente il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="aac61-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="aac61-117">Un'applicazione console, ad esempio, può semplicemente `Return` dal `Main` procedure.</span><span class="sxs-lookup"><span data-stu-id="aac61-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aac61-118">Il `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo il <xref:System.Environment> classe il <xref:System> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="aac61-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="aac61-119"><xref:System.Environment.Exit%2A> è necessario disporre `UnmanagedCode` l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="aac61-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="aac61-120">In caso contrario, un <xref:System.Security.SecurityException> errore si verifica.</span><span class="sxs-lookup"><span data-stu-id="aac61-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="aac61-121">Quando è seguito da una parola chiave aggiuntiva, [finali \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delinea la fine della definizione di procedura appropriata o il blocco.</span><span class="sxs-lookup"><span data-stu-id="aac61-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="aac61-122">Ad esempio, `End Function` termina la definizione di un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="aac61-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aac61-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="aac61-123">Example</span></span>  
 <span data-ttu-id="aac61-124">L'esempio seguente usa il `End` istruzione per terminare l'esecuzione di codice se l'utente lo richiede.</span><span class="sxs-lookup"><span data-stu-id="aac61-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="aac61-125">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="aac61-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="aac61-126">Questa istruzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="aac61-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac61-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aac61-127">See also</span></span>
- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="aac61-128">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="aac61-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="aac61-129">Fine \<parola chiave > istruzione</span><span class="sxs-lookup"><span data-stu-id="aac61-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
