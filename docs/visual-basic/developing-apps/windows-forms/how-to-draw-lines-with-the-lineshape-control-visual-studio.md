---
title: 'Procedura: Disegnare linee con il controllo LineShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596228"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Procedura: Disegnare linee con il controllo LineShape (Visual Studio)
È possibile usare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo per disegnare linee orizzontale, verticale o diagonale in un form o un contenitore, in fase di progettazione sia in fase di esecuzione.  
  
 **Nota** computer potrebbe mostrare diversi nomi o percorsi di alcuni utente di Visual Studio gli elementi dell'interfaccia nelle istruzioni seguenti. La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi. Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-line-at-design-time"></a>Per disegnare una linea in fase di progettazione  
  
1.  Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** trascinare in un form o un controllo contenitore.  
  
2.  Trascinare il dimensionamento e gli handle per ridimensionare e posizionare la riga di spostamento.  
  
     È anche possibile ridimensionare e posizionare la riga modificando la `X1`, `X2`, `Y1`, e `Y2` le proprietà nel **proprietà** finestra.  
  
3.  Nel **delle proprietà** finestra, se lo si desidera impostare proprietà aggiuntive, ad esempio `BorderStyle` o `BorderColor` per modificare l'aspetto della riga.  
  
### <a name="to-draw-a-line-at-run-time"></a>Per disegnare una linea in fase di esecuzione  
  
1.  Scegliere **Aggiungi riferimento** dal menu **Progetto**.  
  
2.  Nel **Aggiungi riferimento** finestra di dialogo **Microsoft.VisualBasic.PowerPacks.VS**, quindi fare clic su **OK**.  
  
3.  Nel **Editor di codice**, aggiungere un' `Imports` o `using` informativa nella parte superiore del modulo:  
  
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
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [Introduzione ai controlli Line e Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [Procedura: Disegnare forme con i controlli OvalShape e RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
