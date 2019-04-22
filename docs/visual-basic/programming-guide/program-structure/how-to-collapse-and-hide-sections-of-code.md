---
title: 'Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bf2a7188456097ac227039e4d902a14eb182664c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822293"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)
Il `#Region` direttiva consente di comprimere e nascondere sezioni di codice nel file di Visual Basic. Il `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere quando si usa l'editor di Visual Studio code. La possibilità di nascondere in modo selettivo il codice rende i file più gestibile e più facile da leggere. Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).  
  
 `#Region` direttive supportano la semantica di blocco di codice, ad esempio `#If...#End If`. Ciò significa che non possono iniziare in un blocco e terminare con un altro. l'inizio e fine deve essere nello stesso blocco. `#Region` direttive non sono supportate all'interno delle funzioni.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Per comprimere e nascondere una sezione di codice  
  
-   Inserire la sezione di codice tra il `#Region` e `#End Region` (istruzioni), come nell'esempio seguente:  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     Il `#Region` blocco può essere usato più volte in un file di codice, di conseguenza, gli utenti possono definire i propri blocchi di procedure e le classi che a sua volta, possono essere compressi. `#Region` blocchi possono anche essere annidati all'interno di altri `#Region` blocchi.  
  
    > [!NOTE]
    >  Nascondere il codice non impedisce che venga compilato e non influisce sul `#If...#End If` istruzioni.  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Struttura](/visualstudio/ide/outlining)
