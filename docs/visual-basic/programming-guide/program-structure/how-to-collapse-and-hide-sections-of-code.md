---
title: 'Procedura: comprimere e nascondere sezioni di codice (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: f6c272b7ac016258d99873512cb789bba6739727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650855"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Procedura: comprimere e nascondere sezioni di codice (Visual Basic)
Il `#Region` direttiva consente di comprimere e nascondere sezioni di codice nel file di Visual Basic. Il `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere quando si utilizza l'editor di codice di Visual Studio. La possibilità di nascondere in modo selettivo il codice rende i file più gestibile e più facile da leggere. Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).  
  
 `#Region` direttive supportano la semantica di blocco di codice, ad esempio `#If...#End If`. Ciò significa che non possono iniziare in un blocco e terminare con un altro. inizio e fine deve essere nello stesso blocco. `#Region` le direttive non sono supportate all'interno delle funzioni.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Per comprimere e nascondere una sezione di codice  
  
-   Inserire la sezione di codice tra le `#Region` e `#End Region` istruzioni, come nell'esempio seguente:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     Il `#Region` blocco può essere utilizzato più volte in un file di codice; pertanto, gli utenti possono definire i propri blocchi di routine e le classi che a sua volta, possono essere compressi. `#Region` blocchi possono anche essere annidati all'interno di altri `#Region` blocchi.  
  
    > [!NOTE]
    >  Nascondere il codice non impedisce che venga compilato e non influisce sulla `#If...#End If` istruzioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Struttura](/visualstudio/ide/outlining)
