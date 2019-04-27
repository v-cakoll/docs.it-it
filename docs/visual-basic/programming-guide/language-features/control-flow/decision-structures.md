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
ms.openlocfilehash: 4a76b2565c343e69ac3c11441035a7682a8f08ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907004"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="dcfc2-102">Strutture decisionali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcfc2-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="dcfc2-103">Visual Basic consente di testare condizioni ed eseguire operazioni diverse a seconda del risultato di un test.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="dcfc2-104">È possibile testare una condizione sia true o false, per diversi valori di un'espressione o di diverse eccezioni generate quando si esegue una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="dcfc2-105">La figura seguente illustra una struttura decisionale che verifica la presenza di una condizione sia true ed esegue azioni diverse a seconda che sia true o false.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Un diagramma di flusso di un blocco If... Quindi... Costruzione else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="dcfc2-107">If... Quindi... Costruzione else</span><span class="sxs-lookup"><span data-stu-id="dcfc2-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="dcfc2-108">`If...Then...Else` consentono di verificare che una o più condizioni ed eseguire una o più istruzioni in base a ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="dcfc2-109">È possibile testare condizioni e intraprendere azioni nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcfc2-109">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="dcfc2-110">Eseguire una o più istruzioni se una condizione `True`</span><span class="sxs-lookup"><span data-stu-id="dcfc2-110">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="dcfc2-111">Eseguire una o più istruzioni se una condizione `False`</span><span class="sxs-lookup"><span data-stu-id="dcfc2-111">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="dcfc2-112">Eseguire alcune istruzioni se una condizione è `True` e ad altri utenti se si tratta di `False`</span><span class="sxs-lookup"><span data-stu-id="dcfc2-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="dcfc2-113">Verificare una condizione aggiuntiva se la prima condizione è `False`</span><span class="sxs-lookup"><span data-stu-id="dcfc2-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="dcfc2-114">La struttura di controllo che offre tutte queste possibilità di [se... Quindi... Istruzione else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcfc2-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="dcfc2-115">Se si ha solo un test e una sola istruzione per l'esecuzione, è possibile utilizzare una versione a riga singola.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="dcfc2-116">Se si dispone di un set più complesso di condizioni e azioni, è possibile usare la versione più righe.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="dcfc2-117">Seleziona... Costruzione di case</span><span class="sxs-lookup"><span data-stu-id="dcfc2-117">Select...Case Construction</span></span>  
 <span data-ttu-id="dcfc2-118">Il `Select...Case` costruzione consente di valutare un'espressione una sola volta ed eseguire set diversi di istruzioni basate su diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="dcfc2-119">Per altre informazioni, vedere [Seleziona... Istruzione case](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcfc2-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="dcfc2-120">Try... Catch... Infine costruzione</span><span class="sxs-lookup"><span data-stu-id="dcfc2-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="dcfc2-121">`Try...Catch...Finally` consentono di eseguire un set di istruzioni in un ambiente che manterrà il controllo se una delle istruzioni genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="dcfc2-122">È possibile eseguire azioni diverse per le eccezioni diverse.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="dcfc2-123">È possibile specificare facoltativamente un blocco di codice che viene eseguito prima di terminare l'intera `Try...Catch...Finally` costruzione, indipendentemente da ciò che si verifica.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="dcfc2-124">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcfc2-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcfc2-125">Per molte strutture di controllo, quando si fa clic su una parola chiave, sono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="dcfc2-126">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione di strutture vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="dcfc2-127">Per spostare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="dcfc2-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfc2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcfc2-128">See also</span></span>

- [<span data-ttu-id="dcfc2-129">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="dcfc2-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="dcfc2-130">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="dcfc2-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="dcfc2-131">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="dcfc2-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="dcfc2-132">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="dcfc2-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="dcfc2-133">Operatore If</span><span class="sxs-lookup"><span data-stu-id="dcfc2-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
