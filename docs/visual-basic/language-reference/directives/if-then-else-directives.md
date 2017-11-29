---
title: '#<a name="ifthenelse-directives"></a>Se... Then... #Else direttive'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="346b3-102">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="346b3-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="346b3-103">Consente di compilare in modo condizionale blocchi di codice Visual Basic selezionati.</span><span class="sxs-lookup"><span data-stu-id="346b3-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="346b3-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="346b3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="346b3-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="346b3-106">Necessario per `#If` e `#ElseIf` istruzioni, facoltative in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="346b3-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="346b3-107">Qualsiasi espressione, costituita esclusivamente da uno o più costanti del compilatore condizionale, valori letterali e operatori, che restituisce `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="346b3-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="346b3-108">Necessario per `#If` blocco di istruzioni, facoltativo in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="346b3-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="346b3-109">Righe di programma Visual Basic o le direttive del compilatore che vengono compilate se l'espressione associata restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="346b3-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="346b3-110">Termina il `#If` blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="346b3-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="346b3-111">Note</span><span class="sxs-lookup"><span data-stu-id="346b3-111">Remarks</span></span>  
 <span data-ttu-id="346b3-112">Nell'area di, il comportamento del `#If...Then...#Else` direttive viene visualizzato lo stesso di quello del `If...Then...Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="346b3-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="346b3-113">Tuttavia, il `#If...Then...#Else` valutano ciò che viene compilato dal compilatore, mentre il `If...Then...Else` istruzioni valutano le condizioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="346b3-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="346b3-114">Compilazione condizionale viene in genere utilizzata per la compilazione del programma stesso per le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="346b3-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="346b3-115">Viene inoltre utilizzato per impedire il debug del codice venga visualizzato in un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="346b3-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="346b3-116">Codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, in modo non ha alcun effetto su dimensioni e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="346b3-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="346b3-117">Indipendentemente dal risultato di ogni valutazione, tutte le espressioni vengono valutate utilizzando `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="346b3-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="346b3-118">Il `Option Compare` istruzione non ha effetto sulle espressioni in `#If` e `#ElseIf` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="346b3-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="346b3-119">Nessuna forma a riga singola del `#If`, `#Else`, `#ElseIf`, e `#End If` direttive esiste.</span><span class="sxs-lookup"><span data-stu-id="346b3-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="346b3-120">Nessun altro codice può trovarsi nella stessa riga come una delle direttive.</span><span class="sxs-lookup"><span data-stu-id="346b3-120">No other code can appear on the same line as any of the directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="346b3-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="346b3-121">Example</span></span>  
 <span data-ttu-id="346b3-122">Questo esempio viene utilizzato il `#If...Then...#Else` costrutto per determinare se alcune istruzioni di compilazione.</span><span class="sxs-lookup"><span data-stu-id="346b3-122">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="346b3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="346b3-123">See Also</span></span>  
 [<span data-ttu-id="346b3-124">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="346b3-124">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="346b3-125">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="346b3-125">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="346b3-126">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="346b3-126">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
