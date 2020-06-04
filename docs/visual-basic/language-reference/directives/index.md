---
title: Direttive
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409998"
---
# <a name="directives-visual-basic"></a>Direttive (Visual Basic)

Gli argomenti in questa sezione descrivono le direttive del compilatore del codice sorgente di Visual Basic.  
  
## <a name="in-this-section"></a>Contenuto della sezione  

 [Direttiva #Const](const-directive.md) --definire una costante del compilatore  
  
 [Direttiva #ExternalSource](externalsource-directive.md) : indicare un mapping tra le righe di origine e il testo esterno all'origine  
  
 [#If... Direttive then... #Else](if-then-else-directives.md) : compila i blocchi di codice selezionati  
  
 [Direttiva #Region](region-directive.md) : comprimere e nascondere sezioni di codice nell'editor di Visual Studio  
  
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

 [Riferimenti al linguaggio Visual Basic](../index.md)  
  