---
title: L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826133"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
Un'istruzione prova ad assegnare un valore a un'espressione. È possibile assegnare un valore solo a una variabile scrivibile, una proprietà o un elemento della matrice in fase di esecuzione. Nell'esempio seguente viene illustrato come questo errore può verificarsi.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Esempi simili è stato possibile applicare alle proprietà e gli elementi della matrice.  
  
 **Accesso indiretto.** Accesso indiretto tramite un tipo di valore può anche generare questo errore. Si consideri l'esempio di codice riportato di seguito, che tenta di impostare il valore della <xref:System.Drawing.Point> accedendovi indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 L'ultima istruzione dell'esempio precedente ha esito negativo perché crea solo un'allocazione temporanea per il <xref:System.Drawing.Point> struttura restituita dal <xref:System.Windows.Forms.Control.Location%2A> proprietà. Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'esecuzione dell'istruzione. Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A>, che crea un'allocazione di più permanente per il <xref:System.Drawing.Point> struttura. Nell'esempio seguente viene illustrato il codice che è possibile sostituire l'ultima istruzione dell'esempio precedente.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **ID errore:** BC30068  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se l'istruzione viene assegnato un valore a un'espressione, sostituire l'espressione con una singola variabile scrivibile, proprietà o elemento di matrice.  
  
-   Se l'istruzione effettua l'accesso indiretto tramite un tipo di valore (in genere una struttura), creare una variabile per contenere il tipo di valore.  
  
-   Assegnare la struttura appropriata (o altro tipo di valore) alla variabile.  
  
-   Usare la variabile per accedere alla proprietà per assegnare un valore.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
- [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
