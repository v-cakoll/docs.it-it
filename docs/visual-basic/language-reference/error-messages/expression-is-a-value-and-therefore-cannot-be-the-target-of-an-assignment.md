---
title: L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: dd5618bd0533f885a6aef8229b2d8cb1bc34c237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590238"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
Un'istruzione tenta di assegnare un valore a un'espressione. È possibile assegnare un valore solo a una variabile scrivibile, una proprietà o un elemento della matrice in fase di esecuzione. Nell'esempio seguente viene illustrato come questo errore può verificarsi.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Esempi simili possibile applicare alle proprietà e gli elementi della matrice.  
  
 **Accesso indiretto.** Accesso indiretto attraverso un tipo di valore può inoltre generare questo errore. Si consideri l'esempio di codice riportato di seguito, che tenta di impostare il valore di <xref:System.Drawing.Point> accedendovi indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 L'ultima istruzione dell'esempio precedente ha esito negativo poiché crea solo un'allocazione temporanea per il <xref:System.Drawing.Point> restituito dalla struttura di <xref:System.Windows.Forms.Control.Location%2A> proprietà. Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'istruzione viene eseguita. Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A>, che consente di creare un'allocazione più permanente per la <xref:System.Drawing.Point> struttura. Nell'esempio seguente viene illustrato il codice che è possibile sostituire l'ultima istruzione dell'esempio precedente.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **ID errore:** BC30068  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se l'istruzione assegna un valore a un'espressione, è possibile sostituire l'espressione a una singola variabile scrivibile, una proprietà o un elemento della matrice.  
  
-   Se l'istruzione effettua l'accesso indiretto attraverso un tipo di valore (in genere una struttura), creare una variabile per contenere il tipo di valore.  
  
-   Assegnare la struttura appropriata (o altro tipo di valore) alla variabile.  
  
-   Utilizzare la variabile per accedere alla proprietà per assegnare un valore.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
