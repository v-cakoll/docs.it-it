---
title: Cenni preliminari sul controllo Popup
description: Informazioni sul controllo Windows Presentation Foundation popup, che fornisce un modo per visualizzare il contenuto in una finestra che si sposta sull'applicazione corrente.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 84eaddc53366df6d1da1a0a005d3618268f8cce2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167532"
---
# <a name="popup-overview"></a>Cenni preliminari sul controllo Popup
Il <xref:System.Windows.Controls.Primitives.Popup> controllo consente di visualizzare il contenuto in una finestra separata che viene spostata sulla finestra dell'applicazione corrente rispetto a un elemento designato o a una coordinata dello schermo. In questo argomento viene introdotto il <xref:System.Windows.Controls.Primitives.Popup> controllo e vengono fornite informazioni sul relativo utilizzo.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Definizione di un controllo Popup  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo Visualizza il contenuto in una finestra separata rispetto a un elemento o a un punto sullo schermo. Quando <xref:System.Windows.Controls.Primitives.Popup> è visibile, la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà viene impostata su `true` .  
  
> [!NOTE]
> Un <xref:System.Windows.Controls.Primitives.Popup> oggetto non viene aperto automaticamente quando il puntatore del mouse viene spostato sul relativo oggetto padre. Se si desidera che un oggetto <xref:System.Windows.Controls.Primitives.Popup> venga aperto automaticamente, utilizzare la <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> classe o. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Creazione di un popup  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.Primitives.Popup> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Button> controllo. Poiché un oggetto <xref:System.Windows.Controls.Button> può avere un solo elemento figlio, in questo esempio viene inserito il testo per i <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.Popup> controlli e in un oggetto <xref:System.Windows.Controls.StackPanel> . Il contenuto di <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato in un <xref:System.Windows.Controls.TextBlock> controllo, che Visualizza il testo in una finestra separata che scorre sulla finestra dell'applicazione accanto al controllo correlato <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Controlli che implementano un controllo Popup  
 È possibile compilare <xref:System.Windows.Controls.Primitives.Popup> controlli in altri controlli. I controlli seguenti implementano il <xref:System.Windows.Controls.Primitives.Popup> controllo per usi specifici:  
  
- <xref:System.Windows.Controls.ToolTip>. Se si desidera creare una descrizione comando per un elemento, utilizzare le <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> classi e. Per altre informazioni, vedere [Panoramica sul controllo ToolTip](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Se si vuole creare un menu di scelta rapida per un elemento, usare il <xref:System.Windows.Controls.ContextMenu> controllo. Per altre informazioni, vedere [Cenni preliminari sull'oggetto ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Se si desidera creare un controllo di selezione con una casella di riepilogo a discesa che può essere visualizzata o nascosta, utilizzare il <xref:System.Windows.Controls.ComboBox> controllo.  
  
- <xref:System.Windows.Controls.Expander>. Se si vuole creare un controllo che visualizza un'intestazione con un'area comprimibile che Visualizza il contenuto, usare il <xref:System.Windows.Controls.Expander> controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo Expander](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Comportamento e aspetto del controllo Popup  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo fornisce funzionalità che consentono di personalizzare il comportamento e l'aspetto. Ad esempio, è possibile impostare il comportamento di apertura e chiusura, l'animazione, l'opacità e gli effetti bitmap, nonché le <xref:System.Windows.Controls.Primitives.Popup> dimensioni e la posizione.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Comportamento di apertura e di chiusura  
 Il <xref:System.Windows.Controls.Primitives.Popup> contenuto di un controllo viene visualizzato quando la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà è impostata su `true` . Per impostazione predefinita, <xref:System.Windows.Controls.Primitives.Popup> rimane aperto fino a quando la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà non viene impostata su `false` . Tuttavia, è possibile modificare il comportamento predefinito impostando la <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> proprietà su `false` . Quando si imposta questa proprietà su `false` , la <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto ha lo stato mouse capture. <xref:System.Windows.Controls.Primitives.Popup>Perde il mouse capture e la finestra si chiude quando si verifica un evento del mouse all'esterno della <xref:System.Windows.Controls.Primitives.Popup> finestra.  
  
 Gli <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> eventi e vengono generati quando la <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto è aperta o chiusa.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animazione  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo dispone del supporto incorporato per le animazioni che in genere sono associate a comportamenti come dissolvenza in entrata e scorrimento. È possibile attivare queste animazioni impostando la <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> proprietà su un <xref:System.Windows.Controls.Primitives.PopupAnimation> valore di enumerazione. Per <xref:System.Windows.Controls.Primitives.Popup> il corretto funzionamento delle animazioni, è necessario impostare la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà su `true` .  
  
 È anche possibile applicare animazioni come <xref:System.Windows.Media.Animation.Storyboard> il <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Effetti di opacità e bitmap  
 La <xref:System.Windows.UIElement.Opacity%2A> proprietà di un <xref:System.Windows.Controls.Primitives.Popup> controllo non ha alcun effetto sul contenuto. Per impostazione predefinita, la <xref:System.Windows.Controls.Primitives.Popup> finestra del contenuto è opaca. Per creare un oggetto trasparente <xref:System.Windows.Controls.Primitives.Popup> , impostare la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà su `true` .  
  
 Il contenuto di un oggetto non <xref:System.Windows.Controls.Primitives.Popup> eredita gli effetti bitmap, ad esempio <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> , impostati direttamente sul <xref:System.Windows.Controls.Primitives.Popup> controllo o su qualsiasi altro elemento nella finestra padre. Per visualizzare gli effetti bitmap sul contenuto di un <xref:System.Windows.Controls.Primitives.Popup> , è necessario impostare l'effetto bitmap direttamente sul contenuto. Se, ad esempio, l'elemento figlio di un oggetto <xref:System.Windows.Controls.Primitives.Popup> è <xref:System.Windows.Controls.StackPanel> , impostare l'effetto bitmap su <xref:System.Windows.Controls.StackPanel> .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Dimensioni del controllo Popup  
 Per impostazione predefinita, un oggetto <xref:System.Windows.Controls.Primitives.Popup> viene ridimensionato automaticamente in base al relativo contenuto. Quando si verifica il ridimensionamento automatico, è possibile che alcuni effetti bitmap siano nascosti perché le dimensioni predefinite dell'area dello schermo definite per il <xref:System.Windows.Controls.Primitives.Popup> contenuto non forniscono spazio sufficiente per la visualizzazione degli effetti bitmap.  
  
 <xref:System.Windows.Controls.Primitives.Popup>il contenuto può anche essere nascosto quando si imposta un oggetto <xref:System.Windows.UIElement.RenderTransform%2A> sul contenuto. In questo scenario alcuni contenuti potrebbero essere nascosti se il contenuto della trasformazione si <xref:System.Windows.Controls.Primitives.Popup> estende oltre l'area del originale <xref:System.Windows.Controls.Primitives.Popup> . Se per un effetto bitmap o una trasformazione è necessario più spazio, è possibile definire un margine intorno al <xref:System.Windows.Controls.Primitives.Popup> contenuto per fornire più area per il controllo.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definizione della posizione di un controllo Popup  
 È possibile posizionare un popup impostando le <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> proprietà,, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> e <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Per altre informazioni, vedere [Comportamento del controllo Popup in relazione al posizionamento](popup-placement-behavior.md). Quando <xref:System.Windows.Controls.Primitives.Popup> viene visualizzato sullo schermo, non viene riposizionato se il relativo padre viene riposizionato.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Personalizzazione del posizionamento di un controllo Popup  
 È possibile personalizzare la posizione di un <xref:System.Windows.Controls.Primitives.Popup> controllo specificando un set di coordinate relative all'oggetto <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> in cui si desidera che <xref:System.Windows.Controls.Primitives.Popup> venga visualizzato.  
  
 Per personalizzare la selezione host, impostare la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> . Definire quindi un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato che restituisce un set di punti di posizionamento possibili e assi primari (in ordine di preferenza) per <xref:System.Windows.Controls.Primitives.Popup> . Il punto che mostra la parte più grande di <xref:System.Windows.Controls.Primitives.Popup> viene selezionato automaticamente. Per un esempio, vedere [Procedura: Specificare una posizione personalizzata per un controllo Popup](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Controllo Popup e struttura ad albero visuale  
 Un <xref:System.Windows.Controls.Primitives.Popup> controllo non dispone di una propria struttura ad albero visuale. restituisce invece una dimensione pari a 0 (zero) quando <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> viene chiamato il metodo per <xref:System.Windows.Controls.Primitives.Popup> . Tuttavia, quando si imposta la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> proprietà di <xref:System.Windows.Controls.Primitives.Popup> su `true` , viene creata una nuova finestra con la relativa struttura ad albero visuale. La nuova finestra contiene il <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto di <xref:System.Windows.Controls.Primitives.Popup> . La larghezza e l'altezza della nuova finestra non possono superare il 75 per cento della larghezza o dell'altezza dello schermo.  
  
 Il <xref:System.Windows.Controls.Primitives.Popup> controllo mantiene un riferimento al <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto come figlio logico. Quando viene creata la nuova finestra, il contenuto di <xref:System.Windows.Controls.Primitives.Popup> diventa un elemento figlio visivo della finestra e rimane l'elemento figlio logico di <xref:System.Windows.Controls.Primitives.Popup> . Viceversa, <xref:System.Windows.Controls.Primitives.Popup> rimane l'elemento padre logico del relativo <xref:System.Windows.Controls.Primitives.Popup.Child%2A> contenuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Procedure relative](popup-how-to-topics.md)
- [Procedure relative](tooltip-how-to-topics.md)
