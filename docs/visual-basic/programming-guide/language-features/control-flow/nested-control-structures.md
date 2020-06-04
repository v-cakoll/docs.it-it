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
ms.openlocfilehash: 539ad639320615c1e53176fe47e5468864aa21d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414389"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="f2fa4-102">Strutture di controllo annidate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2fa4-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="f2fa4-103">È possibile inserire istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocco all'interno di un `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="f2fa4-104">Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo è detta *annidata*.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="f2fa4-105">Livelli di annidamento</span><span class="sxs-lookup"><span data-stu-id="f2fa4-105">Nesting Levels</span></span>  
 <span data-ttu-id="f2fa4-106">Le strutture di controllo in Visual Basic possono essere nidificate a tutti i livelli desiderati.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="f2fa4-107">Per rendere più leggibili le strutture annidate, è consigliabile rientrare nel corpo di ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="f2fa4-108">Questa operazione viene eseguita automaticamente dall'editor Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="f2fa4-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="f2fa4-109">Nell'esempio seguente la procedura `sumRows` aggiunge insieme gli elementi positivi di ogni riga della matrice.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="f2fa4-110">Nell'esempio precedente, la prima `Next` istruzione chiude il ciclo interno `For` e l'ultima `Next` istruzione chiude il ciclo esterno `For` .</span><span class="sxs-lookup"><span data-stu-id="f2fa4-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="f2fa4-111">Analogamente, nelle `If` istruzioni nidificate, le `End If` istruzioni si applicano automaticamente all'istruzione precedente più vicina `If` .</span><span class="sxs-lookup"><span data-stu-id="f2fa4-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="f2fa4-112">`Do`I cicli annidati funzionano in modo simile, con l'istruzione più interna che `Loop` corrisponde all'istruzione più interna `Do` .</span><span class="sxs-lookup"><span data-stu-id="f2fa4-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2fa4-113">Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="f2fa4-114">Ad esempio, quando si fa clic `If` in una `If...Then...Else` costruzione, vengono evidenziate tutte le istanze di `If` ,,, `Then` `ElseIf` `Else` e `End If` nella costruzione.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="f2fa4-115">Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="f2fa4-116">Annidamento di tipi diversi di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f2fa4-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="f2fa4-117">È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="f2fa4-118">Nell'esempio seguente viene utilizzato un `With` blocco all'interno di un `For Each` ciclo e blocchi annidati `If` all'interno del `With` blocco.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="f2fa4-119">Strutture di controllo sovrapposte</span><span class="sxs-lookup"><span data-stu-id="f2fa4-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="f2fa4-120">Non è possibile sovrapporre strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-120">You cannot overlap control structures.</span></span> <span data-ttu-id="f2fa4-121">Ciò significa che qualsiasi struttura annidata deve essere completamente contenuta nella successiva struttura più interna.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="f2fa4-122">La disposizione seguente, ad esempio, non è valida perché il `For` ciclo termina prima del `With` termine del blocco interno.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagramma che mostra un esempio di annidamento non valido.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="f2fa4-124">Il compilatore Visual Basic rileva tali strutture di controllo sovrapposte e segnala un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fa4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2fa4-125">See also</span></span>

- [<span data-ttu-id="f2fa4-126">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="f2fa4-126">Control Flow</span></span>](index.md)
- [<span data-ttu-id="f2fa4-127">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="f2fa4-127">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="f2fa4-128">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="f2fa4-128">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="f2fa4-129">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f2fa4-129">Other Control Structures</span></span>](other-control-structures.md)
