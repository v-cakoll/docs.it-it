---
title: La variabile '<variablename>' viene utilizzata prima che le sia stato assegnato un valore
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 34718243172d3b1a238a813268e672d62c4eeb6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406534"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>La variabile '\<variablename>' viene utilizzata prima che le sia stato assegnato un valore
La variabile ' \<variablename> ' viene usata prima dell'assegnazione di un valore. È possibile che in fase di esecuzione venga restituita un'eccezione dovuta a un riferimento Null.  
  
 Un'applicazione ha almeno un possibile percorso attraverso il codice che legge una variabile prima che venga assegnato un qualsiasi valore.  
  
 Se a una variabile non è mai stato assegnato alcun valore, questa manterrà il valore predefinito per il tipo di dati. Per un tipo di dati di riferimento, il valore predefinito è [Nothing](../nothing.md). La lettura di una variabile di riferimento con un valore `Nothing` può causare un'eccezione <xref:System.NullReferenceException> in alcune circostanze.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42104  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Controllare la logica del flusso di controllo e verificare che la variabile abbia un valore valido prima che il controllo passi a qualsiasi istruzione che la legga.  
  
- Un modo per garantire che la variabile abbia sempre un valore valido consiste nell'inizializzarla come parte della relativa dichiarazione. Vedere "inizializzazione" nell' [istruzione Dim](../statements/dim-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../statements/dim-statement.md)
- [Dichiarazione di variabile](../../programming-guide/language-features/variables/variable-declaration.md)
- [Risoluzione dei problemi relativi alle variabili](../../programming-guide/language-features/variables/troubleshooting-variables.md)
