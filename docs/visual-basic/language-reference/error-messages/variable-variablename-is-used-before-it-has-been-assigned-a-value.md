---
title: Variabile &#39; &lt;variablename&gt;&#39; viene utilizzato prima che sia stato assegnato un valore
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 201667c250e15bb9af73e64e2d8c924c1952d1be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variabile &#39; &lt;variablename&gt;&#39; viene utilizzato prima che sia stato assegnato un valore
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
