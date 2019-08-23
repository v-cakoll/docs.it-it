---
title: Cenni preliminari sul controllo Popup
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 7e6977737d362fd0df6321702bb8a1ac6cad66e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951436"
---
# <a name="popup-overview"></a>Cenni preliminari sul controllo Popup
Il <xref:System.Windows.Controls.Primitives.Popup> controllo consente di visualizzare il contenuto in una finestra separata che viene spostata sulla finestra dell'applicazione corrente rispetto a un elemento designato o a una coordinata dello schermo. In questo argomento viene <xref:System.Windows.Controls.Primitives.Popup> introdotto il controllo e vengono fornite informazioni sul relativo utilizzo.  

<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Definizione di un controllo Popup  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo Visualizza il contenuto in una finestra separata rispetto a un elemento o a un punto sullo schermo. Quando è visibile, la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà viene impostata su `true`. <xref:System.Windows.Controls.Primitives.Popup>  
  
> [!NOTE]
> Un <xref:System.Windows.Controls.Primitives.Popup> oggetto non viene aperto automaticamente quando il puntatore del mouse viene spostato sul relativo oggetto padre. Se si desidera che <xref:System.Windows.Controls.Primitives.Popup> un oggetto venga aperto automaticamente, <xref:System.Windows.Controls.ToolTip> utilizzare <xref:System.Windows.Controls.ToolTipService> la classe o. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Creazione di un popup  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.Primitives.Popup> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Button> controllo. Poiché un <xref:System.Windows.Controls.Button> oggetto può avere un solo elemento figlio, in questo esempio viene inserito il <xref:System.Windows.Controls.Button> testo per <xref:System.Windows.Controls.Primitives.Popup> i controlli e <xref:System.Windows.Controls.StackPanel>in un oggetto. Il contenuto di <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato in un <xref:System.Windows.Controls.TextBlock> controllo, che Visualizza il testo in una finestra separata che scorre sulla finestra dell'applicazione accanto al controllo correlato. <xref:System.Windows.Controls.Button>  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Controlli che implementano un controllo Popup  
 È possibile compilare <xref:System.Windows.Controls.Primitives.Popup> controlli in altri controlli. I controlli seguenti implementano <xref:System.Windows.Controls.Primitives.Popup> il controllo per usi specifici:  
  
- [https://login.microsoftonline.com/common/](<xref:System.Windows.Controls.ToolTip>). Se si desidera creare una descrizione comando per un elemento, utilizzare le <xref:System.Windows.Controls.ToolTip> classi <xref:System.Windows.Controls.ToolTipService> e. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
- [https://login.microsoftonline.com/common/](<xref:System.Windows.Controls.ContextMenu>). Se si vuole creare un menu di scelta rapida per un elemento, usare <xref:System.Windows.Controls.ContextMenu> il controllo. Per altre informazioni, vedere [Cenni preliminari sull'oggetto ContextMenu](contextmenu-overview.md).  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Controls.ComboBox>). Se si desidera creare un controllo di selezione con una casella di riepilogo a discesa che può essere visualizzata o nascosta, utilizzare il <xref:System.Windows.Controls.ComboBox> controllo.  
  
- <xref:System.Windows.Controls.Expander>. Se si vuole creare un controllo che visualizza un'intestazione con un'area comprimibile che Visualizza il contenuto, <xref:System.Windows.Controls.Expander> usare il controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Comportamento e aspetto del controllo Popup  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo fornisce funzionalità che consentono di personalizzare il comportamento e l'aspetto. Ad esempio, è possibile impostare il comportamento di apertura e chiusura, l'animazione, l'opacità <xref:System.Windows.Controls.Primitives.Popup> e gli effetti bitmap, nonché le dimensioni e la posizione.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Comportamento di apertura e di chiusura  
 Il <xref:System.Windows.Controls.Primitives.Popup> contenuto di un controllo viene visualizzato <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> quando la proprietà è `true`impostata su. Per impostazione predefinita <xref:System.Windows.Controls.Primitives.Popup> , rimane aperto fino <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> a quando la proprietà `false`non viene impostata su. Tuttavia, è possibile modificare il comportamento predefinito impostando la <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> proprietà su `false`. Quando si imposta questa proprietà su `false`, la <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto ha lo stato mouse capture. Perde <xref:System.Windows.Controls.Primitives.Popup> il mouse capture e la finestra si chiude quando si verifica un evento del <xref:System.Windows.Controls.Primitives.Popup> mouse all'esterno della finestra.  
  
 Gli <xref:System.Windows.Controls.Primitives.Popup.Opened> eventi <xref:System.Windows.Controls.Primitives.Popup.Closed> e vengono generati quando la <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto è aperta o chiusa.  
  
<a name="Animation"></a>   
### <a name="animation"></a>Animazione  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo dispone del supporto incorporato per le animazioni che in genere sono associate a comportamenti come dissolvenza in entrata e scorrimento. È possibile attivare queste animazioni impostando la <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> proprietà su un <xref:System.Windows.Controls.Primitives.PopupAnimation> valore di enumerazione. Per <xref:System.Windows.Controls.Primitives.Popup> il corretto funzionamento delle animazioni, è necessario impostare <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> la proprietà `true`su.  
  
 È anche possibile applicare animazioni come <xref:System.Windows.Media.Animation.Storyboard> il <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Effetti di opacità e bitmap  
 La <xref:System.Windows.UIElement.Opacity%2A> proprietà di un <xref:System.Windows.Controls.Primitives.Popup> controllo non ha alcun effetto sul contenuto. Per impostazione predefinita, <xref:System.Windows.Controls.Primitives.Popup> la finestra del contenuto è opaca. Per creare un oggetto <xref:System.Windows.Controls.Primitives.Popup>trasparente, impostare <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> la proprietà `true`su.  
  
 Il contenuto di un <xref:System.Windows.Controls.Primitives.Popup> oggetto non eredita gli effetti bitmap, <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>ad esempio, impostati direttamente sul <xref:System.Windows.Controls.Primitives.Popup> controllo o su qualsiasi altro elemento nella finestra padre. Per visualizzare gli effetti bitmap sul contenuto di un <xref:System.Windows.Controls.Primitives.Popup>, è necessario impostare l'effetto bitmap direttamente sul contenuto. Se, ad esempio, l'elemento figlio <xref:System.Windows.Controls.Primitives.Popup> di un <xref:System.Windows.Controls.StackPanel>oggetto è, impostare <xref:System.Windows.Controls.StackPanel>l'effetto bitmap su.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Dimensioni del controllo Popup  
 Per impostazione predefinita, <xref:System.Windows.Controls.Primitives.Popup> un oggetto viene ridimensionato automaticamente in base al relativo contenuto. Quando si verifica il ridimensionamento automatico, è possibile che alcuni effetti bitmap siano nascosti perché le dimensioni predefinite dell'area dello schermo definite <xref:System.Windows.Controls.Primitives.Popup> per il contenuto non forniscono spazio sufficiente per la visualizzazione degli effetti bitmap.  
  
 <xref:System.Windows.Controls.Primitives.Popup>il contenuto può anche essere nascosto quando si imposta un <xref:System.Windows.UIElement.RenderTransform%2A> oggetto sul contenuto. In questo scenario alcuni contenuti potrebbero essere nascosti se il contenuto della trasformazione <xref:System.Windows.Controls.Primitives.Popup> si estende oltre l'area del originale. <xref:System.Windows.Controls.Primitives.Popup> Se per un effetto bitmap o una trasformazione è necessario più spazio, è possibile definire un <xref:System.Windows.Controls.Primitives.Popup> margine intorno al contenuto per fornire più area per il controllo.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Definizione della posizione di un controllo Popup  
 È possibile posizionare un popup impostando le <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>proprietà <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Per altre informazioni, vedere [Comportamento del controllo Popup in relazione al posizionamento](popup-placement-behavior.md). Quando <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sullo schermo, non viene riposizionato se il relativo padre viene riposizionato.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> controllo specificando un set di coordinate relative all'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup> in cui si desidera che venga visualizzato.  
  
 Per personalizzare la selezione host, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> impostare la <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>proprietà su. Definire quindi un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato che restituisce un set di punti di posizionamento possibili e assi primari (in ordine di preferenza) <xref:System.Windows.Controls.Primitives.Popup>per. Il punto che mostra la parte più grande di <xref:System.Windows.Controls.Primitives.Popup> viene selezionato automaticamente. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Controllo Popup e struttura ad albero visuale  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo non dispone di una propria struttura ad albero visuale. restituisce invece una dimensione pari a 0 (zero <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> ) quando <xref:System.Windows.Controls.Primitives.Popup> viene chiamato il metodo per. Tuttavia, quando si imposta la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà di <xref:System.Windows.Controls.Primitives.Popup> su `true`, viene creata una nuova finestra con la relativa struttura ad albero visuale. La nuova finestra contiene il <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto di <xref:System.Windows.Controls.Primitives.Popup>. La larghezza e l'altezza della nuova finestra non possono superare il 75 per cento della larghezza o dell'altezza dello schermo.  
  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo mantiene un riferimento <xref:System.Windows.Controls.Primitives.Popup.Child%2A> al contenuto come figlio logico. Quando viene creata la nuova finestra, il contenuto di <xref:System.Windows.Controls.Primitives.Popup> diventa un elemento figlio visivo della finestra e rimane l'elemento figlio logico <xref:System.Windows.Controls.Primitives.Popup>di. Viceversa, <xref:System.Windows.Controls.Primitives.Popup> rimane l'elemento padre logico del relativo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Procedure relative alle proprietà](popup-how-to-topics.md)
- [Procedure relative alle proprietà](tooltip-how-to-topics.md)
