---
title: Introduzione ai controlli Line e Shape (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3ad740f7dd15194830959a5493970b4ba54ce142
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Introduzione ai controlli Line e Shape (Visual Studio)
I controlli Visual Basic Power Pack Line e Shape sono un set di tre controlli grafici che consentono di disegnare linee e forme su form e i contenitori. Il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo viene utilizzato per disegnare linee orizzontali, verticali e diagonali. Il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> controllo viene utilizzato per disegnare cerchi e ovali e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controllo viene utilizzato per disegnare rettangoli e quadrati.  
  
## <a name="line-and-shape-controls"></a>Controlli Line e Shape  
 Controlli Line e Shape incapsulano molti dei metodi contenuti in grafici di <xref:System.Drawing> dello spazio dei nomi. Ciò consente di disegnare linee e forme in un unico passaggio, senza dover creare pennelli, penne e oggetti di grafica. Tecniche di grafici complessi, ad esempio riempimenti possono essere eseguite impostando solo alcune proprietà.  
  
 Benché sia anche possibile disegnare linee e forme utilizzando metodi grafici, sono disponibili tramite i controlli Line e Shape offre numerosi vantaggi:  
  
-   Metodi grafici possono essere chiamati solo in fase di esecuzione. Controlli Line e Shape possono essere aggiunto a un form in fase di progettazione. Ciò consente di visualizzare l'aspetto e di posizionarli correttamente. possono inoltre essere aggiunti in fase di esecuzione.  
  
-   Controlli Line e Shape possono essere selezionati in fase di esecuzione forniscono gli eventi, ad esempio <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> e <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. L'output dei metodi grafici non sono selezionabili e non forniscono eventi.  
  
-   Controlli Line e Shape forniscono <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> e <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> metodi che consentono di controllare l'ordine z in fase di progettazione e in fase di esecuzione. È possibile controllare l'ordine z di metodi grafici solo modificandone l'ordine di esecuzione in fase di esecuzione.  
  
-   Controlli Line e Shape sono i controlli privi di finestra. che non dispone di alcun handle di finestra e quindi usare meno risorse di sistema.  
  
### <a name="object-model"></a>Modello a oggetti  
 Controlli Line e Shape derivano da una base <xref:Microsoft.VisualBasic.PowerPacks.Shape> classe che definisce le proprietà, metodi ed eventi.  
  
 Nella figura seguente illustra la gerarchia di oggetti Line e Shape.  
  
 ![Un diagramma della gerarchia di oggetti Line e Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Gerarchia di oggetti Line e Shape  
  
 Derivata <xref:Microsoft.VisualBasic.PowerPacks.LineShape> classe contiene proprietà, metodi ed eventi che sono univoci per le righe. Derivata <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> classe è la classe base per <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; contiene proprietà, metodi ed eventi comuni a tutte le forme. È anche possibile derivare da <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> per creare la propria `Shape` controlli.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> classi possono essere utilizzate per disegnare cerchi, ovali, rettangoli e rettangoli con angoli arrotondati.  
  
 Quando un controllo Line o Shape viene aggiunto a un form o contenitore, un invisibile <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> viene creato l'oggetto. Il <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> funge da un'area di disegno per le forme all'interno di ogni controllo contenitore; ogni <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> dispone di un corrispondente <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> che consente di scorrere i controlli Line e Shape. È possibile spostare le forme da un contenitore a un altro utilizzando Taglia e Incolla o trascinamento della selezione. Quando l'ultima forma viene rimosso da un contenitore, il <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> viene rimosso anche.  
  
> [!NOTE]
>  Non tutti i controlli contenitore supportano i controlli Line e Shape. Non è possibile ospitare un controllo Line o Shape in un <xref:System.Windows.Forms.TableLayoutPanel> o <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [Procedura: Disegnare linee con il controllo LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Procedura: Disegnare forme con i controlli OvalShape e RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Procedura: Abilitare la tabulazione tra forme](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
