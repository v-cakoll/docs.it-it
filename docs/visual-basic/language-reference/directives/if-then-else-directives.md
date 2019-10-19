---
title: '#Se... Direttive then... #Else (Visual Basic)'
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
ms.openlocfilehash: aaf5e7dd82cebf734da59e9feb89174705468a4b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580082"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="de5ff-102">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="de5ff-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="de5ff-103">Compila in modo condizionale i blocchi selezionati del codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="de5ff-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="de5ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de5ff-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="de5ff-105">Parti</span><span class="sxs-lookup"><span data-stu-id="de5ff-105">Parts</span></span>

`expression`  
<span data-ttu-id="de5ff-106">Obbligatorio per le istruzioni `#If` e `#ElseIf`, facoltativo altrove.</span><span class="sxs-lookup"><span data-stu-id="de5ff-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="de5ff-107">Qualsiasi espressione, costituita esclusivamente da una o più costanti del compilatore condizionali, valori letterali e operatori, che restituisce `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="de5ff-108">Obbligatorio per `#If` blocco di istruzioni, facoltativo altrove.</span><span class="sxs-lookup"><span data-stu-id="de5ff-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="de5ff-109">Visual Basic linee di programma o direttive del compilatore compilate se l'espressione associata restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="de5ff-110">Termina il blocco di istruzioni `#If`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="de5ff-111">Note</span><span class="sxs-lookup"><span data-stu-id="de5ff-111">Remarks</span></span>

<span data-ttu-id="de5ff-112">Nell'area, il comportamento delle direttive `#If...Then...#Else` viene visualizzato come quello delle istruzioni `If...Then...Else`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="de5ff-113">Tuttavia, le direttive `#If...Then...#Else` valutano gli elementi compilati dal compilatore, mentre le istruzioni `If...Then...Else` valutano le condizioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="de5ff-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="de5ff-114">La compilazione condizionale viene in genere utilizzata per compilare lo stesso programma per piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="de5ff-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="de5ff-115">Viene inoltre usato per impedire che il codice di debug venga visualizzato in un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="de5ff-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="de5ff-116">Il codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, quindi non ha alcun effetto sulle dimensioni o sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="de5ff-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="de5ff-117">Indipendentemente dal risultato di una valutazione, tutte le espressioni vengono valutate utilizzando `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="de5ff-118">L'istruzione `Option Compare` non influisce sulle espressioni nelle istruzioni `#If` e `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="de5ff-119">Non esiste alcuna forma a riga singola delle direttive `#If`, `#Else`, `#ElseIf` e `#End If`.</span><span class="sxs-lookup"><span data-stu-id="de5ff-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="de5ff-120">Non è possibile visualizzare altro codice nella stessa riga delle direttive.</span><span class="sxs-lookup"><span data-stu-id="de5ff-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="de5ff-121">Le istruzioni all'interno di un blocco di compilazione condizionale devono essere istruzioni logiche complete.</span><span class="sxs-lookup"><span data-stu-id="de5ff-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="de5ff-122">Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare la funzione in modo condizionale insieme ai relativi attributi:</span><span class="sxs-lookup"><span data-stu-id="de5ff-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="de5ff-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="de5ff-123">Example</span></span>

<span data-ttu-id="de5ff-124">Questo esempio usa il costrutto `#If...Then...#Else` per determinare se compilare determinate istruzioni.</span><span class="sxs-lookup"><span data-stu-id="de5ff-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="de5ff-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de5ff-125">See also</span></span>

- [<span data-ttu-id="de5ff-126">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="de5ff-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="de5ff-127">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="de5ff-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="de5ff-128">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="de5ff-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
