---
title: Comportamento del controllo Popup in relazione al posizionamento
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951726"
---
# <a name="popup-placement-behavior"></a>Comportamento del controllo Popup in relazione al posizionamento
Un <xref:System.Windows.Controls.Primitives.Popup> controllo Visualizza il contenuto in una finestra separata che è mobile su un'applicazione. È possibile specificare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> oggetto rispetto a un controllo, al mouse o alla schermata usando le <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>proprietà, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> .  Queste proprietà interagiscono per offrire la flessibilità necessaria per specificare la posizione di <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Le <xref:System.Windows.Controls.ToolTip> classi <xref:System.Windows.Controls.ContextMenu> e definiscono anche queste cinque proprietà e si comportano in modo simile.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Posizionamento del controllo Popup  
 La posizione di un <xref:System.Windows.Controls.Primitives.Popup> oggetto può essere relativa a <xref:System.Windows.UIElement> un oggetto o all'intero schermo.  Nell'esempio seguente vengono creati <xref:System.Windows.Controls.Primitives.Popup> quattro controlli relativi a un oggetto <xref:System.Windows.UIElement>, in questo caso un'immagine. Per tutti i <xref:System.Windows.Controls.Primitives.Popup> controlli <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> la proprietà è impostata su `image1`, ma ognuna <xref:System.Windows.Controls.Primitives.Popup> presenta un valore diverso per la proprietà Placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 La figura seguente illustra l'immagine e i <xref:System.Windows.Controls.Primitives.Popup> controlli  
  
 ![Immagine con quattro controlli popup](./media/popup-placement-behavior/popup-placement-intro.png "Immagine con quattro popup")    
  
 Questo semplice esempio illustra come impostare le <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> proprietà e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , ma usando le <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>proprietà, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> , si ha un maggiore controllo sulla posizione in cui è posizionato.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definizioni dei termini: Anatomia di un popup  
 I termini seguenti sono utili per comprendere il modo <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>in <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>cui <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>le proprietà, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> ,, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>e sono correlate tra loro <xref:System.Windows.Controls.Primitives.Popup>e:  
  
- Oggetto destinazione  
  
- Area di destinazione  
  
- Origine di destinazione  
  
- Punto di allineamento del controllo Popup  
  
 Questi termini costituiscono un modo pratico per fare riferimento a diversi aspetti di <xref:System.Windows.Controls.Primitives.Popup> e al controllo a cui è associato.  
  
### <a name="target-object"></a>Oggetto di destinazione  
 L' *oggetto di destinazione* è l'elemento a <xref:System.Windows.Controls.Primitives.Popup> cui è associato. Se la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> proprietà è impostata, viene specificato l'oggetto di destinazione.  Se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> non è impostato <xref:System.Windows.Controls.Primitives.Popup> e ha un padre, l'elemento padre è l'oggetto di destinazione.  Se non è <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> presente alcun valore e nessun elemento padre, non è presente alcun oggetto di <xref:System.Windows.Controls.Primitives.Popup> destinazione e l'oggetto viene posizionato in relazione allo schermo.  
  
 Nell'esempio seguente viene creato <xref:System.Windows.Controls.Primitives.Popup> un oggetto che è l'elemento <xref:System.Windows.Controls.Canvas>figlio di un oggetto.  Nell'esempio non viene impostata la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> proprietà nell'oggetto <xref:System.Windows.Controls.Primitives.Popup>. Il valore predefinito per <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType> <xref:System.Windows.Controls.Primitives.Popup> ,<xref:System.Windows.Controls.Canvas>quindi viene visualizzato sotto.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Nella figura seguente viene illustrato che <xref:System.Windows.Controls.Primitives.Popup> l'oggetto è posizionato in <xref:System.Windows.Controls.Canvas>relazione all'oggetto.  
  
 ![Controllo popup senza PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup senza PlacementTarget.")  

 Nell'esempio seguente viene creato <xref:System.Windows.Controls.Primitives.Popup> un oggetto che è l'elemento <xref:System.Windows.Controls.Canvas>figlio di un oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> , ma questa volta `ellipse1`è impostato <xref:System.Windows.Shapes.Ellipse>su, quindi la finestra popup viene visualizzata sotto.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Nella figura seguente viene illustrato che <xref:System.Windows.Controls.Primitives.Popup> l'oggetto è posizionato in <xref:System.Windows.Shapes.Ellipse>relazione all'oggetto.  
  
 ![Popup posizionato in relazione a un'ellisse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup con PlacementTarget")    
  
> [!NOTE]
> Per <xref:System.Windows.Controls.ToolTip>, il valore predefinito di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Per <xref:System.Windows.Controls.ContextMenu>, il valore predefinito di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Questi valori vengono descritti più avanti nella sezione "Modalità di interazione delle proprietà".  
  
### <a name="target-area"></a>Area di destinazione  
 L' *area di destinazione* è l'area sullo schermo a cui <xref:System.Windows.Controls.Primitives.Popup> è relativo. Negli esempi precedenti, <xref:System.Windows.Controls.Primitives.Popup> è allineato con i limiti dell'oggetto di destinazione, ma in alcuni casi <xref:System.Windows.Controls.Primitives.Popup> è allineato ad altri limiti, anche se <xref:System.Windows.Controls.Primitives.Popup> dispone di un oggetto di destinazione.  Se la <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> proprietà è impostata, l'area di destinazione è diversa dai limiti dell'oggetto di destinazione.  
  
 Nell'esempio seguente vengono creati <xref:System.Windows.Controls.Canvas> due oggetti, ognuno dei quali <xref:System.Windows.Shapes.Rectangle> contiene un <xref:System.Windows.Controls.Primitives.Popup>oggetto e un oggetto.  In entrambi i casi, l'oggetto di destinazione <xref:System.Windows.Controls.Primitives.Popup> per <xref:System.Windows.Controls.Canvas>è. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Rect.Width%2A> Nelprimo<xref:System.Windows.Rect.Height%2A> è impostato il set, <xref:System.Windows.Rect.Y%2A>con le proprietà ,,eimpostaterispettivamentesu50,50,50e100.<xref:System.Windows.Rect.X%2A> <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Primitives.Popup> Nel secondo <xref:System.Windows.Controls.Canvas> non è impostato il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> set. <xref:System.Windows.Controls.Primitives.Popup>  Di conseguenza, il <xref:System.Windows.Controls.Primitives.Popup> primo è posizionato al di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> sotto di e il <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>secondo è posizionato sotto. Ogni <xref:System.Windows.Controls.Canvas> contiene anche un <xref:System.Windows.Shapes.Rectangle> oggetto con gli <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> stessi limiti di per la prima <xref:System.Windows.Controls.Primitives.Popup>.  Si noti che <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> non crea un elemento visibile nell'applicazione. nell'esempio viene creato un oggetto <xref:System.Windows.Shapes.Rectangle> per rappresentare <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Popup con e senza PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con e senza PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origine di destinazione e punto di allineamento del controllo Popup  
 L'*origine di destinazione* e il *punto di allineamento del controllo Popup* sono punti di riferimento, rispettivamente sull'area di destinazione e sul popup, usati per il posizionamento. È possibile usare le <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> proprietà <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> e per compensare il popup dall'area di destinazione.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> E<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sono relativi all'origine di destinazione e al punto di allineamento del popup. Il valore della <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà determina la posizione in cui si trovano l'origine di destinazione e il punto di allineamento del popup.  
  
 Nell'esempio seguente viene creato <xref:System.Windows.Controls.Primitives.Popup> un oggetto e <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> le <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà e vengono impostate su 20.  La <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (impostazione predefinita), quindi l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Posizionamento popup con punto di allineamento origine destinazione](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset e VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Modalità di interazione delle proprietà  
 I valori di <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> devono essere considerati insieme per individuare l'area di destinazione, l'origine di destinazione e il punto di allineamento del popup corretti.  Se, ad esempio, il valore <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> di <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>è, non è presente <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> alcun oggetto di destinazione, viene ignorato e l'area di destinazione è il limite del puntatore del mouse. D'altra parte, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> se è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, l' <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> elemento padre di o determina l'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione e determina l'area di destinazione.  
  
 Nella tabella seguente vengono descritti l'oggetto di destinazione, l'area di destinazione, l'origine di destinazione e il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> punto <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> di allineamento del popup <xref:System.Windows.Controls.Primitives.PlacementMode> e viene indicato se e vengono utilizzati per ogni valore di enumerazione.  
  
|PlacementMode|Oggetto destinazione|Area di destinazione|Origine di destinazione|Punto di allineamento del controllo Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>viene ignorato.|Schermata o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>viene ignorato.|Schermata o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo inferiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Centro dell'area di destinazione.|Centro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Definito da <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definito da <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore destro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>viene ignorato.|Angolo inferiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>viene ignorato.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo superiore destro dell'area di destinazione.|Angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> È relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Le illustrazioni seguenti mostrano l' <xref:System.Windows.Controls.Primitives.Popup>area di destinazione, l'origine di destinazione e il punto di allineamento <xref:System.Windows.Controls.Primitives.PlacementMode> del popup per ogni valore. In ogni figura l'area di destinazione è gialla e <xref:System.Windows.Controls.Primitives.Popup> è blu.  
  
 ![Popup con posizionamento assoluto o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "La selezione host è Absolute o AbsolutePoint.")    
  
 ![Popup con posizionamento inferiore] Il (./media/popup-placement-behavior/popup-placement-bottom.png "posizionamento è inferiore.")   
  
 ![Popup con posizionamento centrato] Il (./media/popup-placement-behavior/popup-placement-center.png "posizionamento è al centro.")    
  
 ![Popup con posizionamento a sinistra](./media/popup-placement-behavior/popup-placement-left.png "La selezione host è a sinistra.")   
  
 ![Popup con posizionamento del mouse] Il (./media/popup-placement-behavior/popup-placement-mouse.png "posizionamento è mouse.")  
  
 ![Popup con selezione host MousePoint] Il (./media/popup-placement-behavior/popup-placement-mousepoint.png "posizionamento è MousePoint.")  
  
 ![Popup con posizionamento relativo o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "La selezione host è relativa o RelativePoint.")    
  
 ![Popup con posizionamento a destra](./media/popup-placement-behavior/popup-placement-right.png "Selezione host corretta.")    
  
 ![Popup con posizionamento superiore] Il (./media/popup-placement-behavior/popup-placement-top.png "posizionamento è top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Rilevamento dei bordi dello schermo da parte del controllo Popup  
 Per motivi di sicurezza, <xref:System.Windows.Controls.Primitives.Popup> un oggetto non può essere nascosto dal bordo di una schermata. Una delle tre situazioni seguenti si verifica quando <xref:System.Windows.Controls.Primitives.Popup> rileva un bordo dello schermo:  
  
- Il popup viene riallineato lungo il bordo dello schermo che nasconderebbe <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Il popup usa un punto di allineamento diverso.  
  
- Il popup usa un'origine di destinazione e un punto di allineamento diversi.  
  
 Tali opzioni vengono descritte più avanti in questa sezione.  
  
 Il comportamento di <xref:System.Windows.Controls.Primitives.Popup> quando rileva un bordo dello schermo dipende dal valore <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> della proprietà e dal bordo dello schermo rilevato dal popup. Nella tabella seguente viene riepilogato il comportamento quando <xref:System.Windows.Controls.Primitives.Popup> rileva un bordo dello schermo per ogni <xref:System.Windows.Controls.Primitives.PlacementMode> valore.  
  
|PlacementMode|Bordo superiore|Bordo inferiore|Bordo sinistro|Bordo destro|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento del popup viene modificato nell'angolo superiore destro dell' <xref:System.Windows.Controls.Primitives.Popup>oggetto.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|L'origine di destinazione viene modificata nell'angolo superiore destro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione (i limiti del puntatore del mouse) e il punto di allineamento viene modificato nell'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore destro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|L'origine di destinazione viene modificata nell'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>. In effetti, questo è lo stesso di quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
  
### <a name="aligning-to-the-screen-edge"></a>Allineamento al bordo dello schermo  
 Un <xref:System.Windows.Controls.Primitives.Popup> oggetto può essere allineato al bordo dello schermo riposizionando se stesso in <xref:System.Windows.Controls.Primitives.Popup> modo che l'intero sia visibile sullo schermo.  In tal caso, la distanza tra l'origine di destinazione e il punto di allineamento del popup potrebbe essere <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> diversa <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>dai valori di e. Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, o<xref:System.Windows.Controls.Primitives.PlacementMode.Center> ,l'<xref:System.Windows.Controls.Primitives.Popup> oggetto si allinea a ogni bordo dello schermo. <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>  Si supponga, ad esempio, che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> sia impostato <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> su <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> e che sia impostato su 100. <xref:System.Windows.Controls.Primitives.Popup>  Se il bordo inferiore dello schermo nasconde tutto o parte dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup> , viene riposizionato lungo il bordo inferiore dello schermo e la distanza verticale tra l'origine di destinazione e il punto di allineamento del popup è inferiore a 100. La figura seguente illustra questa situazione.  
  
 ![Popup che è allineato al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup è allineato al bordo dello schermo.")    
  
### <a name="changing-the-popup-alignment-point"></a>Modifica del punto di allineamento del controllo Popup  
 Se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>o ,ilpuntodiallineamentodelpopupvienemodificatoquandoilpopuprilevailbordoinferioreodestrodelloschermo.<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>  
  
 Nell'illustrazione seguente viene dimostrato che quando il bordo inferiore dello schermo nasconde tutto o parte di <xref:System.Windows.Controls.Primitives.Popup>, il punto di allineamento del popup è l'angolo inferiore sinistro <xref:System.Windows.Controls.Primitives.Popup>di.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup rileva il bordo inferiore dello schermo e modifica il punto di allineamento del popup.")  

 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup> è nascosto dal bordo destro dello schermo, il punto di allineamento del popup è l'angolo superiore destro dell' <xref:System.Windows.Controls.Primitives.Popup>oggetto.  
  
 ![Nuovo punto di allineamento popup dovuto al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup rileva il bordo destro dello schermo e modifica il punto di allineamento del popup.")    
  
 Se rileva i bordi inferiore e destro dello schermo, il punto <xref:System.Windows.Controls.Primitives.Popup>di allineamento del popup è l'angolo inferiore destro di. <xref:System.Windows.Controls.Primitives.Popup>  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Modifica dell'origine di destinazione e del punto di allineamento del controllo Popup  
 Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, ,<xref:System.Windows.Controls.Primitives.PlacementMode.Left> ,o<xref:System.Windows.Controls.Primitives.PlacementMode.Top>, l'origine di destinazione e il punto di allineamento del popup cambiano se viene rilevato un determinato bordo dello schermo. <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.PlacementMode.Right>  Il bordo dello schermo che determina la modifica della posizione dipende <xref:System.Windows.Controls.Primitives.PlacementMode> dal valore.  
  
 Nell'illustrazione seguente viene dimostrato che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> quando <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> è e <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento del popup è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo] Il (./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "posizionamento è inferiore e il popup rileva il bordo inferiore dello schermo.")    
  
 Nell'illustrazione seguente viene dimostrato che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> quando <xref:System.Windows.Controls.Primitives.PlacementMode.Left> è e <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo sinistro della schermata, l'origine di destinazione è l'angolo superiore destro dell'area di destinazione e il punto di allineamento del popup è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo sinistro dello schermo](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Il posizionamento è a sinistra e il popup rileva il bordo sinistro dello schermo.")  
  
 Nell'illustrazione seguente viene dimostrato che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> quando <xref:System.Windows.Controls.Primitives.PlacementMode.Right> è e <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo destro dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore destro della <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo destro dello schermo] Il (./media/popup-placement-behavior/popup-placement-right-screen-edge.png "posizionamento è a destra e il popup rileva il bordo destro dello schermo.")  

 Nell'illustrazione seguente viene dimostrato che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> quando <xref:System.Windows.Controls.Primitives.PlacementMode.Top> è e <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo superiore dello schermo, l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento del popup è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo superiore dello schermo] Il (./media/popup-placement-behavior/popup-placement-top-screen-edge.png "posizionamento è top e il popup rileva il bordo superiore dello schermo.")  
  
 Nell'illustrazione seguente viene dimostrato che <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> quando <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> è e <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione (i limiti del puntatore del mouse) e l'allineamento del popup. Point è l'angolo inferiore sinistro di <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nuovo punto di allineamento dovuto al mouse vicino al bordo dello schermo](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Il posizionamento è il mouse e il popup rileva il bordo inferiore dello schermo.")    
  
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare l'origine di destinazione e il punto di allineamento del <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> popup impostando la proprietà su. <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> Definire quindi un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato che restituisce un set di punti di posizionamento possibili e assi primari (in ordine di preferenza) <xref:System.Windows.Controls.Primitives.Popup>per. Il punto che mostra la parte più grande di <xref:System.Windows.Controls.Primitives.Popup> è selezionato.  La posizione dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> viene regolata automaticamente <xref:System.Windows.Controls.Primitives.Popup> se è nascosta al bordo dello schermo. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vedere anche

- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS) (Esempio di posizionamento di un controllo Popup)
