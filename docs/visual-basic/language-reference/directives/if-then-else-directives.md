---
title: '#Direttive If...Then...#Else'
ms.date: 04/11/2018
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
ms.openlocfilehash: 7054a6ada4583c5d89e020437eb622a59d3eb17a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410010"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="c8c56-102">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="c8c56-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="c8c56-103">Compila in modo condizionale i blocchi selezionati del codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c8c56-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8c56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8c56-104">Syntax</span></span>

```vb
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

## <a name="parts"></a><span data-ttu-id="c8c56-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c8c56-105">Parts</span></span>

`expression`  
<span data-ttu-id="c8c56-106">Obbligatorio per `#If` le `#ElseIf` istruzioni e, facoltativo altrove.</span><span class="sxs-lookup"><span data-stu-id="c8c56-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="c8c56-107">Qualsiasi espressione, costituita esclusivamente da una o più costanti del compilatore condizionali, valori letterali e operatori, che restituiscono `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="c8c56-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="c8c56-108">Obbligatorio per il `#If` blocco di istruzioni, facoltativo altrove.</span><span class="sxs-lookup"><span data-stu-id="c8c56-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="c8c56-109">Visual Basic linee di programma o direttive del compilatore compilate se l'espressione associata restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="c8c56-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="c8c56-110">Termina il `#If` blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8c56-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8c56-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="c8c56-111">Remarks</span></span>

<span data-ttu-id="c8c56-112">Nell'area, il comportamento delle `#If...Then...#Else` direttive appare come quello delle `If...Then...Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8c56-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="c8c56-113">Tuttavia, le `#If...Then...#Else` direttive valutano gli elementi compilati dal compilatore, mentre le `If...Then...Else` istruzioni valutano le condizioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c8c56-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="c8c56-114">La compilazione condizionale viene in genere utilizzata per compilare lo stesso programma per piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="c8c56-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="c8c56-115">Viene inoltre usato per impedire che il codice di debug venga visualizzato in un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c8c56-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="c8c56-116">Il codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, quindi non ha alcun effetto sulle dimensioni o sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c8c56-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="c8c56-117">Indipendentemente dal risultato di una valutazione, tutte le espressioni vengono valutate mediante `Option Compare Binary` .</span><span class="sxs-lookup"><span data-stu-id="c8c56-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="c8c56-118">L' `Option Compare` istruzione non influisce sulle espressioni `#If` nelle `#ElseIf` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="c8c56-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="c8c56-119">Non esiste alcuna forma a riga singola `#If` delle `#Else` `#ElseIf` direttive,, e `#End If` .</span><span class="sxs-lookup"><span data-stu-id="c8c56-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="c8c56-120">Non è possibile visualizzare altro codice nella stessa riga delle direttive.</span><span class="sxs-lookup"><span data-stu-id="c8c56-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="c8c56-121">Le istruzioni all'interno di un blocco di compilazione condizionale devono essere istruzioni logiche complete.</span><span class="sxs-lookup"><span data-stu-id="c8c56-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="c8c56-122">Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare la funzione in modo condizionale insieme ai relativi attributi:</span><span class="sxs-lookup"><span data-stu-id="c8c56-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="c8c56-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8c56-123">Example</span></span>

<span data-ttu-id="c8c56-124">Questo esempio usa il `#If...Then...#Else` costrutto per determinare se compilare determinate istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8c56-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c8c56-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c56-125">See also</span></span>

- [<span data-ttu-id="c8c56-126">#Const (direttiva)</span><span class="sxs-lookup"><span data-stu-id="c8c56-126">#Const Directive</span></span>](const-directive.md)
- [<span data-ttu-id="c8c56-127">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="c8c56-127">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="c8c56-128">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="c8c56-128">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
