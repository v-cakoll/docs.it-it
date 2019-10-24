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
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "69951726"
---
# <a name="popup-placement-behavior"></a>Comportamento del controllo Popup in relazione al posizionamento
Un controllo <xref:System.Windows.Controls.Primitives.Popup> Visualizza il contenuto in una finestra separata che è mobile su un'applicazione. È possibile specificare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> rispetto a un controllo, al mouse o alla schermata usando le proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>.  Queste proprietà interagiscono per offrire la flessibilità necessaria per specificare la posizione del <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
> Le classi <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ContextMenu> definiscono anche queste cinque proprietà e si comportano in modo simile.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Posizionamento del controllo Popup  
 La posizione di un <xref:System.Windows.Controls.Primitives.Popup> può essere relativa a una <xref:System.Windows.UIElement> o all'intero schermo.  Nell'esempio seguente vengono creati quattro controlli <xref:System.Windows.Controls.Primitives.Popup> relativi a una <xref:System.Windows.UIElement>, in questo caso un'immagine. Tutti i controlli <xref:System.Windows.Controls.Primitives.Popup> hanno la proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> impostata su `image1`, ma ogni <xref:System.Windows.Controls.Primitives.Popup> ha un valore diverso per la proprietà Placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Nella figura seguente vengono illustrati l'immagine e i controlli <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![Immagine con quattro controlli Popup](./media/popup-placement-behavior/popup-placement-intro.png "Immagine con quattro popup")    
  
 Questo semplice esempio illustra come impostare le proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, ma usando le proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>, si ha un maggiore controllo sulla posizione in cui è posizionato il <xref:System.Windows.Controls.Primitives.Popup>.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definizioni dei termini - Analisi di un controllo Popup  
 I termini seguenti sono utili per comprendere il modo in cui le proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sono correlate tra loro e il <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Oggetto destinazione  
  
- Area di destinazione  
  
- Origine di destinazione  
  
- Punto di allineamento del controllo Popup  
  
 Questi termini costituiscono un modo pratico per fare riferimento a diversi aspetti del <xref:System.Windows.Controls.Primitives.Popup> e al controllo a cui è associato.  
  
### <a name="target-object"></a>Oggetto di destinazione  
 L' *oggetto di destinazione* è l'elemento a cui è associata la <xref:System.Windows.Controls.Primitives.Popup>. Se viene impostata la proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, viene specificato l'oggetto di destinazione.  Se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> non è impostato e il <xref:System.Windows.Controls.Primitives.Popup> dispone di un elemento padre, l'elemento padre è l'oggetto di destinazione.  Se non è presente alcun valore <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> e nessun elemento padre, non è presente alcun oggetto di destinazione e il <xref:System.Windows.Controls.Primitives.Popup> è posizionato in relazione allo schermo.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.Popup> figlio di un <xref:System.Windows.Controls.Canvas>.  Nell'esempio non viene impostata la proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nel <xref:System.Windows.Controls.Primitives.Popup>. Il valore predefinito per <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, quindi il <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sotto il <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Nella figura seguente viene illustrato che il <xref:System.Windows.Controls.Primitives.Popup> è posizionato in relazione al <xref:System.Windows.Controls.Canvas>.  
  
 ![Controllo Popup senza proprietà PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup senza PlacementTarget.")  

 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.Popup> figlio di un <xref:System.Windows.Controls.Canvas>, ma questa volta il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è impostato su `ellipse1`, quindi la finestra popup viene visualizzata sotto la <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Nella figura seguente viene illustrato che il <xref:System.Windows.Controls.Primitives.Popup> è posizionato in relazione al <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Controllo Popup posizionato in relazione a un'ellisse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Controllo Popup con proprietà PlacementTarget")    
  
> [!NOTE]
> Per <xref:System.Windows.Controls.ToolTip>, il valore predefinito di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Per <xref:System.Windows.Controls.ContextMenu>, il valore predefinito di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Questi valori vengono descritti più avanti nella sezione "Modalità di interazione delle proprietà".  
  
### <a name="target-area"></a>Area di destinazione  
 L' *area di destinazione* è l'area sullo schermo a cui è correlata la <xref:System.Windows.Controls.Primitives.Popup>. Negli esempi precedenti, il <xref:System.Windows.Controls.Primitives.Popup> è allineato con i limiti dell'oggetto di destinazione, ma in alcuni casi il <xref:System.Windows.Controls.Primitives.Popup> è allineato ad altri limiti, anche se il <xref:System.Windows.Controls.Primitives.Popup> dispone di un oggetto di destinazione.  Se la proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è impostata, l'area di destinazione è diversa dai limiti dell'oggetto di destinazione.  
  
 Nell'esempio seguente vengono creati due oggetti <xref:System.Windows.Controls.Canvas>, ognuno contenente una <xref:System.Windows.Shapes.Rectangle> e un <xref:System.Windows.Controls.Primitives.Popup>.  In entrambi i casi, l'oggetto di destinazione per il <xref:System.Windows.Controls.Primitives.Popup> è l'<xref:System.Windows.Controls.Canvas>. Il <xref:System.Windows.Controls.Primitives.Popup> nella prima <xref:System.Windows.Controls.Canvas> dispone del set di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, con le proprietà <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> e <xref:System.Windows.Rect.Height%2A> impostate rispettivamente su 50, 50, 50 e 100. Il <xref:System.Windows.Controls.Primitives.Popup> nel secondo <xref:System.Windows.Controls.Canvas> non dispone del set di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  Di conseguenza, la prima <xref:System.Windows.Controls.Primitives.Popup> viene posizionata al di sotto della <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> e la seconda <xref:System.Windows.Controls.Primitives.Popup> viene posizionata sotto la <xref:System.Windows.Controls.Canvas>. Ogni <xref:System.Windows.Controls.Canvas> contiene anche una <xref:System.Windows.Shapes.Rectangle> con gli stessi limiti del <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> per il primo <xref:System.Windows.Controls.Primitives.Popup>.  Si noti che il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> non crea un elemento visibile nell'applicazione; Nell'esempio viene creato un <xref:System.Windows.Shapes.Rectangle> per rappresentare l'<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Popup con e senza PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con e senza PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origine di destinazione e punto di allineamento del controllo Popup  
 L'*origine di destinazione* e il *punto di allineamento del controllo Popup* sono punti di riferimento, rispettivamente sull'area di destinazione e sul popup, usati per il posizionamento. È possibile usare le proprietà <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> per compensare il popup dall'area di destinazione.  Il <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sono relativi all'origine di destinazione e al punto di allineamento del popup. Il valore della proprietà <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> determina la posizione in cui si trovano l'origine di destinazione e il punto di allineamento del popup.  
  
 Nell'esempio seguente viene creata una <xref:System.Windows.Controls.Primitives.Popup> e vengono impostate le proprietà <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> su 20.  La proprietà <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (impostazione predefinita), quindi l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro della <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Posizionamento del controllo Popup con punto di allineamento sull'origine di destinazione](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset e VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Modalità di interazione delle proprietà  
 I valori di <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> devono essere considerati insieme per individuare l'area di destinazione, l'origine di destinazione e il punto di allineamento del popup corretti.  Se, ad esempio, il valore di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, non è presente alcun oggetto di destinazione, il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato e l'area di destinazione è il limite del puntatore del mouse. D'altra parte, se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o l'elemento padre determina l'oggetto di destinazione e <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> determina l'area di destinazione.  
  
 La tabella seguente descrive l'oggetto di destinazione, l'area di destinazione, l'origine di destinazione e il punto di allineamento del popup e indica se vengono usati <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> e <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> per ogni <xref:System.Windows.Controls.Primitives.PlacementMode> valore di enumerazione.  
  
|PlacementMode|Oggetto destinazione|Area di destinazione|Origine di destinazione|Punto di allineamento del controllo Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Schermata o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Schermata o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo inferiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Centro dell'area di destinazione.|Centro della <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Definito dall'<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definito dall'<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo inferiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore destro dell'area di destinazione.|Angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|Oggetto di destinazione o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostato.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|Angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Nelle illustrazioni seguenti vengono illustrati il <xref:System.Windows.Controls.Primitives.Popup>, l'area di destinazione, l'origine di destinazione e il punto di allineamento del popup per ogni valore di <xref:System.Windows.Controls.Primitives.PlacementMode>. In ogni figura l'area di destinazione è gialla e il <xref:System.Windows.Controls.Primitives.Popup> è blu.  
  
 ![Popup con posizionamento Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "La selezione host è Absolute o AbsolutePoint.")    
  
 ![Popup con posizionamento Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "Il posizionamento è inferiore.")   
  
 ![Popup con posizionamento Center](./media/popup-placement-behavior/popup-placement-center.png "Il posizionamento è al centro.")    
  
 ![Popup con posizionamento Left](./media/popup-placement-behavior/popup-placement-left.png "La selezione host è a sinistra.")   
  
 ![Popup con posizionamento Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "Il posizionamento è mouse.")  
  
 ![Popup con posizionamento MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Il posizionamento è MousePoint.")  
  
 ![Popup con posizionamento Relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "La selezione host è relativa o RelativePoint.")    
  
 ![Popup con posizionamento Right](./media/popup-placement-behavior/popup-placement-right.png "Selezione host corretta.")    
  
 ![Popup con posizionamento Top](./media/popup-placement-behavior/popup-placement-top.png "Il posizionamento è top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Rilevamento dei bordi dello schermo da parte del controllo Popup  
 Per motivi di sicurezza, un <xref:System.Windows.Controls.Primitives.Popup> non può essere nascosto dal bordo di una schermata. Una delle tre situazioni seguenti si verifica quando il <xref:System.Windows.Controls.Primitives.Popup> rileva un bordo dello schermo:  
  
- Il popup viene riallineato lungo il bordo dello schermo che nasconderebbe la <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Il popup usa un punto di allineamento diverso.  
  
- Il popup usa un'origine di destinazione e un punto di allineamento diversi.  
  
 Tali opzioni vengono descritte più avanti in questa sezione.  
  
 Il comportamento del <xref:System.Windows.Controls.Primitives.Popup> quando rileva un bordo dello schermo dipende dal valore della proprietà <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> e dal bordo dello schermo rilevato dal popup. Nella tabella seguente viene riepilogato il comportamento quando il <xref:System.Windows.Controls.Primitives.Popup> rileva un bordo dello schermo per ogni valore <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
|PlacementMode|Bordo superiore|Bordo inferiore|Bordo sinistro|Bordo destro|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento del popup viene modificato nell'angolo superiore destro della <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|L'origine di destinazione viene modificata nell'angolo superiore destro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione (i limiti del puntatore del mouse) e il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Allineamento al bordo superiore.|Il punto di allineamento del popup viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|L'origine di destinazione viene modificata nell'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>. In effetti, questo è lo stesso di quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
  
### <a name="aligning-to-the-screen-edge"></a>Allineamento al bordo dello schermo  
 Un <xref:System.Windows.Controls.Primitives.Popup> può essere allineato al bordo dello schermo riposizionando in modo che l'intero <xref:System.Windows.Controls.Primitives.Popup> sia visibile sullo schermo.  In tal caso, la distanza tra l'origine di destinazione e il punto di allineamento del popup potrebbe essere diversa dai valori di <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> o <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, il <xref:System.Windows.Controls.Primitives.Popup> si allinea a ogni bordo dello schermo.  Si supponga, ad esempio, che un <xref:System.Windows.Controls.Primitives.Popup> abbia <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> impostato su <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> impostato su 100.  Se il bordo inferiore dello schermo nasconde tutto o parte del <xref:System.Windows.Controls.Primitives.Popup>, il <xref:System.Windows.Controls.Primitives.Popup> viene riposizionato lungo il bordo inferiore dello schermo e la distanza verticale tra l'origine di destinazione e il punto di allineamento del popup è inferiore a 100. La figura seguente illustra questa situazione.  
  
 ![Popup allineato al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup è allineato al bordo dello schermo.")    
  
### <a name="changing-the-popup-alignment-point"></a>Modifica del punto di allineamento del controllo Popup  
 Se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> o <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, il punto di allineamento del popup viene modificato quando il popup rileva il bordo inferiore o destro dello schermo.  
  
 Nell'illustrazione seguente viene dimostrato che quando il bordo inferiore dello schermo nasconde tutto o parte del <xref:System.Windows.Controls.Primitives.Popup>, il punto di allineamento del popup è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup rileva il bordo inferiore dello schermo e modifica il punto di allineamento del popup.")  

 Nell'illustrazione seguente viene dimostrato che quando il <xref:System.Windows.Controls.Primitives.Popup> è nascosto dal bordo destro dello schermo, il punto di allineamento è l'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup rileva il bordo destro dello schermo e modifica il punto di allineamento del popup.")    
  
 Se il <xref:System.Windows.Controls.Primitives.Popup> rileva i bordi inferiore e destro dello schermo, il punto di allineamento del popup è l'angolo inferiore destro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Modifica dell'origine di destinazione e del punto di allineamento del controllo Popup  
 Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> o <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, l'origine di destinazione e il punto di allineamento del popup cambiano se viene rilevato un determinato bordo dello schermo.  Il bordo dello schermo che determina la modifica della posizione dipende dal valore <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento del popup è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Il posizionamento è inferiore e il popup rileva il bordo inferiore dello schermo.")    
  
 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Left> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo sinistro della schermata, l'origine di destinazione è l'angolo superiore destro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo sinistro dello schermo](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Il posizionamento è a sinistra e il popup rileva il bordo sinistro dello schermo.")  
  
 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Right> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo destro dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento del popup è l'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo destro dello schermo](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Il posizionamento è a destra e il popup rileva il bordo destro dello schermo.")  

 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Top> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo superiore dello schermo, l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo superiore dello schermo](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Il posizionamento è top e il popup rileva il bordo superiore dello schermo.")  
  
 Nell'illustrazione seguente viene dimostrato che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione (i limiti del puntatore del mouse) e il punto di allineamento del popup è il lato inferiore sinistro angolo del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al mouse vicino al bordo dello schermo](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Il posizionamento è il mouse e il popup rileva il bordo inferiore dello schermo.")    
  
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare l'origine di destinazione e il punto di allineamento del popup impostando la proprietà <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definire quindi un delegato <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> che restituisca un set di punti di posizionamento possibili e assi primari (in ordine di preferenza) per l'<xref:System.Windows.Controls.Primitives.Popup>. Il punto che mostra la parte più grande del <xref:System.Windows.Controls.Primitives.Popup> è selezionato.  La posizione del <xref:System.Windows.Controls.Primitives.Popup> viene regolata automaticamente se il <xref:System.Windows.Controls.Primitives.Popup> è nascosto dal bordo dello schermo. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vedere anche

- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS) (Esempio di posizionamento di un controllo Popup)
