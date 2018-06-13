---
title: Strutture di controllo annidate (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: ec3d4d477290480cdfa0f5b1c88aa82c81040d11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648072"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="f2371-102">Strutture di controllo annidate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2371-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="f2371-103">È possibile inserire le istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocco all'interno di un `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="f2371-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="f2371-104">Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo è detta *nidificata*.</span><span class="sxs-lookup"><span data-stu-id="f2371-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="f2371-105">Livelli di annidamento</span><span class="sxs-lookup"><span data-stu-id="f2371-105">Nesting Levels</span></span>  
 <span data-ttu-id="f2371-106">Strutture di controllo in Visual Basic possono essere nidificate fino a un numero di livelli.</span><span class="sxs-lookup"><span data-stu-id="f2371-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="f2371-107">È pratica comune per rendere più leggibile strutture annidate rientrare il corpo di ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="f2371-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="f2371-108">L'editor di sviluppo integrato (IDE) di ambiente automaticamente esegue questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f2371-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="f2371-109">Nell'esempio seguente, la procedura `sumRows` per sommare positivo gli elementi di ogni riga della matrice.</span><span class="sxs-lookup"><span data-stu-id="f2371-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```  
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="f2371-110">Nell'esempio precedente, il primo `Next` istruzione chiude il `For` ciclo e l'ultimo `Next` istruzione chiude esterna `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="f2371-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="f2371-111">Analogamente, in annidati `If` istruzioni, il `End If` istruzioni vengono applicate automaticamente al precedente più vicino `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2371-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="f2371-112">Annidati `Do` cicli di lavoro in modo simile, con più interna `Loop` corrispondente alla più interna `Do` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f2371-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2371-113">Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="f2371-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="f2371-114">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="f2371-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="f2371-115">Per spostarsi alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="f2371-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="f2371-116">Annidamento di tipi diversi di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f2371-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="f2371-117">È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="f2371-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="f2371-118">Nell'esempio seguente viene utilizzato un `With` blocco un `For Each` ciclo e nidificate `If` blocchi all'interno di `With` blocco.</span><span class="sxs-lookup"><span data-stu-id="f2371-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```  
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="f2371-119">Sovrapposizione di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f2371-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="f2371-120">Non è possibile sovrapporre le strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="f2371-120">You cannot overlap control structures.</span></span> <span data-ttu-id="f2371-121">Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta all'interno della successiva struttura più interna.</span><span class="sxs-lookup"><span data-stu-id="f2371-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="f2371-122">Ad esempio, la disposizione seguente non è valida perché il `For` ciclo termina prima del `With` termina.</span><span class="sxs-lookup"><span data-stu-id="f2371-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="f2371-123">![Diagramma grafico di annidamento non valida](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="f2371-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="f2371-124">Annidamento non valido di per e con strutture</span><span class="sxs-lookup"><span data-stu-id="f2371-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="f2371-125">Il compilatore Visual Basic rileva le strutture di controllo sovrapposte e segnala un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2371-125">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2371-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2371-126">See Also</span></span>  
 [<span data-ttu-id="f2371-127">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="f2371-127">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="f2371-128">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="f2371-128">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="f2371-129">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="f2371-129">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="f2371-130">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f2371-130">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
