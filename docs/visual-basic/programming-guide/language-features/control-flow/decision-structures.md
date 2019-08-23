---
title: Strutture decisionali (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: f0df649c4be50e9cadd51258c89137b68b4ffe22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963195"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="21087-102">Strutture decisionali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21087-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="21087-103">Visual Basic consente di verificare le condizioni ed eseguire diverse operazioni in base ai risultati del test.</span><span class="sxs-lookup"><span data-stu-id="21087-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="21087-104">È possibile verificare se una condizione è true o false, per i diversi valori di un'espressione o per varie eccezioni generate quando si esegue una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="21087-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="21087-105">Nella figura seguente viene illustrata una struttura decisionale che verifica la presenza di una condizione true e che esegue azioni diverse a seconda che sia true o false.</span><span class="sxs-lookup"><span data-stu-id="21087-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Un diagramma di flusso di un if... Quindi... Costruzione else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="21087-107">Se... Quindi... Costruzione else</span><span class="sxs-lookup"><span data-stu-id="21087-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="21087-108">`If...Then...Else`le costruzioni consentono di testare una o più condizioni ed eseguire una o più istruzioni a seconda di ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="21087-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="21087-109">È possibile verificare le condizioni e intraprendere azioni nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21087-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="21087-110">Eseguire una o più istruzioni se una condizione è`True`</span><span class="sxs-lookup"><span data-stu-id="21087-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="21087-111">Eseguire una o più istruzioni se una condizione è`False`</span><span class="sxs-lookup"><span data-stu-id="21087-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="21087-112">Eseguire alcune istruzioni se una condizione è `True` e altre se è`False`</span><span class="sxs-lookup"><span data-stu-id="21087-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="21087-113">Testare una condizione aggiuntiva se una condizione precedente è`False`</span><span class="sxs-lookup"><span data-stu-id="21087-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="21087-114">La struttura di controllo che offre tutte queste possibilità è il [... Quindi... Else (istruzione](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="21087-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="21087-115">È possibile utilizzare una versione a riga singola se si dispone solo di un test e di un'istruzione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="21087-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="21087-116">Se si dispone di un set più complesso di condizioni e azioni, è possibile usare la versione a più righe.</span><span class="sxs-lookup"><span data-stu-id="21087-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="21087-117">Seleziona... Costruzione case</span><span class="sxs-lookup"><span data-stu-id="21087-117">Select...Case Construction</span></span>  
 <span data-ttu-id="21087-118">La `Select...Case` costruzione consente di valutare un'espressione una sola volta ed eseguire set di istruzioni diversi in base a valori possibili differenti.</span><span class="sxs-lookup"><span data-stu-id="21087-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="21087-119">Per ulteriori informazioni, vedere [Select... Istruzione case](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21087-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="21087-120">Prova... Rileva... Costruzione definitiva</span><span class="sxs-lookup"><span data-stu-id="21087-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="21087-121">`Try...Catch...Finally`le costruzioni consentono di eseguire un set di istruzioni in un ambiente che mantiene il controllo se una qualsiasi delle istruzioni causa un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="21087-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="21087-122">È possibile eseguire azioni diverse per le diverse eccezioni.</span><span class="sxs-lookup"><span data-stu-id="21087-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="21087-123">Facoltativamente, è possibile specificare un blocco di codice che viene eseguito prima di uscire `Try...Catch...Finally` dall'intera costruzione, indipendentemente da ciò che si verifica.</span><span class="sxs-lookup"><span data-stu-id="21087-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="21087-124">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21087-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21087-125">Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="21087-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="21087-126">Ad esempio, quando si fa `If` clic in `If...Then...Else` una costruzione, vengono evidenziate `Then`tutte `ElseIf`le `Else`istanze di `End If` `If`,,, e nella costruzione.</span><span class="sxs-lookup"><span data-stu-id="21087-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="21087-127">Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="21087-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21087-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21087-128">See also</span></span>

- [<span data-ttu-id="21087-129">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="21087-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="21087-130">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="21087-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="21087-131">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="21087-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="21087-132">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="21087-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="21087-133">Operatore If</span><span class="sxs-lookup"><span data-stu-id="21087-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
