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
ms.openlocfilehash: c016722332dafa3d3be91a1e9e98cc0ce9a49717
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835193"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="93659-102">Strutture di controllo annidate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93659-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="93659-103">È possibile inserire le istruzioni di controllo all'interno di altre istruzioni di controllo, ad esempio un `If...Then...Else` blocchi all'interno di un `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="93659-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="93659-104">Un'istruzione di controllo posizionata all'interno di un'altra istruzione di controllo viene detto *nidificata*.</span><span class="sxs-lookup"><span data-stu-id="93659-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="93659-105">Livelli di annidamento</span><span class="sxs-lookup"><span data-stu-id="93659-105">Nesting Levels</span></span>  
 <span data-ttu-id="93659-106">Strutture di controllo in Visual Basic possono essere annidate a tutti i livelli desiderato.</span><span class="sxs-lookup"><span data-stu-id="93659-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="93659-107">È pratica comune per rendere più leggibile strutture annidate rientrando il corpo della ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="93659-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="93659-108">L'editor di sviluppo integrato (IDE) di ambiente automaticamente esegue questa operazione.</span><span class="sxs-lookup"><span data-stu-id="93659-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="93659-109">Nell'esempio seguente, la procedura `sumRows` somma tra gli elementi positivi di ogni riga della matrice.</span><span class="sxs-lookup"><span data-stu-id="93659-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="93659-110">Nell'esempio precedente, il primo `Next` istruzione chiude interna `For` ciclo e l'ultima `Next` istruzione chiude esterna `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="93659-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="93659-111">Allo stesso modo, in annidati `If` (istruzioni), il `End If` istruzioni si applicano automaticamente per il più vicino prima `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="93659-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="93659-112">Annidato `Do` cicli funzionano in modo analogo, con più interna `Loop` istruzione corrispondente più interna `Do` istruzione.</span><span class="sxs-lookup"><span data-stu-id="93659-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93659-113">Per molte strutture di controllo, quando si fa clic su una parola chiave, sono evidenziate tutte le parole chiave nella struttura.</span><span class="sxs-lookup"><span data-stu-id="93659-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="93659-114">Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione di strutture vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="93659-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="93659-115">Per spostare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.</span><span class="sxs-lookup"><span data-stu-id="93659-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="93659-116">Nidificazione di diversi tipi di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="93659-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="93659-117">È possibile annidare un tipo di struttura di controllo all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="93659-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="93659-118">L'esempio seguente usa una `With` blocchi all'interno di un `For Each` ciclo e nidificate `If` blocca all'interno del `With` blocco.</span><span class="sxs-lookup"><span data-stu-id="93659-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="93659-119">La sovrapposizione di strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="93659-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="93659-120">Non è possibile sovrapporre le strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="93659-120">You cannot overlap control structures.</span></span> <span data-ttu-id="93659-121">Ciò significa che qualsiasi struttura annidata debba essere completamente contenuta all'interno della successiva struttura più interna.</span><span class="sxs-lookup"><span data-stu-id="93659-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="93659-122">Ad esempio, la disposizione seguente non è valida perché il `For` ciclo termina prima del `With` blocco termina.</span><span class="sxs-lookup"><span data-stu-id="93659-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagramma che mostra un esempio di annidamento non valida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="93659-124">Il compilatore Visual Basic rileva le strutture di controllo sovrapposte e segnala un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="93659-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93659-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93659-125">See also</span></span>

- [<span data-ttu-id="93659-126">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="93659-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="93659-127">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="93659-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="93659-128">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="93659-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="93659-129">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="93659-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
