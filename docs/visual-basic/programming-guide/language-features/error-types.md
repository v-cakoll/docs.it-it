---
title: Tipi di errore (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 51cf5820e79ff9467357619d4f5b067bc4168bfb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="error-types-visual-basic"></a><span data-ttu-id="86adf-102">Tipi di errore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86adf-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="86adf-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], gli errori (detto anche *eccezioni*) rientrano in una delle tre categorie: errori di sintassi, errori di run-time e gli errori logici.</span><span class="sxs-lookup"><span data-stu-id="86adf-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="86adf-104">Errori di sintassi</span><span class="sxs-lookup"><span data-stu-id="86adf-104">Syntax Errors</span></span>  
 <span data-ttu-id="86adf-105">*Errori di sintassi* vengono visualizzati durante la scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="86adf-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="86adf-106">Controlla il codice durante la digitazione nel **Editor di codice** finestra e genera avvisi se si commette un errore, ad esempio ortografia errata di parole o utilizzo improprio di un elemento di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="86adf-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="86adf-107">Errori di sintassi sono il tipo più comune di errori.</span><span class="sxs-lookup"><span data-stu-id="86adf-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="86adf-108">È possibile correggerli facilmente nell'ambiente di codifica, non appena si verificano.</span><span class="sxs-lookup"><span data-stu-id="86adf-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86adf-109">Il `Option Explicit` istruzione è un mezzo per evitare errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="86adf-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="86adf-110">Impone la dichiarazione in anticipo, tutte le variabili da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86adf-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="86adf-111">Pertanto, quando tali variabili vengono utilizzate nel codice, gli errori di digitazione vengono rilevati immediatamente e possono essere risolto.</span><span class="sxs-lookup"><span data-stu-id="86adf-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="86adf-112">Errori di Run-Time</span><span class="sxs-lookup"><span data-stu-id="86adf-112">Run-Time Errors</span></span>  
 <span data-ttu-id="86adf-113">*Errori di run-time* vengono visualizzati solo dopo la compilazione e l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="86adf-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="86adf-114">Queste comprendono il codice che sembra essere corretto in quanto non si verificano errori di sintassi, ma che non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="86adf-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="86adf-115">Ad esempio, è possibile scrivere correttamente una riga di codice per aprire un file.</span><span class="sxs-lookup"><span data-stu-id="86adf-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="86adf-116">Ma se il file è danneggiato, l'applicazione non può eseguire il `Open` funzione e si arresta.</span><span class="sxs-lookup"><span data-stu-id="86adf-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="86adf-117">Per risolvere la maggior parte degli errori di runtime, riscrivere il codice non corretto, quindi ricompilare ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="86adf-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="86adf-118">Errori di logica</span><span class="sxs-lookup"><span data-stu-id="86adf-118">Logic Errors</span></span>  
 <span data-ttu-id="86adf-119">*Errori di logica* vengono visualizzati una volta che l'applicazione è in uso.</span><span class="sxs-lookup"><span data-stu-id="86adf-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="86adf-120">Si tratta la maggior parte dei risultati indesiderati o imprevisti in risposta alle azioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="86adf-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="86adf-121">Ad esempio, una chiave errata o altri determini, si potrebbero smettere di funzionare nei parametri previsti, l'applicazione o del tutto.</span><span class="sxs-lookup"><span data-stu-id="86adf-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="86adf-122">Gli errori logici sono in genere il tipo più difficile da correggere, perché non è sempre chiaro dove provengono.</span><span class="sxs-lookup"><span data-stu-id="86adf-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86adf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86adf-123">See Also</span></span>  
 <span data-ttu-id="86adf-124">[Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="86adf-124">[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
<span data-ttu-id="86adf-125"> [Nozioni di base sul debugger](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span><span class="sxs-lookup"><span data-stu-id="86adf-125"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span></span>
