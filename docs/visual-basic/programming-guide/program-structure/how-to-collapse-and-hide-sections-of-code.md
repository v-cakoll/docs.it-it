---
title: 'Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 4f11982cc0aa7654c1e456fb15d918a68bc4791b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054111"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Procedura: Comprimere e nascondere sezioni di codice (Visual Basic)

La `#Region` direttiva consente di comprimere e nascondere sezioni di codice in file di Visual Basic. La `#Region` direttiva consente di specificare un blocco di codice che è possibile espandere o comprimere quando si usa l'editor di codice di Visual Studio. La possibilità di nascondere il codice rende i file più gestibili e più facili da leggere. Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).

`#Region`le direttive supportano la semantica del blocco `#If...#End If`di codice, ad esempio. Ciò significa che non possono iniziare in un blocco e terminare con un altro; l'inizio e la fine devono trovarsi nello stesso blocco. `#Region`le direttive non sono supportate all'interno di funzioni.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Per comprimere e nascondere una sezione di codice

Inserire la sezione di codice tra le `#Region` istruzioni `#End Region` e, come nell'esempio seguente:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Il `#Region` blocco può essere utilizzato più volte in un file di codice; pertanto, gli utenti possono definire blocchi di routine e classi che possono, a loro volta, essere compressi. `#Region`i blocchi possono anche essere annidati `#Region` all'interno di altri blocchi.

> [!NOTE]
> Il codice nascosto non ne impedisce la compilazione e non influisce sulle `#If...#End If` istruzioni.

## <a name="see-also"></a>Vedere anche

- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Struttura](/visualstudio/ide/outlining)
