---
title: Istruzione End
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b692409f2895f5e9b713c57fc35ff2def40bce75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="end-statement"></a><span data-ttu-id="22a34-102">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="22a34-102">End Statement</span></span>
<span data-ttu-id="22a34-103">Termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22a34-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22a34-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="22a34-105">Note</span><span class="sxs-lookup"><span data-stu-id="22a34-105">Remarks</span></span>  
 <span data-ttu-id="22a34-106">È possibile inserire il `End` istruzione in un punto qualsiasi in una procedura per imporre l'intera applicazione a interrompere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22a34-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="22a34-107">`End`Chiude qualsiasi file aperto con un `Open` istruzione e Cancella tutte le variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22a34-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="22a34-108">La chiusura dell'applicazione, non appena non sono presenti altri programmi che contiene riferimenti a oggetti e nessuna parte del codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22a34-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22a34-109">Il `End` istruzione interruzione dell'esecuzione di codice e non viene richiamato il `Dispose` o `Finalize` metodo, o qualsiasi altro codice di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="22a34-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="22a34-110">I riferimenti agli oggetti attivati da altri programmi vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="22a34-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="22a34-111">Se un `End` viene rilevata un'istruzione all'interno di un `Try` o `Catch` blocco di controllo, non viene passato al corrispondente `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="22a34-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="22a34-112">Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o deselezionare tutte le variabili, a meno che non viene rilevata in un file eseguibile compilato (.exe).</span><span class="sxs-lookup"><span data-stu-id="22a34-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="22a34-113">Poiché `End` termina l'applicazione senza tenere conto di tutte le risorse che possono essere aperte, è consigliabile provare a chiudere correttamente prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="22a34-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="22a34-114">Ad esempio, se l'applicazione presenta i form aperti, è necessario chiuderli prima che venga raggiunta la `End` istruzione.</span><span class="sxs-lookup"><span data-stu-id="22a34-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="22a34-115">È consigliabile utilizzare `End` sporadicamente e solo quando è necessario arrestare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="22a34-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="22a34-116">Le modalità usuali per interrompere una routine ([istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo la routine, ma offre inoltre il codice chiamante la possibilità di chiudere correttamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22a34-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="22a34-117">Un'applicazione console, ad esempio, può semplicemente `Return` dal `Main` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="22a34-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22a34-118">Il `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo il <xref:System.Environment> classe il <xref:System> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="22a34-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="22a34-119"><xref:System.Environment.Exit%2A>è necessario disporre `UnmanagedCode` autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="22a34-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="22a34-120">In caso contrario, un <xref:System.Security.SecurityException> si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="22a34-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="22a34-121">Quando è seguito da una parola chiave aggiuntiva, [fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delinea la fine della definizione di procedura appropriata o il blocco.</span><span class="sxs-lookup"><span data-stu-id="22a34-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="22a34-122">Ad esempio, `End Function` termina la definizione di un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="22a34-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22a34-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="22a34-123">Example</span></span>  
 <span data-ttu-id="22a34-124">L'esempio seguente usa il `End` istruzione per terminare l'esecuzione di codice se richiesto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="22a34-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="22a34-125">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="22a34-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="22a34-126">Questa istruzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="22a34-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a34-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a34-127">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [<span data-ttu-id="22a34-128">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="22a34-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="22a34-129">Fine \<parola chiave > istruzione</span><span class="sxs-lookup"><span data-stu-id="22a34-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
