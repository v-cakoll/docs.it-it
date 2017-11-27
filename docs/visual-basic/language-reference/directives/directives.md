---
title: Direttive (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a>Direttive (Visual Basic)
Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [#Const (direttiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definire una costante del compilatore  
  
 [Direttiva #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) -indica un mapping tra righe di codice sorgente e testo esterno per l'origine  
  
 [#If... ... Then direttive #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -compilare i blocchi di codice selezionati  
  
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
