---
title: Tipi di errore (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831566"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="f634d-102">Tipi di errore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f634d-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="f634d-103">In Visual Basic, gli errori (chiamato anche *eccezioni*) possono essere suddivise in tre categorie: errori di sintassi, gli errori di runtime ed errori per la logica.</span><span class="sxs-lookup"><span data-stu-id="f634d-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="f634d-104">Errori di sintassi</span><span class="sxs-lookup"><span data-stu-id="f634d-104">Syntax Errors</span></span>  
 <span data-ttu-id="f634d-105">*Errori di sintassi* sono quelli che vengono visualizzati durante la scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="f634d-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="f634d-106">Visual Basic controlla il codice durante la digitazione nel **Editor di codice** finestra e genera avvisi se si commette un errore, ad esempio ortografia errata di una parola o utilizzo improprio di un elemento di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="f634d-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="f634d-107">Errori di sintassi sono il tipo più comune degli errori.</span><span class="sxs-lookup"><span data-stu-id="f634d-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="f634d-108">È possibile correggerli con facilità nell'ambiente di codifica, non appena si verificano.</span><span class="sxs-lookup"><span data-stu-id="f634d-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f634d-109">Il `Option Explicit` istruzione è consente di evitare errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="f634d-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="f634d-110">Viene forzato, è possibile dichiarare in anticipo, tutte le variabili da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f634d-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="f634d-111">Pertanto, quando tali variabili vengono usate nel codice, gli errori di digitazione vengono rilevati immediatamente e possono essere corretti.</span><span class="sxs-lookup"><span data-stu-id="f634d-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="f634d-112">Errori di Run-Time</span><span class="sxs-lookup"><span data-stu-id="f634d-112">Run-Time Errors</span></span>  
 <span data-ttu-id="f634d-113">*Errori di run-time* sono quelli che vengono visualizzate solo dopo che viene compilato ed eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="f634d-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="f634d-114">Queste comprendono il codice che può sembrare corretto che non siano presenti errori di sintassi, ma che non verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="f634d-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="f634d-115">Ad esempio, si potrebbe scrivere correttamente una riga di codice per aprire un file.</span><span class="sxs-lookup"><span data-stu-id="f634d-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="f634d-116">Ma se il file è danneggiato, l'applicazione non è possibile eseguire il `Open` funzione e interrompe l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f634d-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="f634d-117">Per risolvere la maggior parte degli errori di runtime, riscrivere il codice non corretto, quindi ricompilare ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f634d-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="f634d-118">Errori di logica</span><span class="sxs-lookup"><span data-stu-id="f634d-118">Logic Errors</span></span>  
 <span data-ttu-id="f634d-119">*Errori di logica* vengono visualizzati una volta che l'applicazione è in uso.</span><span class="sxs-lookup"><span data-stu-id="f634d-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="f634d-120">Sono la maggior parte dei risultati indesiderati o imprevisti in risposta alle azioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f634d-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="f634d-121">Ad esempio, una chiave digitata incorrettamente o altri determini potrebbero causare l'applicazione per smettere di funzionare nei parametri previsti o completamente.</span><span class="sxs-lookup"><span data-stu-id="f634d-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="f634d-122">Gli errori per la logica sono in genere il tipo più difficile da risolvere, poiché non è sempre chiaro dove provengono.</span><span class="sxs-lookup"><span data-stu-id="f634d-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f634d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f634d-123">See also</span></span>

- [<span data-ttu-id="f634d-124">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="f634d-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- <span data-ttu-id="f634d-125">[Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)</span><span class="sxs-lookup"><span data-stu-id="f634d-125">[Debugger Basics](/visualstudio/debugger/debugger-basics)</span></span>
