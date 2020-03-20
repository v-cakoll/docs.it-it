---
title: Cenni preliminari sul controllo Popup
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185945"
---
# <a name="popup-overview"></a>Cenni preliminari sul controllo Popup
Il <xref:System.Windows.Controls.Primitives.Popup> controllo consente di visualizzare il contenuto in una finestra separata che si sposta sulla finestra dell'applicazione corrente rispetto a un elemento designato o a una coordinata dello schermo. In questo argomento <xref:System.Windows.Controls.Primitives.Popup> viene presentato il controllo e vengono fornite informazioni sul relativo utilizzo.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Definizione di un controllo Popup  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo visualizza il contenuto in una finestra separata relativa a un elemento o un punto sullo schermo. Quando <xref:System.Windows.Controls.Primitives.Popup> l'oggetto <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> è visibile, `true`la proprietà è impostata su .  
  
> [!NOTE]
> Un <xref:System.Windows.Controls.Primitives.Popup> oggetto non si apre automaticamente quando il puntatore del mouse si sposta sull'oggetto padre. Se si <xref:System.Windows.Controls.Primitives.Popup> desidera che un <xref:System.Windows.Controls.ToolTip> oggetto <xref:System.Windows.Controls.ToolTipService> si apra automaticamente, utilizzare la classe o . Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Creazione di un popup  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Primitives.Popup> illustrato come definire un <xref:System.Windows.Controls.Button> controllo che è l'elemento figlio di un controllo. Poiché <xref:System.Windows.Controls.Button> un oggetto può avere un solo elemento <xref:System.Windows.Controls.Button> figlio, in questo esempio il testo per i <xref:System.Windows.Controls.Primitives.Popup> controlli e e viene posizionato in un <xref:System.Windows.Controls.StackPanel>oggetto . Il contenuto <xref:System.Windows.Controls.Primitives.Popup> di viene <xref:System.Windows.Controls.TextBlock> visualizzato in un controllo , che visualizza il testo in <xref:System.Windows.Controls.Button> una finestra separata che si sposta sulla finestra dell'applicazione vicino al controllo correlato.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Controlli che implementano un controllo Popup  
 È possibile <xref:System.Windows.Controls.Primitives.Popup> compilare controlli in altri controlli. I controlli seguenti <xref:System.Windows.Controls.Primitives.Popup> implementano il controllo per usi specifici:  
  
- <xref:System.Windows.Controls.ToolTip>. Se si desidera creare una descrizione comando <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> per un elemento, utilizzare le classi e . Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Se si desidera creare un menu di <xref:System.Windows.Controls.ContextMenu> scelta rapida per un elemento, utilizzare il controllo . Per altre informazioni, vedere [Cenni preliminari sull'oggetto ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Se si desidera creare un controllo di selezione con una casella di riepilogo <xref:System.Windows.Controls.ComboBox> a discesa che può essere visualizzata o nascosta, utilizzare il controllo .  
  
- <xref:System.Windows.Controls.Expander>. Se si desidera creare un controllo che visualizza un'intestazione con un'area comprimibile che visualizza il contenuto, utilizzare il <xref:System.Windows.Controls.Expander> controllo . Per altre informazioni, vedere [Cenni preliminari sul controllo Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Comportamento e aspetto del controllo Popup  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo fornisce funzionalità che consentono di personalizzarne il comportamento e l'aspetto. Ad esempio, è possibile impostare il comportamento di apertura e <xref:System.Windows.Controls.Primitives.Popup> chiusura, l'animazione, l'opacità e gli effetti bitmap, nonché le dimensioni e la posizione.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Comportamento di apertura e di chiusura  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo visualizza il <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> contenuto quando `true`la proprietà è impostata su . Per impostazione <xref:System.Windows.Controls.Primitives.Popup> predefinita, <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> rimane aperto `false`finché la proprietà non viene impostata su . Tuttavia, è possibile modificare il <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> comportamento `false`predefinito impostando la proprietà su . Quando si imposta `false`questa <xref:System.Windows.Controls.Primitives.Popup> proprietà su , la finestra del contenuto ha mouse capture. Il <xref:System.Windows.Controls.Primitives.Popup> perde mouse capture e la finestra si chiude <xref:System.Windows.Controls.Primitives.Popup> quando si verifica un evento del mouse all'esterno della finestra.  
  
 Gli <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> eventi e vengono <xref:System.Windows.Controls.Primitives.Popup> generati quando la finestra del contenuto è aperta o chiusa.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animazione  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo include il supporto incorporato per le animazioni che sono in genere associate a comportamenti come dissolvenza in entrata e scorrimento in entrata. È possibile attivare queste <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> animazioni <xref:System.Windows.Controls.Primitives.PopupAnimation> impostando la proprietà su un valore di enumerazione. Affinché <xref:System.Windows.Controls.Primitives.Popup> le animazioni funzionino <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> correttamente, è necessario impostare la proprietà su `true`.  
  
 È inoltre possibile <xref:System.Windows.Media.Animation.Storyboard> applicare <xref:System.Windows.Controls.Primitives.Popup> animazioni come al controllo.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Effetti di opacità e bitmap  
 La <xref:System.Windows.UIElement.Opacity%2A> proprietà <xref:System.Windows.Controls.Primitives.Popup> per un controllo non ha alcun effetto sul relativo contenuto. Per impostazione <xref:System.Windows.Controls.Primitives.Popup> predefinita, la finestra del contenuto è opaca. Per creare <xref:System.Windows.Controls.Primitives.Popup>un oggetto <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> trasparente, impostare la proprietà su `true`.  
  
 Il contenuto <xref:System.Windows.Controls.Primitives.Popup> di un oggetto non <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>eredita effetti bitmap, <xref:System.Windows.Controls.Primitives.Popup> ad esempio , impostati direttamente sul controllo o su qualsiasi altro elemento nella finestra padre. Affinché gli effetti bitmap vengano visualizzati sul contenuto di un <xref:System.Windows.Controls.Primitives.Popup>oggetto , è necessario impostare l'effetto bitmap direttamente sul relativo contenuto. Ad esempio, se l'elemento figlio di a <xref:System.Windows.Controls.Primitives.Popup> è un <xref:System.Windows.Controls.StackPanel>, impostare l'effetto bitmap sul file <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Dimensioni del controllo Popup  
 Per impostazione <xref:System.Windows.Controls.Primitives.Popup> predefinita, un oggetto viene ridimensionato automaticamente in base al contenuto. Quando si verifica il ridimensionamento automatico, alcuni effetti bitmap potrebbero essere nascosti <xref:System.Windows.Controls.Primitives.Popup> perché le dimensioni predefinite dell'area dello schermo definita per il contenuto non forniscono spazio sufficiente per la visualizzazione degli effetti bitmap.  
  
 <xref:System.Windows.Controls.Primitives.Popup>contenuto può anche essere oscurato quando <xref:System.Windows.UIElement.RenderTransform%2A> si imposta un sul contenuto. In questo scenario, parte del contenuto potrebbe essere <xref:System.Windows.Controls.Primitives.Popup> nascosto se il <xref:System.Windows.Controls.Primitives.Popup>contenuto della trasformazione si estende oltre l'area dell'originale. Se un effetto bitmap o una trasformazione richiede <xref:System.Windows.Controls.Primitives.Popup> più spazio, è possibile definire un margine intorno al contenuto per fornire più area per il controllo.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definizione della posizione di un controllo Popup  
 È possibile posizionare un <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>popup <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>impostando <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> le proprietà , , , e . Per altre informazioni, vedere [Comportamento del controllo Popup in relazione al posizionamento](popup-placement-behavior.md). Quando <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sullo schermo, non viene riposizionato se l'elemento padre viene riposizionato.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare la <xref:System.Windows.Controls.Primitives.Popup> posizione di un controllo specificando un <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> set di <xref:System.Windows.Controls.Primitives.Popup> coordinate relative al punto in cui si desidera visualizzare l'oggetto .  
  
 Per personalizzare il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> posizionamento, impostate la proprietà su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definire quindi <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> un delegato che restituisce un set di possibili punti <xref:System.Windows.Controls.Primitives.Popup>di posizionamento e assi primari (in ordine di preferenza) per il file . Il punto che mostra la <xref:System.Windows.Controls.Primitives.Popup> parte più grande del viene selezionato automaticamente. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Controllo Popup e struttura ad albero visuale  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo non dispone di una propria struttura ad albero visuale. restituisce invece una dimensione pari <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> a <xref:System.Windows.Controls.Primitives.Popup> 0 (zero) quando viene chiamato il metodo per. Tuttavia, quando <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> si <xref:System.Windows.Controls.Primitives.Popup> imposta `true`la proprietà di , viene creata una nuova finestra con la propria struttura ad albero visuale. La nuova finestra <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contiene <xref:System.Windows.Controls.Primitives.Popup>il contenuto di . La larghezza e l'altezza della nuova finestra non possono superare il 75 per cento della larghezza o dell'altezza dello schermo.  
  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo mantiene un <xref:System.Windows.Controls.Primitives.Popup.Child%2A> riferimento al relativo contenuto come elemento figlio logico. Quando viene creata la nuova <xref:System.Windows.Controls.Primitives.Popup> finestra, il contenuto di diventa un <xref:System.Windows.Controls.Primitives.Popup>elemento figlio visivo della finestra e rimane l'elemento figlio logico di . Al contrario, <xref:System.Windows.Controls.Primitives.Popup> rimane l'elemento padre logico del relativo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Argomenti relativi alle procedure](popup-how-to-topics.md)
- [Argomenti relativi alle procedure](tooltip-how-to-topics.md)
