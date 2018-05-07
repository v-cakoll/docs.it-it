---
title: 'Procedura: disegnare linee con il controllo LineShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Procedura: disegnare linee con il controllo LineShape (Visual Studio)
È possibile utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo in cui disegnare linee orizzontali, verticale o diagonale su un form o un contenitore, in fase di progettazione e in fase di esecuzione.  
  
 **Nota** computer potrebbero essere diversi nomi o percorsi visualizzati per alcuni utente di Visual Studio gli elementi dell'interfaccia nelle istruzioni seguenti. La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi. Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-line-at-design-time"></a>Disegnare una riga in fase di progettazione  
  
1.  Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** trascinare un controllo form o del contenitore.  
  
2.  Trascinare le dimensioni e gli handle per ridimensionare e posizionare la riga di spostamento.  
  
     È possibile ridimensionare e posizionare la riga tramite la modifica anche il `X1`, `X2`, `Y1`, e `Y2` le proprietà di **proprietà** finestra.  
  
3.  Nel **proprietà** finestra, facoltativamente, impostare proprietà aggiuntive, ad esempio `BorderStyle` o `BorderColor` per modificare l'aspetto della riga.  
  
### <a name="to-draw-a-line-at-run-time"></a>Disegnare una riga in fase di esecuzione  
  
1.  Scegliere **Aggiungi riferimento** dal menu **Progetto**.  
  
2.  Nel **Aggiungi riferimento** nella finestra di dialogo **Microsoft.VisualBasic.PowerPacks.VS**, quindi fare clic su **OK**.  
  
3.  Nel **Editor di codice**, aggiungere un `Imports` o `using` istruzione nella parte superiore del modulo:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Nella routine `Event` aggiungere il codice seguente:  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [Introduzione ai controlli Line e Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Procedura: Disegnare forme con i controlli OvalShape e RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
