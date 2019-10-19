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
ms.openlocfilehash: 66dba1df125a08b8ae05519a0c66edb6da15ceaa
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583421"
---
# <a name="end-statement"></a><span data-ttu-id="90bda-102">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="90bda-102">End Statement</span></span>
<span data-ttu-id="90bda-103">Termina immediatamente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="90bda-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90bda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90bda-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="90bda-105">Note</span><span class="sxs-lookup"><span data-stu-id="90bda-105">Remarks</span></span>  
 <span data-ttu-id="90bda-106">È possibile inserire l'istruzione `End` in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="90bda-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="90bda-107">`End` chiude tutti i file aperti con un'istruzione `Open` e cancella tutte le variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90bda-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="90bda-108">L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="90bda-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90bda-109">L'istruzione `End` interrompe l'esecuzione del codice improvvisamente e non richiama il metodo `Dispose` o `Finalize` o qualsiasi altro codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="90bda-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="90bda-110">I riferimenti agli oggetti contenuti in altri programmi vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="90bda-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="90bda-111">Se viene rilevata un'istruzione `End` all'interno di un blocco `Try` o `Catch`, il controllo non passa al blocco `Finally` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="90bda-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="90bda-112">L'istruzione `Stop` sospende l'esecuzione, ma a differenza di `End` non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).</span><span class="sxs-lookup"><span data-stu-id="90bda-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="90bda-113">Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla.</span><span class="sxs-lookup"><span data-stu-id="90bda-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="90bda-114">Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l'istruzione `End`.</span><span class="sxs-lookup"><span data-stu-id="90bda-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="90bda-115">È consigliabile utilizzare `End` sporadicamente e solo quando è necessario arrestare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="90bda-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="90bda-116">I modi normali per terminare una procedura (istruzione[return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="90bda-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="90bda-117">Un'applicazione console, ad esempio, può semplicemente `Return` dalla procedura `Main`.</span><span class="sxs-lookup"><span data-stu-id="90bda-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="90bda-118">L'istruzione `End` chiama il metodo <xref:System.Environment.Exit%2A> della classe <xref:System.Environment> nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="90bda-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="90bda-119">per <xref:System.Environment.Exit%2A> è necessario disporre di `UnmanagedCode` autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="90bda-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="90bda-120">In caso contrario, si verifica un errore di <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="90bda-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="90bda-121">Quando seguito da una parola chiave aggiuntiva, [end \<keyword > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato.</span><span class="sxs-lookup"><span data-stu-id="90bda-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="90bda-122">Ad esempio, `End Function` termina la definizione di una routine di `Function`.</span><span class="sxs-lookup"><span data-stu-id="90bda-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90bda-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="90bda-123">Example</span></span>  
 <span data-ttu-id="90bda-124">Nell'esempio seguente viene utilizzata l'istruzione `End` per terminare l'esecuzione del codice se richiesto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="90bda-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="90bda-125">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="90bda-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="90bda-126">Questa istruzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="90bda-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bda-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90bda-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="90bda-128">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="90bda-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="90bda-129">Istruzione End \<keyword ></span><span class="sxs-lookup"><span data-stu-id="90bda-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
