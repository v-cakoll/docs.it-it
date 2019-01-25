---
title: Introduzione ai controlli Line e Shape (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3623c2363f39150fd4bb202ba61ebd51df383ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699922"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Introduzione ai controlli Line e Shape (Visual Studio)
I controlli Visual Basic Power Packs Line e Shape sono un set di tre controlli grafici che consentono di tracciare linee e forme su form e contenitori. Il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo viene usato per disegnare linee orizzontali, verticali e diagonali. Il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> utilizzato per disegnare cerchi e ovali, controllo e il <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controllo utilizzato per disegnare rettangoli e quadrati.  
  
## <a name="line-and-shape-controls"></a>Controlli Line e Shape  
 Controlli Line e Shape incapsulano molti dei metodi grafici che sono contenuti nel <xref:System.Drawing> dello spazio dei nomi. Ciò consente di tracciare linee e forme in un unico passaggio senza la necessità di creare oggetti grafici, penne e pennelli. Sono possibile tecniche grafiche complesse, ad esempio riempimenti sfumati, semplicemente impostando alcune proprietà.  
  
 Sebbene sia anche possibile disegnare linee e forme con i metodi grafici, sono disponibili tramite i controlli Line e Shape presenta diversi vantaggi:  
  
-   I metodi grafici possono essere chiamati solo in fase di esecuzione. Controlli Line e Shape possono essere aggiunti a un form in fase di progettazione. Ciò consente di visualizzare l'aspetto e di posizionarli esattamente; possono anche essere aggiunti in fase di esecuzione.  
  
-   Controlli Line e Shape possono sono selezionabili in fase di esecuzione, fornendo ad esempio gli eventi <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> e <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. L'output dei metodi grafici non sono selezionabili e non forniscono eventi.  
  
-   Controlli Line e Shape forniscono <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> e <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> metodi che consentono di controllare l'ordine z in fase di progettazione e in fase di esecuzione. L'ordine z dei metodi grafici può essere controllata solo modificandone l'ordine di esecuzione in fase di esecuzione.  
  
-   Controlli Line e Shape sono controlli privi di finestra; non hanno alcun handle di finestra e pertanto usano meno risorse di sistema.  
  
### <a name="object-model"></a>Modello a oggetti  
 Controlli Line e Shape derivano da una base <xref:Microsoft.VisualBasic.PowerPacks.Shape> classe che definisce le proprietà condivise, metodi ed eventi.  
  
 La figura seguente mostra la gerarchia di oggetti Line e Shape.  
  
 ![Un diagramma della gerarchia di oggetti Line e Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Gerarchia di oggetti Line e Shape  
  
 Derivata <xref:Microsoft.VisualBasic.PowerPacks.LineShape> classe contiene proprietà, metodi ed eventi che sono univoci per le righe. Il derivato <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> classe è la classe base per <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; contiene proprietà, metodi ed eventi comuni a tutte le forme. È anche possibile derivare da <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> per crearne una propria `Shape` controlli.  
  
 Il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> classi possono essere utilizzate per disegnare rettangoli con angoli arrotondati, ellissi, rettangoli e cerchi.  
  
 Quando un controllo Line o Shape viene aggiunto a un form o contenitore, un invisibile <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> oggetto viene creato. Il <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> funge da un'area di disegno delle forme all'interno di ogni controllo contenitore, ognuna delle quali <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> sia presente un <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> che consente di scorrere i controlli Line e Shape. È possibile spostare le forme da un contenitore a un altro utilizzando le operazioni Taglia e Incolla o trascinamento della selezione. Quando l'ultima forma viene rimosso da un contenitore, il <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> viene rimosso anche.  
  
> [!NOTE]
>  Non tutti i controlli contenitore supportano i controlli Line e Shape. Non è possibile ospitare un controllo Line o Shape in una <xref:System.Windows.Forms.TableLayoutPanel> o un <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks>
- [Procedura: Disegnare linee con il controllo LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Procedura: Disegnare forme con i controlli OvalShape e RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Procedura: Abilitare la tabulazione tra forme](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
