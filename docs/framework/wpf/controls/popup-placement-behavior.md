---
title: Comportamento del controllo Popup in relazione al posizionamento
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 911c2064e34ed8d0a341ffd9a52f852eab677e0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771319"
---
# <a name="popup-placement-behavior"></a>Comportamento del controllo Popup in relazione al posizionamento
Oggetto <xref:System.Windows.Controls.Primitives.Popup> controllo Visualizza il contenuto in una finestra separata mobile rispetto a un'applicazione. È possibile specificare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> rispetto a un controllo, il puntatore del mouse o la schermata usando la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà.  Queste proprietà interagiscono per offrire flessibilità nello specificare la posizione del <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ContextMenu> anche classi definiscono queste cinque proprietà e presentano un comportamento simile.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Posizionamento del controllo Popup  
 Il posizionamento di un <xref:System.Windows.Controls.Primitives.Popup> può essere relativo a un <xref:System.Windows.UIElement> o per l'intera schermata.  L'esempio seguente crea quattro <xref:System.Windows.Controls.Primitives.Popup> controlli di cui si riferiscono un <xref:System.Windows.UIElement>: in questo caso, un'immagine. Tutti i <xref:System.Windows.Controls.Primitives.Popup> controlli hanno il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> proprietà impostata su `image1`, ma ogni <xref:System.Windows.Controls.Primitives.Popup> ha un valore diverso per la proprietà di posizionamento.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 La figura seguente mostra l'immagine e il <xref:System.Windows.Controls.Primitives.Popup> controlli  
  
 ![Immagine con quattro controlli popup](./media/popup-placement-behavior/popup-placement-intro.png "immagine con quattro controlli popup")    
  
 Questo semplice esempio viene illustrato come impostare il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> delle proprietà, ma tramite il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà, avere maggiore controllo sulla posizione in cui il <xref:System.Windows.Controls.Primitives.Popup> è posizionato.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definizioni dei termini: Anatomia di un controllo Popup  
 I termini seguenti sono utili per informazioni su come la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà sono correlate tra loro e <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Oggetto destinazione  
  
- Area di destinazione  
  
- Origine di destinazione  
  
- Punto di allineamento del controllo Popup  
  
 Questi termini rappresentano un modo pratico per fare riferimento a vari aspetti del <xref:System.Windows.Controls.Primitives.Popup> e il controllo che è associato.  
  
### <a name="target-object"></a>Oggetto di destinazione  
 Il *oggetto di destinazione* è l'elemento che il <xref:System.Windows.Controls.Primitives.Popup> è associato. Se il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è impostata, specifica l'oggetto di destinazione.  Se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> non è impostato e il <xref:System.Windows.Controls.Primitives.Popup> ha un padre, l'elemento padre è l'oggetto di destinazione.  Se è presente alcun <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> valore e nessun elemento padre, è presente alcun oggetto di destinazione e il <xref:System.Windows.Controls.Primitives.Popup> viene posizionata in relazione la schermata.  
  
 L'esempio seguente crea una <xref:System.Windows.Controls.Primitives.Popup> che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas>.  L'esempio non viene impostata la <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> proprietà di <xref:System.Windows.Controls.Primitives.Popup>. Il valore predefinito per <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, pertanto il <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sotto il <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 La figura seguente mostra che il <xref:System.Windows.Controls.Primitives.Popup> è posizionato in relazione al <xref:System.Windows.Controls.Canvas>.  
  
 ![Controllo popup senza proprietà PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup senza proprietà PlacementTarget.")  

 L'esempio seguente crea una <xref:System.Windows.Controls.Primitives.Popup> che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas>, ma questa volta il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è impostata su `ellipse1`, in modo che il popup viene visualizzato sotto il <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 La figura seguente mostra che il <xref:System.Windows.Controls.Primitives.Popup> è posizionato in relazione al <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Popup posizionato rispetto a un'ellisse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup con proprietà PlacementTarget")    
  
> [!NOTE]
>  Per la <xref:System.Windows.Controls.ToolTip>, il valore predefinito <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Per la <xref:System.Windows.Controls.ContextMenu>, il valore predefinito <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Questi valori vengono descritti più avanti nella sezione "Modalità di interazione delle proprietà".  
  
### <a name="target-area"></a>Area di destinazione  
 Il *area di destinazione* è l'area sullo schermo che il <xref:System.Windows.Controls.Primitives.Popup> relativo alla. Negli esempi precedenti, il <xref:System.Windows.Controls.Primitives.Popup> è allineato con i limiti dell'oggetto di destinazione, ma in alcuni casi, il <xref:System.Windows.Controls.Primitives.Popup> è allineato ad altri limiti, anche se il <xref:System.Windows.Controls.Primitives.Popup> dispone di un oggetto di destinazione.  Se il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è impostata, l'area di destinazione è diverso rispetto ai limiti dell'oggetto di destinazione.  
  
 L'esempio seguente crea due <xref:System.Windows.Controls.Canvas> oggetti, ognuno dei quali contenente un <xref:System.Windows.Shapes.Rectangle> e un <xref:System.Windows.Controls.Primitives.Popup>.  In entrambi i casi, l'oggetto di destinazione per il <xref:System.Windows.Controls.Primitives.Popup> è il <xref:System.Windows.Controls.Canvas>. Il <xref:System.Windows.Controls.Primitives.Popup> nel primo <xref:System.Windows.Controls.Canvas> ha il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> impostato, con relativi <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, e <xref:System.Windows.Rect.Height%2A> impostate rispettivamente su 50, 50, 50 e 100,. Il <xref:System.Windows.Controls.Primitives.Popup> nella seconda <xref:System.Windows.Controls.Canvas> non dispone di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> impostato.  Di conseguenza, il primo <xref:System.Windows.Controls.Primitives.Popup> è posizionata sotto la <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> e il secondo <xref:System.Windows.Controls.Primitives.Popup> si trova sotto il <xref:System.Windows.Controls.Canvas>. Ogni <xref:System.Windows.Controls.Canvas> contiene anche un <xref:System.Windows.Shapes.Rectangle> che ha gli stessi limiti di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> per il primo <xref:System.Windows.Controls.Primitives.Popup>.  Si noti che il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> non crea un elemento visibile nell'applicazione; nell'esempio viene creata una <xref:System.Windows.Shapes.Rectangle> per rappresentare il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Popup con e senza PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con e senza PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origine di destinazione e punto di allineamento del controllo Popup  
 L'*origine di destinazione* e il *punto di allineamento del controllo Popup* sono punti di riferimento, rispettivamente sull'area di destinazione e sul popup, usati per il posizionamento. È possibile usare la <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> le proprietà di offset il popup provenienti dall'area di destinazione.  Il <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> riguardano l'origine di destinazione e il punto di allineamento. Il valore della <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà determina in cui si trova il punto di allineamento popup e origine di destinazione.  
  
 L'esempio seguente crea una <xref:System.Windows.Controls.Primitives.Popup> e imposta la <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà a 20.  Il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (impostazione predefinita), pertanto l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Posizionamento di popup con punto di allineamento di origine di destinazione](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset e VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Modalità di interazione delle proprietà  
 I valori della <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, e <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> devono essere presi in considerazione insieme per determinare l'area di destinazione, l'origine di destinazione e punto di allineamento.  Ad esempio, se il valore di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, è presente alcun oggetto di destinazione, il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato e l'area di destinazione è costituita dai limiti del puntatore del mouse. D'altra parte, se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre determina l'oggetto di destinazione e <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> determina l'area di destinazione.  
  
 Nella tabella seguente descrive l'oggetto di destinazione, area di destinazione, origine di destinazione e punto di allineamento e indica se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> e <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> vengono utilizzati per ciascun <xref:System.Windows.Controls.Primitives.PlacementMode> valore di enumerazione.  
  
|PlacementMode|Oggetto destinazione|Area di destinazione|Origine di destinazione|Punto di allineamento del controllo Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Schermata di, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Schermata di, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo inferiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Centro dell'area di destinazione.|Al centro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Definito dal <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definito dal <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo inferiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore destro dell'area di destinazione.|L'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> o padre.|L'oggetto di destinazione, o <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> se è impostata.  Il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Nell'illustrazione seguente vengono mostrati i <xref:System.Windows.Controls.Primitives.Popup>, area di destinazione, origine di destinazione e allineamento dei punti per ogni <xref:System.Windows.Controls.Primitives.PlacementMode> valore. In ogni figura l'area di destinazione è di colore giallo e il <xref:System.Windows.Controls.Primitives.Popup> è blu.  
  
 ![Popup con posizionamento Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "il posizionamento è Absolute o AbsolutePoint.")    
  
 ![Popup con posizionamento Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "il posizionamento è Bottom.")   
  
 ![Popup con posizionamento Center](./media/popup-placement-behavior/popup-placement-center.png "il posizionamento è Center.")    
  
 ![Popup con posizionamento Left](./media/popup-placement-behavior/popup-placement-left.png "il posizionamento è Left.")   
  
 ![Popup con posizionamento Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "il posizionamento è Mouse.")  
  
 ![Popup con posizionamento MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "il posizionamento è MousePoint.")  
  
 ![Popup con posizionamento relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "il posizionamento è relative o RelativePoint.")    
  
 ![Popup con posizionamento Right](./media/popup-placement-behavior/popup-placement-right.png "il posizionamento è Right.")    
  
 ![Popup con posizionamento Top](./media/popup-placement-behavior/popup-placement-top.png "il posizionamento è Top.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Rilevamento dei bordi dello schermo da parte del controllo Popup  
 Per motivi di sicurezza, un <xref:System.Windows.Controls.Primitives.Popup> non può essere nascosto dal bordo di una schermata. Si verifica una delle tre situazioni seguenti quando il <xref:System.Windows.Controls.Primitives.Popup> incontra un bordo dello schermo:  
  
- La finestra popup viene riposizionato lungo il bordo dello schermo che nasconde il <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Il popup usa un punto di allineamento diverso.  
  
- Il popup usa un'origine di destinazione e un punto di allineamento diversi.  
  
 Tali opzioni vengono descritte più avanti in questa sezione.  
  
 Il comportamento del <xref:System.Windows.Controls.Primitives.Popup> quando rileva un bordo dello schermo dipende dal valore della <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà e il cui bordo il controllo popup rileva dello schermo. La tabella seguente riepiloga il comportamento quando le <xref:System.Windows.Controls.Primitives.Popup> incontra un bordo dello schermo per ogni <xref:System.Windows.Controls.Primitives.PlacementMode> valore.  
  
|PlacementMode|Bordo superiore|Bordo inferiore|Bordo sinistro|Bordo destro|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Allineamento al bordo superiore.|Il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Allineamento al bordo superiore.|L'origine di destinazione viene modificato nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|L'origine di destinazione viene modificato nell'angolo superiore destro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Allineamento al bordo superiore.|L'origine di destinazione viene modificato nell'angolo superiore sinistro dell'area di destinazione (limiti del puntatore del mouse) e il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Allineamento al bordo superiore.|Il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Allineamento al bordo superiore.|Il punto di allineamento viene modificato nell'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|L'origine di destinazione viene modificato nell'angolo superiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|L'origine di destinazione viene modificato nell'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento viene modificato nell'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>. In effetti, questo è analogo a quello <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
  
### <a name="aligning-to-the-screen-edge"></a>Allineamento al bordo dello schermo  
 Oggetto <xref:System.Windows.Controls.Primitives.Popup> possibile allineato al bordo dello schermo riposizionandolo così l'intera <xref:System.Windows.Controls.Primitives.Popup> è visibile sullo schermo.  In questo caso, la distanza tra il punto di allineamento popup e origine di destinazione potrebbero essere diversi dai valori di <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, o <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, il <xref:System.Windows.Controls.Primitives.Popup> viene allineato a ogni bordo dello schermo.  Ad esempio, si supponga che un <xref:System.Windows.Controls.Primitives.Popup> ha <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> impostato su 100.  Se il bordo inferiore dello schermo nasconde tutto o parte del <xref:System.Windows.Controls.Primitives.Popup>, il <xref:System.Windows.Controls.Primitives.Popup> viene riposizionato lungo il bordo inferiore dello schermo e la distanza verticale tra l'origine di destinazione e popup punto di allineamento è inferiore a 100. La figura seguente illustra questa situazione.  
  
 ![Popup allineato al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup allineato al bordo dello schermo.")    
  
### <a name="changing-the-popup-alignment-point"></a>Modifica del punto di allineamento del controllo Popup  
 Se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, o <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, il punto di allineamento viene modificato quando il controllo popup rileva il bordo inferiore o destro dello schermo.  
  
 La figura seguente illustra che quando il bordo inferiore dello schermo nasconde o in parte il <xref:System.Windows.Controls.Primitives.Popup>, il punto di allineamento è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "controllo Popup rileva il bordo inferiore dello schermo e il punto di allineamento viene modificato.")  

 La figura seguente illustra che quando la <xref:System.Windows.Controls.Primitives.Popup> è nascosto dal bordo destro dello schermo, il punto di allineamento è l'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento popup dovuto al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "controllo Popup rileva il bordo destro dello schermo e il punto di allineamento viene modificato.")    
  
 Se il <xref:System.Windows.Controls.Primitives.Popup> rileva i bordi inferiore e destro dello schermo, il punto di allineamento è l'angolo in basso a destra del <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Modifica dell'origine di destinazione e del punto di allineamento del controllo Popup  
 Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, o <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, l'allineamento di origine e la finestra popup di destinazione se il punto viene rilevato un determinato bordo dello schermo.  Il bordo dello schermo che causa la modifica della posizione dipende il <xref:System.Windows.Controls.Primitives.PlacementMode> valore.  
  
 La figura seguente illustra che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "il posizionamento è Bottom e il controllo popup rileva il bordo inferiore dello schermo.")    
  
 La figura seguente illustra che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Left> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo sinistro dello schermo, l'origine di destinazione è l'angolo superiore destro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo sinistro dello schermo](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "il posizionamento è Left e il controllo popup rileva il bordo sinistro della schermata.")  
  
 La figura seguente illustra che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Right> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo destro dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore destro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo destro dello schermo](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "il posizionamento è Right e il controllo popup rileva il bordo destro dello schermo.")  

 La figura seguente illustra che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Top> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo superiore dello schermo, l'origine di destinazione è l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento è l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Nuovo punto di allineamento dovuto al bordo superiore dello schermo](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "il posizionamento è Top e il controllo popup rileva il bordo superiore dello schermo.")  
  
 La figura seguente illustra che quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> e il <xref:System.Windows.Controls.Primitives.Popup> rileva il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro dell'area di destinazione (limiti del puntatore del mouse) e l'allineamento del controllo popup punto è l'angolo inferiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![nuovo punto di allineamento dovuto al mouse vicino al bordo dello schermo](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "il posizionamento è Mouse e il controllo popup rileva il bordo inferiore dello schermo.")    
  
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare il punto di allineamento popup e origine di destinazione impostando il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Quindi definire un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato che restituisce un set di possibili punti di posizionamento e assi primari (in ordine di preferenza) per il <xref:System.Windows.Controls.Primitives.Popup>. Il punto che visualizza la parte di maggiore di <xref:System.Windows.Controls.Primitives.Popup> sia selezionata.  La posizione del <xref:System.Windows.Controls.Primitives.Popup> viene adattata automaticamente se il <xref:System.Windows.Controls.Primitives.Popup> è nascosto dal bordo dello schermo. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vedere anche

- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS) (Esempio di posizionamento di un controllo Popup)
