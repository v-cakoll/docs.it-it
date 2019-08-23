---
title: Istruzione End (Visual Basic)
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
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944459"
---
# <a name="end-statement"></a><span data-ttu-id="9b1ed-102">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="9b1ed-102">End Statement</span></span>
<span data-ttu-id="9b1ed-103">Termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b1ed-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="9b1ed-105">Note</span><span class="sxs-lookup"><span data-stu-id="9b1ed-105">Remarks</span></span>  
 <span data-ttu-id="9b1ed-106">È possibile inserire l' `End` istruzione in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="9b1ed-107">`End`chiude tutti i file aperti con `Open` un'istruzione e cancella tutte le variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="9b1ed-108">L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b1ed-109">L' `End` istruzione arresta l'esecuzione del codice improvvisamente e non richiama il `Dispose` metodo o `Finalize` o qualsiasi altro codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="9b1ed-110">I riferimenti agli oggetti contenuti in altri programmi vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="9b1ed-111">Se viene `End` rilevata un'istruzione `Try` all' `Catch` interno di un blocco o, il controllo non `Finally` passa al blocco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="9b1ed-112">L' `Stop` istruzione sospende l'esecuzione, ma, a `End`differenza di, non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).</span><span class="sxs-lookup"><span data-stu-id="9b1ed-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="9b1ed-113">Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="9b1ed-114">Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l' `End` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="9b1ed-115">Si consiglia di `End` usare con parsimonia e solo quando è necessario arrestare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="9b1ed-116">I modi normali per terminare una procedura (istruzione[return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="9b1ed-117">Un'applicazione console, ad esempio, può semplicemente `Return` `Main` dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9b1ed-118">L' `End` istruzione chiama il <xref:System.Environment.Exit%2A> <xref:System.Environment> metodo<xref:System> della classe nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="9b1ed-119"><xref:System.Environment.Exit%2A>richiede l' `UnmanagedCode` autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="9b1ed-120">In caso contrario, si verificherà un <xref:System.Security.SecurityException> errore.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="9b1ed-121">Quando seguito da una parola chiave aggiuntiva, la [parola chiave End \<> istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="9b1ed-122">Ad esempio, `End Function` termina la definizione di una `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1ed-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b1ed-123">Example</span></span>  
 <span data-ttu-id="9b1ed-124">Nell'esempio seguente viene utilizzata `End` l'istruzione per terminare l'esecuzione del codice se richiesto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="9b1ed-125">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="9b1ed-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="9b1ed-126">Questa istruzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="9b1ed-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1ed-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b1ed-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="9b1ed-128">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="9b1ed-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="9b1ed-129">Istruzione \<end > parola chiave</span><span class="sxs-lookup"><span data-stu-id="9b1ed-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
