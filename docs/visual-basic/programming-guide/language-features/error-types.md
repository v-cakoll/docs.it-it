---
title: Tipi di errore (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b3cf1307f54a5c902bf8e6379c8760c735a45e4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="0455b-102">Tipi di errore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0455b-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="0455b-103">In Visual Basic, gli errori (chiamato anche *eccezioni*) rientrano in una delle tre categorie: errori di sintassi, errori di run-time e gli errori di logica.</span><span class="sxs-lookup"><span data-stu-id="0455b-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="0455b-104">Errori di sintassi</span><span class="sxs-lookup"><span data-stu-id="0455b-104">Syntax Errors</span></span>  
 <span data-ttu-id="0455b-105">*Errori di sintassi* vengono visualizzati durante la scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="0455b-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="0455b-106">Visual Basic controlla il codice come si digita il **Editor di codice** finestra e genera avvisi se si commette un errore, ad esempio ortografia errata di una parola o l'utilizzo improprio di un elemento di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="0455b-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="0455b-107">Errori di sintassi sono il tipo più comune di errori.</span><span class="sxs-lookup"><span data-stu-id="0455b-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="0455b-108">È possibile correggerli facilmente nell'ambiente di codifica, non appena si verificano.</span><span class="sxs-lookup"><span data-stu-id="0455b-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0455b-109">Il `Option Explicit` istruzione è consente di evitare errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="0455b-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="0455b-110">Impone di dichiarare in anticipo, tutte le variabili da utilizzare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0455b-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="0455b-111">Pertanto, quando tali variabili vengono utilizzate nel codice, gli errori di digitazione vengono rilevati immediatamente e possono essere risolto.</span><span class="sxs-lookup"><span data-stu-id="0455b-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="0455b-112">Errori di Run-Time</span><span class="sxs-lookup"><span data-stu-id="0455b-112">Run-Time Errors</span></span>  
 <span data-ttu-id="0455b-113">*Errori di run-time* sono quelli che vengono visualizzate solo dopo che viene compilato ed eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="0455b-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="0455b-114">Che implicano il codice che potrebbe risultare corretto in quanto non ha gli errori di sintassi, ma che non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="0455b-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="0455b-115">Ad esempio, è possibile scrivere correttamente una riga di codice per aprire un file.</span><span class="sxs-lookup"><span data-stu-id="0455b-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="0455b-116">Ma se il file è danneggiato, l'applicazione non è possibile eseguire il `Open` (funzione) e arresta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0455b-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="0455b-117">È possibile risolvere la maggior parte degli errori di runtime per la riscrittura del codice non corretto, quindi ricompilare ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="0455b-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="0455b-118">Errori di logica</span><span class="sxs-lookup"><span data-stu-id="0455b-118">Logic Errors</span></span>  
 <span data-ttu-id="0455b-119">*Errori di logica* vengono visualizzati una volta che l'applicazione è in uso.</span><span class="sxs-lookup"><span data-stu-id="0455b-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="0455b-120">Sono la maggior parte dei risultati indesiderati o imprevisti in risposta alle azioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0455b-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="0455b-121">Ad esempio, una chiave digitata incorrettamente o altri determini potrebbero causare l'applicazione per smettere di funzionare nei parametri previsti o del tutto.</span><span class="sxs-lookup"><span data-stu-id="0455b-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="0455b-122">Errori logici sono in genere il tipo più difficile da risolvere poiché non è sempre chiaro in cui sono generati.</span><span class="sxs-lookup"><span data-stu-id="0455b-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0455b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0455b-123">See Also</span></span>  
 [<span data-ttu-id="0455b-124">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="0455b-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 <span data-ttu-id="0455b-125">[Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)</span><span class="sxs-lookup"><span data-stu-id="0455b-125">[Debugger Basics](/visualstudio/debugger/debugger-basics)</span></span>
