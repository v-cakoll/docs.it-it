---
title: 'Procedura: comprimere e nascondere sezioni di codice'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347401"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Procedura: comprimere e nascondere sezioni di codice (Visual Basic)

La direttiva `#Region` consente di comprimere e nascondere sezioni di codice in file di Visual Basic. La direttiva `#Region` consente di specificare un blocco di codice che è possibile espandere o comprimere quando si usa l'editor di codice di Visual Studio. La possibilità di nascondere il codice rende i file più gestibili e più facili da leggere. Per altre informazioni, vedere [Struttura](/visualstudio/ide/outlining).

le direttive `#Region` supportano la semantica del blocco di codice, ad esempio `#If...#End If`. Ciò significa che non possono iniziare in un blocco e terminare con un altro; l'inizio e la fine devono trovarsi nello stesso blocco. le direttive `#Region` non sono supportate all'interno di funzioni.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Per comprimere e nascondere una sezione di codice

Inserire la sezione di codice tra le istruzioni `#Region` e `#End Region`, come nell'esempio seguente:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Il blocco `#Region` può essere utilizzato più volte in un file di codice. di conseguenza, gli utenti possono definire blocchi di routine e classi che possono, a loro volta, essere compressi. i blocchi di `#Region` possono anche essere annidati all'interno di altri blocchi di `#Region`.

> [!NOTE]
> Il codice nascosto non ne impedisce la compilazione e non influisce sulle istruzioni `#If...#End If`.

## <a name="see-also"></a>Vedere anche

- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Struttura](/visualstudio/ide/outlining)
