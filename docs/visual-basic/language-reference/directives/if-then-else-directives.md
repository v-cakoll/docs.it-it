---
title: '#Se... Then... #Else direttive'
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884c7ed6f0a346f2d35f01006cea23e47907d13f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="4d220-102">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="4d220-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="4d220-103">Consente di compilare in modo condizionale blocchi di codice Visual Basic selezionati.</span><span class="sxs-lookup"><span data-stu-id="4d220-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d220-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d220-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="4d220-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4d220-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="4d220-106">Necessario per `#If` e `#ElseIf` istruzioni, facoltative in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="4d220-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="4d220-107">Qualsiasi espressione, costituita esclusivamente da uno o più costanti del compilatore condizionale, valori letterali e operatori, che restituisce `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="4d220-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="4d220-108">Necessario per `#If` blocco di istruzioni, facoltativo in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="4d220-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="4d220-109">Righe di programma Visual Basic o le direttive del compilatore che vengono compilate se l'espressione associata restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="4d220-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="4d220-110">Termina il `#If` blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4d220-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d220-111">Note</span><span class="sxs-lookup"><span data-stu-id="4d220-111">Remarks</span></span>  
 <span data-ttu-id="4d220-112">Nell'area di, il comportamento del `#If...Then...#Else` direttive viene visualizzato lo stesso di quello del `If...Then...Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4d220-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="4d220-113">Tuttavia, il `#If...Then...#Else` valutano ciò che viene compilato dal compilatore, mentre il `If...Then...Else` istruzioni valutano le condizioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d220-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="4d220-114">Compilazione condizionale viene in genere utilizzata per la compilazione del programma stesso per le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="4d220-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="4d220-115">Viene inoltre utilizzato per impedire il debug del codice venga visualizzato in un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4d220-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="4d220-116">Codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, in modo non ha alcun effetto su dimensioni e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4d220-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="4d220-117">Indipendentemente dal risultato di ogni valutazione, tutte le espressioni vengono valutate utilizzando `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="4d220-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="4d220-118">Il `Option Compare` istruzione non ha effetto sulle espressioni in `#If` e `#ElseIf` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4d220-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d220-119">Nessuna forma a riga singola del `#If`, `#Else`, `#ElseIf`, e `#End If` direttive esiste.</span><span class="sxs-lookup"><span data-stu-id="4d220-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="4d220-120">Nessun altro codice può trovarsi nella stessa riga come una delle direttive.</span><span class="sxs-lookup"><span data-stu-id="4d220-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="4d220-121">Le istruzioni all'interno di un blocco di compilazione condizionale devono essere istruzioni logiche completate.</span><span class="sxs-lookup"><span data-stu-id="4d220-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="4d220-122">Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare in modo condizionale la funzione insieme ai relativi attributi:</span><span class="sxs-lookup"><span data-stu-id="4d220-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="4d220-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d220-123">Example</span></span>
 <span data-ttu-id="4d220-124">Questo esempio viene utilizzato il `#If...Then...#Else` costrutto per determinare se alcune istruzioni di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4d220-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d220-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d220-125">See Also</span></span>  
[<span data-ttu-id="4d220-126">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="4d220-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
[<span data-ttu-id="4d220-127">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="4d220-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
<span data-ttu-id="4d220-128">[Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="4d220-128">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


