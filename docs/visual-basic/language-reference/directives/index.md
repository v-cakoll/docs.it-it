---
title: Direttive
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838143"
---
# <a name="directives-visual-basic"></a>Direttive (Visual Basic)

Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.  
  
## <a name="in-this-section"></a>Contenuto della sezione  

 [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md) --definire una costante del compilatore  
  
 [Direttiva #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) : indicare un mapping tra le righe di origine e il testo esterno all'origine  
  
 [#If... Direttive then... #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compila i blocchi di codice selezionati  
  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md) : comprimere e nascondere sezioni di codice nell'editor di Visual Studio  
  
 **#Disable, #Enable** disabilitare e abilitare avvisi specifici per le aree di codice.  
  
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
  