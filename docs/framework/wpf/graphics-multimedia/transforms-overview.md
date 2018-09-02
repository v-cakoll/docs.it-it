---
title: Cenni preliminari sulle trasformazioni
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: 4fd846502fd348222bc1da1c8746f037e9f237fe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425843"
---
# <a name="transforms-overview"></a>Cenni preliminari sulle trasformazioni
In questo argomento viene descritto come utilizzare il [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> alle classi di ruotare, ridimensionare, spostare (traslare) e inclinare <xref:System.Windows.FrameworkElement> oggetti.  
  
  
<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Che cos'è un oggetto Transform?  
 Oggetto <xref:System.Windows.Media.Transform> definisce come eseguire il mapping o trasformare i punti da uno spazio di coordinate a un altro spazio delle coordinate. Questo mapping è descritto da una trasformazione <xref:System.Windows.Media.Matrix>, che è una raccolta di tre righe con tre colonne di <xref:System.Double> valori.  
  
> [!NOTE]
>  Windows Presentation Foundation (WPF) Usa matrici row-major. I vettori sono espressi come vettori di riga anziché come vettori di colonna.  
  
 La tabella seguente illustra la struttura di una matrice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Matrice di trasformazione 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valore predefinito: 1,0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valore predefinito: 0,0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valore predefinito: 1,0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valore predefinito: 0,0|1.0|  
  
 Modificando i valori della matrice, è possibile ruotare, ridimensionare, inclinare e spostare (traslare) un oggetto. Ad esempio, se si modifica il valore nella prima colonna della terza riga (il <xref:System.Windows.Media.Matrix.OffsetX%2A> valore) a 100, è possibile usarlo per spostare un oggetto di 100 unità lungo l'asse x. Se si imposta il valore nella seconda colonna della seconda riga su 3, è possibile usarlo per allungare un oggetto fino a un'altezza tre volte superiore a quella corrente. Se si modificano entrambi i valori, si sposta l'oggetto di 100 unità lungo l'asse x e se ne aumenta l'altezza di un fattore di 3. Poiché Windows Presentation Foundation (WPF) supporta solo le trasformazioni affini, i valori nella colonna destra sono sempre 0, 0, 1.  
  
 Anche se Windows Presentation Foundation (WPF) consente di modificare direttamente i valori della matrice, vengono comunque fornite diverse <xref:System.Windows.Media.Transform> le classi che consentono di trasformare un oggetto senza conoscere la configurazione della struttura della matrice sottostante. Ad esempio, il <xref:System.Windows.Media.ScaleTransform> classe consente di ridimensionare un oggetto tramite l'impostazione relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà, anziché la modifica di una matrice di trasformazione. Analogamente, il <xref:System.Windows.Media.RotateTransform> classe consente di ruotare un oggetto impostando semplicemente il <xref:System.Windows.Media.RotateTransform.Angle%2A> proprietà.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Classi Transform  
 Windows Presentation Foundation (WPF) offre quanto segue [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> classi per le operazioni di trasformazione comuni:  
  
|Classe|Descrizione|Esempio|Illustrazione|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Ruota un elemento in base ai valori <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Ruotare un oggetto](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)|![Rotate illustration](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Ridimensiona un elemento dall'oggetto specificato <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> quantità.|[Ridimensionare un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)|![Scale illustration](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Inclina un elemento dall'oggetto specificato <xref:System.Windows.Media.SkewTransform.AngleX%2A> e <xref:System.Windows.Media.SkewTransform.AngleY%2A> quantità.|[Inclinare un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)|![Skew illustration](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Sposta (Trasla) un elemento dall'oggetto specificato <xref:System.Windows.Media.TranslateTransform.X%2A> e <xref:System.Windows.Media.TranslateTransform.Y%2A> quantità.|[Convertire un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)|![Translate illustration](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Per la creazione di trasformazioni più complesse, Windows Presentation Foundation (WPF) offre le due classi seguenti:  
  
|Classe|Descrizione|Esempio|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Raggruppa più <xref:System.Windows.Media.TransformGroup> oggetti in un'unica <xref:System.Windows.Media.Transform> che è quindi possibile applicare alle proprietà di trasformazione.|[Applicare più trasformazioni a un oggetto](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea trasformazioni personalizzate non fornite da altro <xref:System.Windows.Media.Transform> classi. Quando si usa un <xref:System.Windows.Media.MatrixTransform>, si modifica direttamente una matrice.|[Utilizzare un MatrixTransform per creare trasformazioni personalizzate](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) fornisce anche [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] trasformazioni. Per altre informazioni, vedere la classe <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Proprietà di trasformazione comuni  
 Un modo per trasformare un oggetto consiste nel dichiarare appropriato <xref:System.Windows.Media.Transform> digitare e applicarlo alla proprietà di trasformazione dell'oggetto. Tipi diversi di oggetti hanno tipi diversi di proprietà di trasformazione. La tabella seguente elenca i diversi tipi di Windows Presentation Foundation (WPF) comunemente usati e le relative proprietà di trasformazione.  
  
|Tipo|Proprietà di trasformazione|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## <a name="transformations-and-coordinate-systems"></a>Trasformazioni e sistemi di coordinate  
 Quando si trasforma un oggetto, non si trasforma solo l'oggetto, ma anche lo spazio di coordinate in cui esiste. Per impostazione predefinita, una trasformazione è allineata al centro in corrispondenza dell'origine del sistema di coordinate dell'oggetto di destinazione: (0,0). L'unica eccezione riguarda <xref:System.Windows.Media.TranslateTransform>; un <xref:System.Windows.Media.TranslateTransform> non sono disponibili proprietà per impostare l'effetto di traslazione è identico indipendentemente in cui viene centrato.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.RotateTransform> ruotare una <xref:System.Windows.Shapes.Rectangle> elemento, un tipo di <xref:System.Windows.FrameworkElement>, di 45 gradi intorno al centro predefinito (0, 0). L'immagine seguente illustra l'effetto della rotazione.  
  
 ![Un oggetto FrameworkElement ruotato di 45 gradi su &#40;0,0&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 Per impostazione predefinita, l'elemento ruota intorno al relativo angolo superiore sinistro, (0, 0). Il <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>, e <xref:System.Windows.Media.SkewTransform> classi forniscono proprietà CenterX e CenterY che consentono di specificare il punto in corrispondenza del quale viene applicata la trasformazione.  
  
 Anche l'esempio seguente usa un <xref:System.Windows.Media.RotateTransform> per ruotare un <xref:System.Windows.Shapes.Rectangle> elemento di 45 gradi; tuttavia, questa volta il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> le proprietà vengono impostate in modo che il <xref:System.Windows.Media.RotateTransform> centro di (25, 25). L'immagine seguente illustra l'effetto della rotazione.  
  
 ![Oggetto Geometry ruotato di 45 gradi su &#40;25, 25&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Trasformazione di FrameworkElement  
 Applicare trasformazioni a un <xref:System.Windows.FrameworkElement>, creare un <xref:System.Windows.Media.Transform> e applicarlo a una delle due proprietà che il <xref:System.Windows.FrameworkElement> classe fornisce:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> : Una trasformazione applicata prima del passaggio di layout. Dopo l'applicazione della trasformazione, il sistema di layout elabora le dimensioni e la posizione trasformate dell'elemento.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> : Una trasformazione che modifica l'aspetto dell'elemento ma viene applicata dopo il passaggio di layout è stata completata. Tramite il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà anziché il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà, è possibile ottenere vantaggi nelle prestazioni.  
  
 Quale proprietà usare? A causa di offre vantaggi nelle prestazioni, usare il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, se possibile, soprattutto quando si usa animato <xref:System.Windows.Media.Transform> oggetti. Usare il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà in caso di ridimensionamento, Ruota o inclina ed è necessario l'elemento padre dell'elemento per adattarti alle dimensioni trasformate dell'elemento. Si noti che, quando vengono usati con il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà <xref:System.Windows.Media.TranslateTransform> gli oggetti sembrano non avere alcun effetto sugli elementi. Ciò è dovuto al fatto che il sistema di layout riporta l'elemento traslato nella posizione originale come parte dell'elaborazione.  
  
 Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere la panoramica sul [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Esempio: rotazione di un oggetto FrameworkElement di 45 gradi  
 L'esempio seguente usa un <xref:System.Windows.Media.RotateTransform> per ruotare un pulsante in senso orario di 45 gradi. Il pulsante è contenuto un <xref:System.Windows.Controls.StackPanel> che include altri due pulsanti.  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.RotateTransform> ruota intorno al punto (0, 0). Poiché l'esempio non specifica un valore relativo al centro, il pulsante ruota intorno al punto (0, 0), che corrisponde all'angolo superiore sinistro. Il <xref:System.Windows.Media.RotateTransform> viene applicato a di <xref:System.Windows.UIElement.RenderTransform%2A> proprietà. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione di 45 gradi in senso orario rispetto all'angolo superiore sinistro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 L'esempio seguente usa anche un <xref:System.Windows.Media.RotateTransform> per ruotare un pulsante di 45 gradi in senso orario, ma viene anche impostata la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante su (0,5, 0,5). Il valore della <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà è relativo alle dimensioni del pulsante. La rotazione viene quindi applicata al centro del pulsante anziché nell'angolo superiore sinistro. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato rispetto al proprio centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi in senso orario intorno al centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 L'esempio seguente usa il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> anziché il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà per ruotare il pulsante.  In questo caso la trasformazione influisce sul layout del pulsante e provoca l'attivazione di un passaggio completo da parte del sistema di layout. Il pulsante viene quindi ruotato e riposizionato perché le relative dimensioni sono state modificate. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando LayoutTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Uso di LayoutTransform per ruotare il pulsante  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animazione delle trasformazioni  
 Poiché ereditano dal <xref:System.Windows.Media.Animation.Animatable> (classe), il <xref:System.Windows.Media.Transform> classi possono essere animate. Animare un <xref:System.Windows.Media.Transform>, applicare un'animazione di un tipo compatibile alla proprietà da animare.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.Animation.Storyboard> e una <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.RotateTransform> per rendere un <xref:System.Windows.Controls.Button> selezione disponibile quando si fa clic.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252). Per altre informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dal <xref:System.Windows.Freezable> (classe), il <xref:System.Windows.Media.Transform> classe fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Transform> gli oggetti possono essere dichiarati come [risorse](../../../../docs/framework/wpf/advanced/xaml-resources.md)condiviso tra più oggetti, sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per altre informazioni sulle diverse funzionalità fornite da <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Matrix>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252)
