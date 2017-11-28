---
title: Strutture decisionali (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38820b6ca0a8f716dcaa28644bb25eb4899bd511
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="d4683-102">Strutture decisionali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4683-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="d4683-103">Consente di condizioni di test ed eseguire operazioni diverse in base ai risultati del test.</span><span class="sxs-lookup"><span data-stu-id="d4683-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="d4683-104">È possibile testare una condizione è true o false per diversi valori di un'espressione o per diverse eccezioni generate quando si esegue una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d4683-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="d4683-105">Nella figura seguente mostra una struttura decisionale che verifica una condizione è true e azioni diverse a seconda se è true o false.</span><span class="sxs-lookup"><span data-stu-id="d4683-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="d4683-106">![Diagramma di flusso di un blocco If... Quindi... Costruzione else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="d4683-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="d4683-107">Operazioni diverse quando una condizione è true e false</span><span class="sxs-lookup"><span data-stu-id="d4683-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="d4683-108">Se... Quindi... Costruzione else</span><span class="sxs-lookup"><span data-stu-id="d4683-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="d4683-109">`If...Then...Else`consentono di verificare la presenza di una o più condizioni ed eseguire uno o più istruzioni in base a ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="d4683-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="d4683-110">È possibile verificare le condizioni e intraprendere azioni nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4683-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="d4683-111">Eseguire una o più istruzioni se una condizione`True`</span><span class="sxs-lookup"><span data-stu-id="d4683-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="d4683-112">Eseguire una o più istruzioni se una condizione`False`</span><span class="sxs-lookup"><span data-stu-id="d4683-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="d4683-113">Eseguire alcune istruzioni se una condizione è `True` e altri se è`False`</span><span class="sxs-lookup"><span data-stu-id="d4683-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="d4683-114">Verificare una condizione aggiuntiva se è una condizione preliminare`False`</span><span class="sxs-lookup"><span data-stu-id="d4683-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="d4683-115">È la struttura di controllo che offre tutte queste possibilità di [se... Quindi... Istruzione else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4683-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="d4683-116">Se si dispone di un'unica verifica e un'istruzione per l'esecuzione, è possibile utilizzare una versione a riga singola.</span><span class="sxs-lookup"><span data-stu-id="d4683-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="d4683-117">Se si dispone di un set di condizioni e azioni più complesso, è possibile utilizzare la versione di più righe.</span><span class="sxs-lookup"><span data-stu-id="d4683-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="d4683-118">Seleziona... Costruzione di case</span><span class="sxs-lookup"><span data-stu-id="d4683-118">Select...Case Construction</span></span>  
 <span data-ttu-id="d4683-119">Il `Select...Case` costruzione consente di valutare un'espressione una sola volta e di eseguire diversi set di istruzioni in base a diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="d4683-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="d4683-120">Per ulteriori informazioni, vedere [Seleziona... Istruzione case](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4683-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="d4683-121">Try... Catch... Infine costruzione</span><span class="sxs-lookup"><span data-stu-id="d4683-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="d4683-122">`Try...Catch...Finally`consentono di eseguire un set di istruzioni in un ambiente che mantiene il controllo, se una qualsiasi delle istruzioni genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d4683-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="d4683-123">È possibile eseguire diverse azioni per le eccezioni diverse.</span><span class="sxs-lookup"><span data-stu-id="d4683-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="d4683-124">È possibile specificare facoltativamente un blocco di codice che viene eseguito prima di terminare l'intera `Try...Catch...Finally` costruzione, indipendentemente da ciò che si verifica.</span><span class="sxs-lookup"><span data-stu-id="d4683-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="d4683-125">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4683-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4683-126">Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="d4683-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="d4683-127">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="d4683-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="d4683-128">Per spostarsi alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="d4683-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4683-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4683-129">See Also</span></span>  
 [<span data-ttu-id="d4683-130">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="d4683-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="d4683-131">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="d4683-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="d4683-132">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="d4683-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="d4683-133">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="d4683-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="d4683-134">Operatore If</span><span class="sxs-lookup"><span data-stu-id="d4683-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
