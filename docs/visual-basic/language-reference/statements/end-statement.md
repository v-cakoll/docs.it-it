---
title: Istruzione End
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
ms.openlocfilehash: fe17a82662c4014069c77f2da76723a051ab9084
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404706"
---
# <a name="end-statement"></a><span data-ttu-id="14a6f-102">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="14a6f-102">End Statement</span></span>
<span data-ttu-id="14a6f-103">Termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14a6f-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="14a6f-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="14a6f-105">Remarks</span></span>  
 <span data-ttu-id="14a6f-106">È possibile inserire l' `End` istruzione in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="14a6f-107">`End`chiude tutti i file aperti con un' `Open` istruzione e cancella tutte le variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="14a6f-108">L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14a6f-109">L' `End` istruzione arresta l'esecuzione del codice improvvisamente e non richiama il `Dispose` metodo o o `Finalize` qualsiasi altro codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14a6f-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="14a6f-110">I riferimenti agli oggetti contenuti in altri programmi vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="14a6f-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="14a6f-111">Se `End` viene rilevata un'istruzione all'interno di un `Try` `Catch` blocco o, il controllo non passa al `Finally` blocco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="14a6f-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="14a6f-112">L' `Stop` istruzione sospende l'esecuzione, ma, a differenza di `End` , non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).</span><span class="sxs-lookup"><span data-stu-id="14a6f-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="14a6f-113">Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla.</span><span class="sxs-lookup"><span data-stu-id="14a6f-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="14a6f-114">Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l' `End` istruzione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="14a6f-115">Si consiglia `End` di usare con parsimonia e solo quando è necessario arrestare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="14a6f-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="14a6f-116">I modi normali per terminare una procedura (istruzione[return](return-statement.md) e [istruzione Exit](exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="14a6f-116">The normal ways to terminate a procedure ([Return Statement](return-statement.md) and [Exit Statement](exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="14a6f-117">Un'applicazione console, ad esempio, può semplicemente `Return` dalla `Main` procedura.</span><span class="sxs-lookup"><span data-stu-id="14a6f-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14a6f-118">L' `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo della <xref:System.Environment> classe nello <xref:System> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="14a6f-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="14a6f-119"><xref:System.Environment.Exit%2A>richiede l' `UnmanagedCode` autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="14a6f-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="14a6f-120">In caso contrario, <xref:System.Security.SecurityException> si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="14a6f-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="14a6f-121">Quando seguito da una parola chiave aggiuntiva, l' [ \<keyword> istruzione End](end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato.</span><span class="sxs-lookup"><span data-stu-id="14a6f-121">When followed by an additional keyword, [End \<keyword> Statement](end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="14a6f-122">Ad esempio, `End Function` termina la definizione di una `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="14a6f-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14a6f-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="14a6f-123">Example</span></span>  
 <span data-ttu-id="14a6f-124">Nell'esempio seguente viene utilizzata l' `End` istruzione per terminare l'esecuzione del codice se richiesto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="14a6f-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="14a6f-125">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="14a6f-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="14a6f-126">Questa istruzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="14a6f-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a6f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14a6f-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="14a6f-128">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="14a6f-128">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="14a6f-129">\<keyword>Istruzione End</span><span class="sxs-lookup"><span data-stu-id="14a6f-129">End \<keyword> Statement</span></span>](end-keyword-statement.md)
