---
title: Direttive (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="directives-visual-basic"></a>Direttive (Visual Basic)
Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.  
  
## <a name="in-this-section"></a>In questa sezione  
 [#Const (direttiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definire una costante del compilatore  
  
 [Direttiva #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) -indica un mapping tra le righe di origine e testo esterno per l'origine  
  
 [#If... ... Then direttive #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -compilare blocchi di codice selezionati  
  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md) - comprime e nasconde sezioni di codice nell'editor di Visual Studio  
  
 **#Disable, #Enable** - disabilitano e abilitano avvisi specifici per le aree di codice.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 È anche possibile disabilitare e abilitare un elenco di codici di avviso delimitato da virgole.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)
