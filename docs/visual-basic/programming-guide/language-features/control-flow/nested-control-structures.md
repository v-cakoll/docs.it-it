---
title: Annidati strutture di controllo (Visual Basic) | Documenti di Microsoft
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
- Visual Basic code, control flow
- control structures, nested
- conditional statements, nested
- statements [Visual Basic], control flow
- control flow, nested control statements
- structures, nested control
- nested control statements
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
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
ms.openlocfilehash: 8275a0628c8593d9e6c55ef27adcde2acec31547
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="c8a08-102">Strutture di controllo annidate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8a08-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="c8a08-103">È possibile inserire istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocco all'interno di un `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="c8a08-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="c8a08-104">Un'istruzione di controllo inserita in un'altra istruzione di controllo è detto *nidificate*.</span><span class="sxs-lookup"><span data-stu-id="c8a08-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="c8a08-105">Livelli di annidamento</span><span class="sxs-lookup"><span data-stu-id="c8a08-105">Nesting Levels</span></span>  
 <span data-ttu-id="c8a08-106">In strutture di controllo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] possono essere nidificate in un numero di livelli desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8a08-106">Control structures in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="c8a08-107">È pratica comune per rendere più leggibile strutture annidate rientrare il corpo di ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="c8a08-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="c8a08-108">L'editor di sviluppo integrato (IDE) di ambiente esegue automaticamente questa.</span><span class="sxs-lookup"><span data-stu-id="c8a08-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="c8a08-109">Nell'esempio seguente, la procedura `sumRows` sommare gli elementi positivi di ogni riga della matrice.</span><span class="sxs-lookup"><span data-stu-id="c8a08-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="c8a08-110">Nell'esempio precedente, il primo `Next` istruzione chiude il `For` ciclo e l'ultimo `Next` istruzione chiude esterna `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="c8a08-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="c8a08-111">Analogamente, nidificazione `If` istruzioni, il `End If` istruzioni vengono applicate automaticamente al più vicino prima `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c8a08-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="c8a08-112">Annidati `Do` cicli funzionano in modo simile, con più interna `Loop` corrispondente più interna `Do` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c8a08-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8a08-113">Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="c8a08-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="c8a08-114">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="c8a08-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="c8a08-115">Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="c8a08-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="c8a08-116">Annidamento di tipi diversi di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="c8a08-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="c8a08-117">È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="c8a08-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="c8a08-118">Nell'esempio seguente viene utilizzato un `With` blocco all'interno di un `For Each` ciclo e nidificati `If` blocchi all'interno di `With` blocco.</span><span class="sxs-lookup"><span data-stu-id="c8a08-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="c8a08-119">Strutture di controllo sovrapposte</span><span class="sxs-lookup"><span data-stu-id="c8a08-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="c8a08-120">Non è possibile sovrapporre le strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="c8a08-120">You cannot overlap control structures.</span></span> <span data-ttu-id="c8a08-121">Ciò significa che qualsiasi struttura annidata deve essere contenuta completamente nella successiva struttura più interna.</span><span class="sxs-lookup"><span data-stu-id="c8a08-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="c8a08-122">Ad esempio, la disposizione seguente è valida perché il `For` ciclo termina prima del `With` termina.</span><span class="sxs-lookup"><span data-stu-id="c8a08-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="c8a08-123">![Diagramma grafico di annidamento non valida](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="c8a08-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="c8a08-124">Annidamento non valida di per e con strutture</span><span class="sxs-lookup"><span data-stu-id="c8a08-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="c8a08-125">Il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore rileva tale controllo sovrapposto strutture e segnala un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c8a08-125">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a08-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8a08-126">See Also</span></span>  
 <span data-ttu-id="c8a08-127">[Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8a08-127">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="c8a08-128"> [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="c8a08-128"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="c8a08-129"> [Cicli (strutture)](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="c8a08-129"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="c8a08-130"> [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="c8a08-130"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span></span>
