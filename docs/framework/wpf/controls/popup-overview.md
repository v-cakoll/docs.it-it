---
title: Cenni preliminari sul controllo Popup
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: c9261e2151f116b46a0c25d8dc775bf41bf932b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557576"
---
# <a name="popup-overview"></a>Cenni preliminari sul controllo Popup
Il <xref:System.Windows.Controls.Primitives.Popup> controllo consente di visualizzare il contenuto in una finestra separata che può essere spostata rispetto alla finestra dell'applicazione corrente relativo a un determinato elemento o coordinata dello schermo. Questo argomento vengono presentate le <xref:System.Windows.Controls.Primitives.Popup> controllare e fornisce informazioni sul relativo utilizzo.  
  
 
  
<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Definizione di un controllo Popup  
 Oggetto <xref:System.Windows.Controls.Primitives.Popup> controllo Visualizza il contenuto in una finestra separata relativa a un elemento o un punto dello schermo. Quando il <xref:System.Windows.Controls.Primitives.Popup> è visibile, il <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> è impostata su `true`.  
  
> [!NOTE]
>  Oggetto <xref:System.Windows.Controls.Primitives.Popup> non viene aperto automaticamente quando si sposta il puntatore del mouse sul relativo oggetto padre. Se si desidera un <xref:System.Windows.Controls.Primitives.Popup> per aprire automaticamente, utilizzare il <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ToolTipService> classe. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Creazione di un popup  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.Primitives.Popup> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Button> controllo. Poiché un <xref:System.Windows.Controls.Button> può avere un solo elemento figlio, in questo esempio viene inserito il testo per il <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.Primitives.Popup> controlli in un <xref:System.Windows.Controls.StackPanel>. Il contenuto del <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato un <xref:System.Windows.Controls.TextBlock> controllo che visualizza il testo in una finestra separata che può essere spostata rispetto alla finestra dell'applicazione accanto al relativo <xref:System.Windows.Controls.Button> controllo.  
  
 [!code-xaml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Controlli che implementano un controllo Popup  
 È possibile compilare <xref:System.Windows.Controls.Primitives.Popup> controlli in altri controlli. Implementano i seguenti controlli di <xref:System.Windows.Controls.Primitives.Popup> controllo per utilizzi specifici:  
  
-   <xref:System.Windows.Controls.ToolTip>. Se si desidera creare una descrizione per un elemento, utilizzare il <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ToolTipService> classi. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu>. Se si desidera creare un menu di scelta rapida per un elemento, utilizzare il <xref:System.Windows.Controls.ContextMenu> controllo. Per altre informazioni, vedere [Cenni preliminari sull'oggetto ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox>. Se si desidera creare un controllo di selezione che include una casella di riepilogo che può essere visualizzato o nascosto, utilizzare il <xref:System.Windows.Controls.ComboBox> controllo.  
  
-   <xref:System.Windows.Controls.Expander>. Se si desidera creare un controllo che visualizza un'intestazione con un'area comprimibile che visualizza il contenuto, utilizzare il <xref:System.Windows.Controls.Expander> controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo Expander](../../../../docs/framework/wpf/controls/expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Comportamento e aspetto del controllo Popup  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo fornisce funzionalità che consente di personalizzare il comportamento e l'aspetto. Ad esempio, è possibile impostare il comportamento di aperto e chiusura, animazione, gli effetti di opacità e bitmap e <xref:System.Windows.Controls.Primitives.Popup> dimensioni e posizione.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Comportamento di apertura e di chiusura  
 Oggetto <xref:System.Windows.Controls.Primitives.Popup> controllo consente di visualizzare il contenuto quando il <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> è impostata su `true`. Per impostazione predefinita, <xref:System.Windows.Controls.Primitives.Popup> resta aperto finché la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> è impostata su `false`. Tuttavia, è possibile modificare il comportamento predefinito impostando il <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> proprietà `false`. Quando si imposta questa proprietà su `false`, <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto ha lo stato mouse capture. Il <xref:System.Windows.Controls.Primitives.Popup> perde lo stato mouse capture e la finestra viene chiusa quando si verifica un evento del mouse all'esterno di <xref:System.Windows.Controls.Primitives.Popup> finestra.  
  
 Il <xref:System.Windows.Controls.Primitives.Popup.Opened> e <xref:System.Windows.Controls.Primitives.Popup.Closed> gli eventi vengono generati quando il <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto è aperta o chiusa.  
  
<a name="Animation"></a>   
### <a name="animation"></a>Animazione  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo include il supporto incorporato per le animazioni che vengono generalmente associate a comportamenti quali dissolvenza in entrata e scorrimento in entrata. È possibile attivare queste animazioni impostando il <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> proprietà per un <xref:System.Windows.Controls.Primitives.PopupAnimation> valore di enumerazione. Per <xref:System.Windows.Controls.Primitives.Popup> animazioni funzionino correttamente, è necessario impostare il <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`.  
  
 È inoltre possibile applicare animazioni come <xref:System.Windows.Media.Animation.Storyboard> per il <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Effetti di opacità e bitmap  
 Il <xref:System.Windows.UIElement.Opacity%2A> proprietà per un <xref:System.Windows.Controls.Primitives.Popup> controllo non ha alcun effetto sul relativo contenuto. Per impostazione predefinita, il <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto è opaco. Per creare un oggetto trasparente <xref:System.Windows.Controls.Primitives.Popup>, impostare il <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`.  
  
 Il contenuto di un <xref:System.Windows.Controls.Primitives.Popup> non eredita gli effetti bitmap, ad esempio <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, che vengono impostati direttamente sul <xref:System.Windows.Controls.Primitives.Popup> controllo o su qualsiasi altro elemento della finestra padre. Per gli effetti bitmap nel contenuto di un <xref:System.Windows.Controls.Primitives.Popup>, è necessario impostare l'effetto bitmap direttamente sul contenuto. Ad esempio, se l'elemento figlio di un <xref:System.Windows.Controls.Primitives.Popup> è un <xref:System.Windows.Controls.StackPanel>, impostare l'effetto bitmap per il <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Dimensioni del controllo Popup  
 Per impostazione predefinita, un <xref:System.Windows.Controls.Primitives.Popup> viene automaticamente ridimensionato in base al contenuto. Quando si verifica il ridimensionamento automatico, alcuni effetti bitmap possono essere nascosti perché le dimensioni predefinite dell'area dello schermo definito per il <xref:System.Windows.Controls.Primitives.Popup> contenuto non forniscono spazio sufficiente per la visualizzazione degli effetti bitmap.  
  
 <xref:System.Windows.Controls.Primitives.Popup> il contenuto può anche essere nascosto quando si imposta un <xref:System.Windows.UIElement.RenderTransform%2A> sul contenuto. In questo scenario, parte del contenuto può essere nascosto se il contenuto di trasformato <xref:System.Windows.Controls.Primitives.Popup> si estende oltre l'area dell'originale <xref:System.Windows.Controls.Primitives.Popup>. Se un effetto bitmap o la trasformazione richiede più spazio, è possibile definire un margine intorno il <xref:System.Windows.Controls.Primitives.Popup> contenuto per fornire più aree per il controllo.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Definizione della posizione di un controllo Popup  
 È possibile posizionare un popup impostando il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> proprietà. Per altre informazioni, vedere [Comportamento del controllo Popup in relazione al posizionamento](../../../../docs/framework/wpf/controls/popup-placement-behavior.md). Quando <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sullo schermo, riposizionato se non viene riposizionata padre.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> controllo specificando un set di coordinate che sono relativi il <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> in cui si desidera il <xref:System.Windows.Controls.Primitives.Popup> da visualizzare.  
  
 Per personalizzare il posizionamento, impostare il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Quindi definire un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato che restituisce un set di possibili punti di posizionamento e assi primari (in ordine di preferenza) per il <xref:System.Windows.Controls.Primitives.Popup>. Il punto che visualizza la maggior parte del <xref:System.Windows.Controls.Primitives.Popup> viene selezionata automaticamente. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Controllo Popup e struttura ad albero visuale  
 Oggetto <xref:System.Windows.Controls.Primitives.Popup> controllo non dispone di un proprio struttura ad albero visuale; restituisce invece una dimensione pari a 0 (zero) quando il <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> metodo per <xref:System.Windows.Controls.Primitives.Popup> viene chiamato. Tuttavia, quando si imposta la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà di <xref:System.Windows.Controls.Primitives.Popup> a `true`, viene creata una nuova finestra con il proprio struttura ad albero visuale. La nuova finestra contiene il <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto di <xref:System.Windows.Controls.Primitives.Popup>. La larghezza e l'altezza della nuova finestra non possono superare il 75 per cento della larghezza o dell'altezza dello schermo.  
  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo mantiene un riferimento al relativo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto come elemento figlio logico. Quando si crea la nuova finestra, il contenuto di <xref:System.Windows.Controls.Primitives.Popup> diventa un elemento figlio visivo della finestra e resta il figlio logico di <xref:System.Windows.Controls.Primitives.Popup>. Al contrario, <xref:System.Windows.Controls.Primitives.Popup> rimane l'elemento padre logico di relativo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Primitives.Popup>  
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>  
 <xref:System.Windows.Controls.Primitives.PlacementMode>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
