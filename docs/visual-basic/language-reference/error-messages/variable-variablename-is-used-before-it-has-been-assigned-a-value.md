---
title: La variabile '<variablename>' viene utilizzata prima che le sia stato assegnato un valore
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 46551a917aeb794c8d35985076b67a315386f628
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819359"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>Variabile '\<nomevariabile >' viene usato prima che sia stato assegnato un valore
Variabile '\<nomevariabile >' viene usato prima che sia stato assegnato un valore. È possibile che in fase di esecuzione venga restituita un'eccezione dovuta a un riferimento Null.  
  
 Un'applicazione ha almeno un possibile percorso all'interno del codice che legge una variabile prima che venga assegnato un valore qualsiasi.  
  
 Se a una variabile non è mai stato assegnato alcun valore, questa manterrà il valore predefinito per il tipo di dati. Per un tipo di dati di riferimento, il valore predefinito è [Nothing](../../../visual-basic/language-reference/nothing.md). La lettura di una variabile di riferimento con un valore `Nothing` può causare un'eccezione <xref:System.NullReferenceException> in alcune circostanze.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42104  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Controllare la logica del flusso di controllo e assicurarsi che la variabile ha un valore valido prima che il controllo passa a qualsiasi istruzione che li legge.  
  
-   Un modo per garantire che la variabile ha sempre un valore valido consiste nell'inizializzare come parte della relativa dichiarazione. Vedere "Inizializzazione" nella [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Risoluzione dei problemi relativi alle variabili](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
