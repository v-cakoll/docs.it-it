---
title: La decisione di strutture (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
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
ms.openlocfilehash: dcbfb4bc3318d5f79870d04e606fab8bfa2dafb9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="b5e80-102">Strutture decisionali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5e80-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b5e80-103">Consente di condizioni di test ed eseguire operazioni diverse in base ai risultati del test.</span><span class="sxs-lookup"><span data-stu-id="b5e80-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="b5e80-104">È possibile verificare una condizione è true o false per diversi valori di un'espressione o per diverse eccezioni generate quando si esegue una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b5e80-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="b5e80-105">Nella figura seguente mostra una struttura decisionale che verifica la presenza di una condizione true ed esegue azioni diverse a seconda se è true o false.</span><span class="sxs-lookup"><span data-stu-id="b5e80-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="b5e80-106">![Diagramma di flusso di un blocco If... Quindi... Costruzione else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="b5e80-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="b5e80-107">Operazioni diverse quando una condizione è true e false</span><span class="sxs-lookup"><span data-stu-id="b5e80-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="b5e80-108">If... Quindi... Costruzione else</span><span class="sxs-lookup"><span data-stu-id="b5e80-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="b5e80-109">`If...Then...Else`consentono di testare per una o più condizioni ed eseguire una o più istruzioni in base a ogni condizione.</span><span class="sxs-lookup"><span data-stu-id="b5e80-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="b5e80-110">È possibile verificare le condizioni e intraprendere azioni nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5e80-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="b5e80-111">Eseguire una o più istruzioni se una condizione`True`</span><span class="sxs-lookup"><span data-stu-id="b5e80-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="b5e80-112">Eseguire una o più istruzioni se una condizione`False`</span><span class="sxs-lookup"><span data-stu-id="b5e80-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="b5e80-113">Eseguire alcune istruzioni se una condizione è `True` e altri in questo caso`False`</span><span class="sxs-lookup"><span data-stu-id="b5e80-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="b5e80-114">Verificare una condizione aggiuntiva se la prima condizione è`False`</span><span class="sxs-lookup"><span data-stu-id="b5e80-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="b5e80-115">La struttura di controllo che offre tutte queste possibilità è la [se... Quindi... Istruzione else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5e80-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="b5e80-116">Se si dispone solo un test e un'istruzione per l'esecuzione, è possibile utilizzare una versione a riga singola.</span><span class="sxs-lookup"><span data-stu-id="b5e80-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="b5e80-117">Se si dispone di un set di condizioni e azioni più complesso, è possibile utilizzare la versione più righe.</span><span class="sxs-lookup"><span data-stu-id="b5e80-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="b5e80-118">Seleziona... Costruzione di case</span><span class="sxs-lookup"><span data-stu-id="b5e80-118">Select...Case Construction</span></span>  
 <span data-ttu-id="b5e80-119">Il `Select...Case` costruzione consente di valutare un'espressione una sola volta e di eseguire diversi set di istruzioni basate su diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="b5e80-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="b5e80-120">Per ulteriori informazioni, vedere [Seleziona... Case (istruzione)](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5e80-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="b5e80-121">Try... Catch... Infine costruzione</span><span class="sxs-lookup"><span data-stu-id="b5e80-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="b5e80-122">`Try...Catch...Finally`consentono di eseguire un set di istruzioni in un ambiente che mantiene il controllo se una qualsiasi di tali istruzioni genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b5e80-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="b5e80-123">È possibile eseguire azioni diverse per le diverse eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b5e80-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="b5e80-124">È possibile specificare facoltativamente un blocco di codice da eseguire prima di terminare l'intera `Try...Catch...Finally` costruzione, indipendentemente dall'esito.</span><span class="sxs-lookup"><span data-stu-id="b5e80-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="b5e80-125">Per ulteriori informazioni, vedere [Try... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5e80-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5e80-126">Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="b5e80-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="b5e80-127">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="b5e80-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="b5e80-128">Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="b5e80-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e80-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5e80-129">See Also</span></span>  
 <span data-ttu-id="b5e80-130">[Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="b5e80-130">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="b5e80-131"> [Cicli (strutture)](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="b5e80-131"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="b5e80-132"> [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="b5e80-132"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="b5e80-133"> [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="b5e80-133"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="b5e80-134"> [Operatore If](../../../../visual-basic/language-reference/operators/if-operator.md)</span><span class="sxs-lookup"><span data-stu-id="b5e80-134"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span></span>
