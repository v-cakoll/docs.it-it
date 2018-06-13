---
title: Variabile &#39; &lt;variablename&gt; &#39; viene utilizzato prima che sia stato assegnato un valore
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596919"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variabile &#39; &lt;variablename&gt; &#39; viene utilizzato prima che sia stato assegnato un valore
Variabile '\<variablename >' viene utilizzato prima che sia stato assegnato un valore. È possibile che in fase di esecuzione venga restituita un'eccezione dovuta a un riferimento Null.  
  
 Un'applicazione dispone di almeno un possibile percorso all'interno del codice che legge una variabile prima che venga assegnato qualsiasi valore.  
  
 Se a una variabile non è mai stato assegnato alcun valore, questa manterrà il valore predefinito per il tipo di dati. Per un tipo di dati di riferimento, il valore predefinito è [nulla](../../../visual-basic/language-reference/nothing.md). La lettura di una variabile di riferimento con un valore `Nothing` può causare un'eccezione <xref:System.NullReferenceException> in alcune circostanze.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42104  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Controllare la logica del flusso di controllo e verificare che la variabile ha un valore valido prima che il controllo passa a qualsiasi istruzione che lo legge.  
  
-   Un modo per garantire che la variabile ha sempre un valore valido è inizializzare come parte della relativa dichiarazione. Vedere "Inizializzazione" in [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Risoluzione dei problemi relativi alle variabili](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
