---
title: Strutture di controllo annidate
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
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266924"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="2206e-102">Strutture di controllo annidate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2206e-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="2206e-103">È possibile inserire istruzioni di controllo all'interno `If...Then...Else` di `For...Next` altre istruzioni di controllo, ad esempio un blocco all'interno di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="2206e-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="2206e-104">Un'istruzione di controllo inserita all'interno di un'altra istruzione di controllo viene detta *annidata.*</span><span class="sxs-lookup"><span data-stu-id="2206e-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="2206e-105">Livelli di nidificazione</span><span class="sxs-lookup"><span data-stu-id="2206e-105">Nesting Levels</span></span>  
 <span data-ttu-id="2206e-106">Le strutture di controllo in Visual Basic possono essere annidate a tutti i livelli desiderati.</span><span class="sxs-lookup"><span data-stu-id="2206e-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="2206e-107">È pratica comune rendere le strutture annidate più leggibili applicando un rientro al corpo di ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="2206e-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="2206e-108">L'editor dell'ambiente di sviluppo integrato (IDE) esegue automaticamente questa operazione.</span><span class="sxs-lookup"><span data-stu-id="2206e-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="2206e-109">Nell'esempio seguente la `sumRows` routine somma gli elementi positivi di ogni riga della matrice.</span><span class="sxs-lookup"><span data-stu-id="2206e-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
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
  
 <span data-ttu-id="2206e-110">Nell'esempio precedente, la `Next` prima istruzione `For` chiude il `Next` ciclo interno e `For` l'ultima istruzione chiude il ciclo esterno.</span><span class="sxs-lookup"><span data-stu-id="2206e-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="2206e-111">Analogamente, `If` nelle istruzioni `End If` annidate, le istruzioni `If` si applicano automaticamente all'istruzione precedente più vicina.</span><span class="sxs-lookup"><span data-stu-id="2206e-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="2206e-112">I `Do` cicli annidati funzionano in modo `Loop` simile, con `Do` l'istruzione più interna corrispondente all'istruzione più interna.</span><span class="sxs-lookup"><span data-stu-id="2206e-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2206e-113">Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="2206e-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="2206e-114">Ad esempio, quando `If` si `If...Then...Else` fa clic `If`in `Then` `ElseIf`una `Else`costruzione, tutte le istanze di , , , e `End If` nella costruzione vengono evidenziate.</span><span class="sxs-lookup"><span data-stu-id="2206e-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="2206e-115">Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL-MAIUSC-FRECCIA GIU' o CTRL-MAIUSC-FRECCIA SU.</span><span class="sxs-lookup"><span data-stu-id="2206e-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="2206e-116">Nidificazione di diversi tipi di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="2206e-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="2206e-117">È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="2206e-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="2206e-118">L'esempio seguente `With` usa `For Each` un blocco `If` all'interno di un ciclo e blocchi annidati all'interno del `With` blocco.</span><span class="sxs-lookup"><span data-stu-id="2206e-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="2206e-119">Strutture di controllo sovrapposte</span><span class="sxs-lookup"><span data-stu-id="2206e-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="2206e-120">Non è possibile sovrapporre strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="2206e-120">You cannot overlap control structures.</span></span> <span data-ttu-id="2206e-121">Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta all'interno della struttura più interna successiva.</span><span class="sxs-lookup"><span data-stu-id="2206e-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="2206e-122">Ad esempio, la disposizione `For` seguente non è `With` valida perché il ciclo termina prima che il blocco interno termini.</span><span class="sxs-lookup"><span data-stu-id="2206e-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagramma che mostra un esempio di annidamento non valido.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="2206e-124">Il compilatore Visual Basic rileva tali strutture di controllo sovrapposte e segnala un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2206e-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2206e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2206e-125">See also</span></span>

- [<span data-ttu-id="2206e-126">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="2206e-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="2206e-127">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="2206e-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="2206e-128">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="2206e-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2206e-129">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="2206e-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
