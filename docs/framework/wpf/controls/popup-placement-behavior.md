---
title: Comportamento del controllo Popup in relazione al posizionamento
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 1c377e62ffd334638031baee4d4831ac5a31acf3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243258"
---
# <a name="popup-placement-behavior"></a>Comportamento del controllo Popup in relazione al posizionamento
Un <xref:System.Windows.Controls.Primitives.Popup> controllo visualizza il contenuto in una finestra separata che fluttua su un'applicazione. È possibile specificare <xref:System.Windows.Controls.Primitives.Popup> la posizione di un controllo relativo a <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>un <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>controllo, il mouse o lo schermo utilizzando le proprietà , , , e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> .  Queste proprietà lavorano insieme per offrire flessibilità <xref:System.Windows.Controls.Primitives.Popup>nella specifica della posizione del file .  
  
> [!NOTE]
> Le <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ContextMenu> classi e definiscono inoltre queste cinque proprietà e si comportano in modo simile.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Posizionamento del controllo Popup  
 La posizione <xref:System.Windows.Controls.Primitives.Popup> di un oggetto <xref:System.Windows.UIElement> può essere relativa all'intero schermo.  Nell'esempio seguente <xref:System.Windows.Controls.Primitives.Popup> vengono creati quattro <xref:System.Windows.UIElement>controlli relativi a un oggetto , in questo caso un'immagine. Tutti i <xref:System.Windows.Controls.Primitives.Popup> controlli <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> hanno la `image1`proprietà <xref:System.Windows.Controls.Primitives.Popup> impostata su , ma ognuno ha un valore diverso per la proprietà placement.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 La figura seguente mostra <xref:System.Windows.Controls.Primitives.Popup> l'immagine e i controlli  
  
 ![Immagine con quattro controlli Popup](./media/popup-placement-behavior/popup-placement-intro.png "Immagine con quattro popup")
  
 In questo semplice esempio <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> illustrato come impostare le <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> proprietà e , ma utilizzando <xref:System.Windows.Controls.Primitives.Popup> le <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>proprietà , <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>e , si ha ancora più controllo sulla posizione dell'oggetto .  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definizioni dei termini - Analisi di un controllo Popup  
 I termini seguenti sono utili <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>per <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>comprendere <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> in che modo le <xref:System.Windows.Controls.Primitives.Popup>proprietà , , , e sono correlate tra loro e le opzioni seguenti:  
  
- Oggetti di destinazione  
  
- Area di destinazione  
  
- Origine di destinazione  
  
- Punto di allineamento del controllo Popup  
  
 Questi termini forniscono un modo pratico <xref:System.Windows.Controls.Primitives.Popup> per fare riferimento a vari aspetti del e il controllo a cui è associato.  
  
### <a name="target-object"></a>Oggetto di destinazione  
 *L'oggetto di destinazione* <xref:System.Windows.Controls.Primitives.Popup> è l'elemento a cui è associato l'oggetto. Se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> la proprietà è impostata, specifica l'oggetto di destinazione.  Se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> non è impostato <xref:System.Windows.Controls.Primitives.Popup> e l'oggetto ha un elemento padre, l'elemento padre è l'oggetto di destinazione.  Se non <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è presente alcun valore e nessun elemento <xref:System.Windows.Controls.Primitives.Popup> padre, non è presente alcun oggetto di destinazione e l'oggetto viene posizionato rispetto allo schermo.  
  
 Nell'esempio riportato di seguito viene creato un <xref:System.Windows.Controls.Primitives.Popup> oggetto che è l'elemento figlio di un oggetto . <xref:System.Windows.Controls.Canvas>  Nell'esempio non <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene impostata la proprietà su <xref:System.Windows.Controls.Primitives.Popup>. Il valore <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> predefinito <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>per <xref:System.Windows.Controls.Primitives.Popup> è , <xref:System.Windows.Controls.Canvas>in modo che venga visualizzato sotto il file .  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup> viene illustrato che <xref:System.Windows.Controls.Canvas>l'oggetto è posizionato rispetto al file .  
  
 ![Controllo Popup senza proprietà PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup senza PlacementTarget.")  

 Nell'esempio riportato di seguito viene creato un <xref:System.Windows.Controls.Primitives.Popup> oggetto che è l'elemento figlio di un <xref:System.Windows.Controls.Canvas>oggetto , ma questa volta l'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è impostato su `ellipse1`, in modo che il popup venga visualizzato sotto l'oggetto <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup> viene illustrato che <xref:System.Windows.Shapes.Ellipse>l'oggetto è posizionato rispetto al file .  
  
 ![Controllo Popup posizionato in relazione a un'ellisse](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Controllo Popup con proprietà PlacementTarget")
  
> [!NOTE]
> Per <xref:System.Windows.Controls.ToolTip>, il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> valore <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>predefinito di è .  Per <xref:System.Windows.Controls.ContextMenu>, il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> valore <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>predefinito di è . Questi valori vengono descritti più avanti nella sezione "Modalità di interazione delle proprietà".  
  
### <a name="target-area"></a>Area di destinazione  
 *L'area di destinazione* è l'area sullo schermo a cui si trova l'oggetto. <xref:System.Windows.Controls.Primitives.Popup> Negli esempi precedenti, <xref:System.Windows.Controls.Primitives.Popup> l'oggetto è allineato con i limiti dell'oggetto di destinazione, ma in alcuni casi, l'oggetto <xref:System.Windows.Controls.Primitives.Popup> è allineato ad altri limiti, anche se <xref:System.Windows.Controls.Primitives.Popup> dispone di un oggetto di destinazione.  Se <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> la proprietà è impostata, l'area di destinazione è diversa dai limiti dell'oggetto di destinazione.  
  
 Nell'esempio riportato di seguito vengono creati due <xref:System.Windows.Controls.Canvas> oggetti, ognuno contenente a <xref:System.Windows.Shapes.Rectangle> e un <xref:System.Windows.Controls.Primitives.Popup>oggetto .  In entrambi i casi, <xref:System.Windows.Controls.Primitives.Popup> l'oggetto di destinazione per il è il <xref:System.Windows.Controls.Canvas>. Nel <xref:System.Windows.Controls.Primitives.Popup> primo <xref:System.Windows.Controls.Canvas> il <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> primo ha <xref:System.Windows.Rect.X%2A>le <xref:System.Windows.Rect.Y%2A> <xref:System.Windows.Rect.Width%2A>proprietà <xref:System.Windows.Rect.Height%2A> set, con le proprietà , , e impostate rispettivamente su 50, 50, 50 e 100 . Il <xref:System.Windows.Controls.Primitives.Popup> nel <xref:System.Windows.Controls.Canvas> secondo non <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ha il set.  Di conseguenza, <xref:System.Windows.Controls.Primitives.Popup> il primo è <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> posizionato <xref:System.Windows.Controls.Primitives.Popup> sotto il e <xref:System.Windows.Controls.Canvas>il secondo è posizionato sotto il file . Ognuno <xref:System.Windows.Controls.Canvas> contiene <xref:System.Windows.Shapes.Rectangle> inoltre un che ha <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> gli <xref:System.Windows.Controls.Primitives.Popup>stessi limiti di per il primo .  Si noti che l'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> non crea un elemento visibile nell'applicazione; l'esempio <xref:System.Windows.Shapes.Rectangle> crea un <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>per rappresentare il .  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Popup con e senza PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup con e senza PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Origine di destinazione e punto di allineamento del controllo Popup  
 L'*origine di destinazione* e il *punto di allineamento del controllo Popup* sono punti di riferimento, rispettivamente sull'area di destinazione e sul popup, usati per il posizionamento. È possibile <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> utilizzare <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> le proprietà e per eseguire l'offset del popup dall'area di destinazione.  Gli <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> oggetti sono relativi all'origine di destinazione e al punto di allineamento popup. Il valore <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> della proprietà determina la posizione dell'origine di destinazione e del punto di allineamento popup.  
  
 Nell'esempio seguente <xref:System.Windows.Controls.Primitives.Popup> vengono <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> create <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> le proprietà e su 20.  La <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà è <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> impostata su (impostazione predefinita), pertanto l'origine di destinazione è l'angolo inferiore <xref:System.Windows.Controls.Primitives.Popup>sinistro dell'area di destinazione e il punto di allineamento popup è l'angolo superiore sinistro dell'oggetto .  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 La figura seguente illustra il risultato dell'esempio precedente.  
  
 ![Posizionamento del controllo Popup con punto di allineamento sull'origine di destinazione](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup con HorizontalOffset e VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Modalità di interazione delle proprietà  
 I valori <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>di <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , e devono essere considerati insieme per individuare l'area di destinazione corretta, l'origine di destinazione e il punto di allineamento popup.  Ad esempio, se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> il <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>valore di , non <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è presente alcun oggetto di destinazione, viene ignorato e l'area di destinazione è i limiti del puntatore del mouse. D'altra parte, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>se <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> è , l'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> o l'elemento padre determina l'oggetto di destinazione e determina l'area di destinazione.  
  
 Nella tabella seguente vengono descritti l'oggetto di destinazione, l'area <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione, <xref:System.Windows.Controls.Primitives.PlacementMode> l'origine di destinazione e il punto di allineamento popup e viene indicato se e vengono utilizzati per ogni valore di enumerazione.  
  
|PlacementMode|Oggetti di destinazione|Area di destinazione|Origine di destinazione|Punto di allineamento del controllo Popup|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Lo schermo <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> o se è impostato.  L'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Lo schermo <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> o se è impostato.  L'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> è relativo allo schermo.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo inferiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Centro dell'area di destinazione.|Il centro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Definito dal <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>file .|Definito dal <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo in alto <xref:System.Windows.Controls.Primitives.Popup>a destra del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo inferiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Non applicabile. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> viene ignorato.|Limiti del puntatore del mouse. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> viene ignorato.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo superiore destro dell'area di destinazione.|L'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>o genitore.|L'oggetto di <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> destinazione o se è impostato.  È <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> relativo all'oggetto di destinazione.|Angolo superiore sinistro dell'area di destinazione.|L'angolo inferiore sinistro <xref:System.Windows.Controls.Primitives.Popup>del file .|  
  
 Nelle illustrazioni seguenti <xref:System.Windows.Controls.Primitives.Popup>vengono illustrati i punti di allineamento <xref:System.Windows.Controls.Primitives.PlacementMode> , area di destinazione, origine di destinazione e punto di allineamento popup per ogni valore. In ogni figura, l'area di <xref:System.Windows.Controls.Primitives.Popup> destinazione è gialla, e la è blu.  
  
 ![Popup con posizionamento Absolute o AbsolutePoint](./media/popup-placement-behavior/popup-placement-absolute.png "Il posizionamento è Absolute o AbsolutePoint.")
  
 ![Popup con posizionamento Bottom](./media/popup-placement-behavior/popup-placement-bottom.png "Posizionamento è Bottom.")
  
 ![Popup con posizionamento Center](./media/popup-placement-behavior/popup-placement-center.png "Il posizionamento è Centro.")
  
 ![Popup con posizionamento Left](./media/popup-placement-behavior/popup-placement-left.png "Posizionamento è Left.")
  
 ![Popup con posizionamento Mouse](./media/popup-placement-behavior/popup-placement-mouse.png "Il posizionamento è Mouse.")  
  
 ![Popup con posizionamento MousePoint](./media/popup-placement-behavior/popup-placement-mousepoint.png "Il posizionamento è MousePoint.Placement is MousePoint.")  
  
 ![Popup con posizionamento Relative o RelativePoint](./media/popup-placement-behavior/popup-placement-relative.png "Il posizionamento è Relative o RelativePoint.")
  
 ![Popup con posizionamento Right](./media/popup-placement-behavior/popup-placement-right.png "Il posizionamento è Giusto.")
  
 ![Popup con posizionamento Top](./media/popup-placement-behavior/popup-placement-top.png "Il posizionamento è Top.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Rilevamento dei bordi dello schermo da parte del controllo Popup  
 Per motivi di <xref:System.Windows.Controls.Primitives.Popup> sicurezza, un oggetto non può essere nascosto dal bordo di uno schermo. Una delle tre situazioni seguenti <xref:System.Windows.Controls.Primitives.Popup> si verifica quando si incontra un bordo dello schermo:  
  
- Il popup si riallinea lungo il bordo <xref:System.Windows.Controls.Primitives.Popup>dello schermo che nasconderebbe il file .  
  
- Il popup usa un punto di allineamento diverso.  
  
- Il popup usa un'origine di destinazione e un punto di allineamento diversi.  
  
 Tali opzioni vengono descritte più avanti in questa sezione.  
  
 Il comportamento <xref:System.Windows.Controls.Primitives.Popup> di quando incontra un bordo dello schermo <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> dipende dal valore della proprietà e dal bordo dello schermo rilevato dal popup. Nella tabella seguente viene riepilogato il comportamento quando <xref:System.Windows.Controls.Primitives.Popup> viene rilevato un bordo dello schermo per ogni <xref:System.Windows.Controls.Primitives.PlacementMode> valore.  
  
|PlacementMode|Bordo superiore|Bordo inferiore|Bordo sinistro|Bordo destro|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Allineamento al bordo superiore.|Il punto di allineamento popup passa <xref:System.Windows.Controls.Primitives.Popup>all'angolo inferiore sinistro del file .|Allineamento al bordo sinistro.|Il punto di allineamento popup passa <xref:System.Windows.Controls.Primitives.Popup>all'angolo superiore destro del file .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione <xref:System.Windows.Controls.Primitives.Popup>e il punto di allineamento popup viene modificato nell'angolo inferiore sinistro dell'oggetto .|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|L'origine di destinazione viene modificata nell'angolo superiore destro dell'area di destinazione <xref:System.Windows.Controls.Primitives.Popup>e il punto di allineamento popup viene modificato nell'angolo superiore sinistro dell'oggetto .|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Allineamento al bordo superiore.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione (i limiti del puntatore del mouse) e il punto di allineamento popup viene modificato nell'angolo inferiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Allineamento al bordo superiore.|Il punto di allineamento popup passa <xref:System.Windows.Controls.Primitives.Popup>all'angolo inferiore sinistro del file .|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Allineamento al bordo superiore.|Il punto di allineamento popup passa <xref:System.Windows.Controls.Primitives.Popup>all'angolo inferiore sinistro del file .|Allineamento al bordo sinistro.|Il punto di allineamento viene modificato nell'angolo superiore destro del controllo Popup.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Allineamento al bordo superiore.|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|L'origine di destinazione viene modificata nell'angolo superiore sinistro dell'area di destinazione <xref:System.Windows.Controls.Primitives.Popup>e il punto di allineamento popup viene modificato nell'angolo superiore destro dell'oggetto .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|L'origine di destinazione viene modificata nell'angolo inferiore sinistro dell'area di destinazione <xref:System.Windows.Controls.Primitives.Popup>e il punto di allineamento popup viene modificato nell'angolo superiore sinistro dell'oggetto . In effetti, questo è <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> lo <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>stesso di quando è .|Allineamento al bordo inferiore.|Allineamento al bordo sinistro.|Allineamento al bordo destro.|  
  
### <a name="aligning-to-the-screen-edge"></a>Allineamento al bordo dello schermo  
 Un <xref:System.Windows.Controls.Primitives.Popup> può allinearsi al bordo dello schermo riposizionandosi in modo che l'intero <xref:System.Windows.Controls.Primitives.Popup> sia visibile sullo schermo.  In questo caso, la distanza tra l'origine di destinazione <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>e il punto di allineamento popup potrebbe essere diversa dai valori di e . Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>è <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> o , l'elemento si allinea a ogni bordo dello schermo.  Ad esempio, si <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> supponga <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> che <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> un oggetto sia impostato su e impostato su 100.For example, assume that a has set to and set to 100.  Se il bordo inferiore dello schermo nasconde <xref:System.Windows.Controls.Primitives.Popup>tutto <xref:System.Windows.Controls.Primitives.Popup> o parte di esso , il si riposiziona lungo il bordo inferiore dello schermo e la distanza verticale tra l'origine di destinazione e il punto di allineamento popup è inferiore a 100. La figura seguente illustra questa situazione.  
  
 ![Popup allineato al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup allinea al bordo dello schermo.")
  
### <a name="changing-the-popup-alignment-point"></a>Modifica del punto di allineamento del controllo Popup  
 Se <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>è <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>o , il punto di allineamento popup cambia quando il popup rileva il bordo inferiore o destro dello schermo.  
  
 Nella figura seguente viene illustrato che quando il bordo <xref:System.Windows.Controls.Primitives.Popup>inferiore dello schermo nasconde tutto o <xref:System.Windows.Controls.Primitives.Popup>parte di , il punto di allineamento popup è l'angolo inferiore sinistro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup incontra il bordo inferiore dello schermo e modifica il punto di allineamento popup.")  

 Nella figura seguente viene <xref:System.Windows.Controls.Primitives.Popup> illustrato che quando l'oggetto è nascosto dal bordo destro <xref:System.Windows.Controls.Primitives.Popup>dello schermo, il punto di allineamento popup è l'angolo superiore destro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo dello schermo](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup incontra il bordo destro dello schermo e cambia il punto di allineamento popup.")
  
 Se <xref:System.Windows.Controls.Primitives.Popup> si incontrano i bordi inferiore e destro dello schermo, il <xref:System.Windows.Controls.Primitives.Popup>punto di allineamento popup è l'angolo inferiore destro del file .  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Modifica dell'origine di destinazione e del punto di allineamento del controllo Popup  
 Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>è <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, o , l'origine di destinazione e il punto di allineamento popup cambiano se viene rilevato un determinato bordo dello schermo.  Il bordo dello schermo che determina <xref:System.Windows.Controls.Primitives.PlacementMode> la modifica della posizione dipende dal valore.  
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> illustrato <xref:System.Windows.Controls.Primitives.Popup> che quando si trova e incontra il bordo inferiore dello schermo, l'origine di destinazione è <xref:System.Windows.Controls.Primitives.Popup>l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento popup è l'angolo inferiore sinistro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo inferiore dello schermo](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Il posizionamento è Bottom e il popup rileva il bordo inferiore dello schermo.")
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Left> illustrato <xref:System.Windows.Controls.Primitives.Popup> che quando si trova e incontra il bordo sinistro dello schermo, l'origine di destinazione è <xref:System.Windows.Controls.Primitives.Popup>l'angolo superiore destro dell'area di destinazione e il punto di allineamento popup è l'angolo superiore sinistro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo sinistro dello schermo](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Il posizionamento è Left e il popup rileva il bordo sinistro dello schermo.")  
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Right> illustrato <xref:System.Windows.Controls.Primitives.Popup> che quando si trova e incontra il bordo destro dello schermo, l'origine di destinazione è <xref:System.Windows.Controls.Primitives.Popup>l'angolo superiore sinistro dell'area di destinazione e il punto di allineamento popup è l'angolo superiore destro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo destro dello schermo](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Il posizionamento è a destra e il popup incontra il bordo destro dello schermo.")  

 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Top> illustrato <xref:System.Windows.Controls.Primitives.Popup> che quando si trova e incontra il bordo superiore dello schermo, l'origine di destinazione è <xref:System.Windows.Controls.Primitives.Popup>l'angolo inferiore sinistro dell'area di destinazione e il punto di allineamento popup è l'angolo superiore sinistro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al bordo superiore dello schermo](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Il posizionamento è Superiore e il popup rileva il bordo superiore dello schermo.")  
  
 Nella figura seguente <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> viene <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> illustrato <xref:System.Windows.Controls.Primitives.Popup> che quando si trova e incontra il bordo inferiore dello schermo, l'origine di destinazione è l'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>dell'area di destinazione (i limiti del puntatore del mouse) e il punto di allineamento popup è l'angolo inferiore sinistro dell'oggetto .  
  
 ![Nuovo punto di allineamento dovuto al mouse vicino al bordo dello schermo](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Posizionamento è Mouse e il popup rileva il bordo inferiore dello schermo.")
  
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare l'origine di destinazione <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> e <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>il punto di allineamento popup impostando la proprietà su . Definire quindi <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> un delegato che restituisce un set di possibili punti <xref:System.Windows.Controls.Primitives.Popup>di posizionamento e assi primari (in ordine di preferenza) per il file . Viene selezionato il punto che <xref:System.Windows.Controls.Primitives.Popup> mostra la parte più grande di .  La posizione <xref:System.Windows.Controls.Primitives.Popup> dell'oggetto viene <xref:System.Windows.Controls.Primitives.Popup> regolata automaticamente se l'oggetto è nascosto dal bordo dello schermo. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Vedere anche

- [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS) (Esempio di posizionamento di un controllo Popup)
