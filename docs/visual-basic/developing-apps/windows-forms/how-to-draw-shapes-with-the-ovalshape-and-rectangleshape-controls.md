---
title: 'Procedura: disegnare forme con i controlli OvalShape e RectangleShape (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53d91d10cc4735bbae521d17d05045cc7ea75fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>Procedura: disegnare forme con i controlli OvalShape e RectangleShape (Visual Studio)
Il controllo <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> consente di disegnare cerchi e ovali in un form o in un contenitore, sia in fase di progettazione che in fase di esecuzione. Il controllo <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> può essere usato per disegnare quadrati, rettangoli o rettangoli con angoli arrotondati in un form o in un contenitore. Anche questo controllo può essere usato sia in fase di progettazione che in fase di esecuzione.  
  
 È possibile personalizzare l'aspetto delle forme modificandone la larghezza, il colore e lo stile del bordo. Lo sfondo di una forma è trasparente per impostazione predefinita. È possibile personalizzare lo sfondo per visualizzare un colore a tinta unita, un motivo, un riempimento sfumato (una transizione da un colore a altro) o un'immagine.  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>Per disegnare una forma semplice in fase di progettazione  
  
1.  Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> o <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controllo il **Visual Basic Power Packs** scheda (per l'installazione, vedere [controlli di Visual Basic Power Pack](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) nel **della casella degli strumenti** per un controllo form o del contenitore.  
  
2.  Trascinare i quadratini di ridimensionamento e di spostamento per impostare le dimensioni e la posizione della forma.  
  
     È anche possibile ridimensionare e posizionare la forma modificando il `Size` e `Position` le proprietà di **proprietà** finestra.  
  
     Per creare un rettangolo con angoli arrotondati, selezionare il `CornerRadius` proprietà il **proprietà** finestra e impostarlo su un valore maggiore di 0.  
  
3.  Nel **proprietà** finestra, facoltativamente, impostare proprietà facoltative aggiuntive per modificare l'aspetto della forma.  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>Per disegnare una forma semplice in fase di esecuzione  
  
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
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>Personalizzazione di forme  
 Quando si usano le impostazioni predefinite, i controlli <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> vengono visualizzati con un bordo nero continuo largo un pixel e uno sfondo trasparente. Specifiche proprietà consentono di modificare la larghezza, lo stile e il colore del bordo. Proprietà aggiuntive consentono di impostare lo sfondo delle forme su una tinta unita, un motivo, un riempimento sfumato o un'immagine.  
  
 Prima di modificare lo sfondo di una forma, è necessario conoscere l'interazione di diverse proprietà.  
  
-   L'impostazione della proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> ha effetto solo se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> esegue l'override di <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.  
  
-   Se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> è impostata su un valore di motivo quale <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> o <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, il motivo viene visualizzato in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>. Lo sfondo viene visualizzato in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Per visualizzare un riempimento sfumato, impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> su <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> e la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> su un valore diverso da <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.  
  
-   L'impostazione della proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> su un'immagine comporta l'override di tutte le altre impostazioni dello sfondo.  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>Per disegnare un cerchio con un bordo personalizzato  
  
1.  Trascinare il `OvalShape` controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Nel **proprietà** finestra, nel `Size` impostata, `Height` e `Width` su valori uguali.  
  
3.  Impostare la proprietà `BorderColor` sul colore desiderato.  
  
4.  Impostare la proprietà `BorderStyle` su qualsiasi valore diverso da `Solid`.  
  
5.  Impostare la proprietà `BorderWidth` sulle dimensioni in pixel desiderate.  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>Per disegnare un cerchio con un riempimento a tinta unita  
  
1.  Trascinare il `OvalShape` controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Nel **proprietà** finestra, nel `Size` impostata, `Height` e `Width` su valori uguali.  
  
3.  Impostare la proprietà `BackColor` sul colore desiderato.  
  
4.  Impostare la proprietà `BackStyle` su `Opaque`.  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>Per disegnare un cerchio con un motivo di riempimento  
  
1.  Trascinare il `OvalShape` controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Nel **proprietà** finestra, nel `Size` impostata, `Height` e `Width` su valori uguali.  
  
3.  Impostare la proprietà `BackColor` sul colore di sfondo desiderato.  
  
4.  Impostare la proprietà `BackStyle` su `Opaque`.  
  
5.  Impostare la proprietà `FillColor` sul colore del motivo desiderato.  
  
6.  Impostare la proprietà `FillStyle` su qualsiasi valore diverso da `Transparent` o `Solid`.  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>Per disegnare un cerchio con un riempimento sfumato  
  
1.  Trascinare il `OvalShape` controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Nel **proprietà** finestra, nel `Size` impostata, `Height` e `Width` su valori uguali.  
  
3.  Impostare la proprietà `FillColor` sul colore iniziale desiderato.  
  
4.  Impostare la proprietà `FillGradientColor` sul colore finale desiderato.  
  
5.  Impostare la proprietà `FillGradientStyle` su un valore diverso da `None`.  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>Per disegnare un cerchio con un'immagine di riempimento  
  
1.  Trascinare il `OvalShape` controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.  
  
2.  Nel **proprietà** finestra, nel `Size` impostata, `Height` e `Width` su valori uguali.  
  
3.  Selezionare il `BackgroundImage` proprietà e fare clic su di **i puntini di sospensione** pulsante (…).  
  
4.  Nel **Seleziona risorsa** la finestra di dialogo, selezionare un'immagine da visualizzare. Se non è elencato alcuna risorsa immagine, fare clic su **importazione** per passare al percorso di un'immagine.  
  
5.  Fare clic su **OK** per inserire l'immagine.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [Introduzione ai controlli Line e Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Procedura: Disegnare linee con il controllo LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
