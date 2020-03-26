---
title: Cenni preliminari sulle trasformazioni
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111959"
---
# <a name="transforms-overview"></a>Cenni preliminari sulle trasformazioni
In questo argomento viene descritto <xref:System.Windows.Media.Transform> come utilizzare le classi 2D per <xref:System.Windows.FrameworkElement> ruotare, ridimensionare, spostare (tradurre) e inclinare gli oggetti.  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>Che cos'è un oggetto Transform?  
 A <xref:System.Windows.Media.Transform> definisce come mappare o trasformare i punti da uno spazio di coordinate a un altro. Questo mapping è descritto <xref:System.Windows.Media.Matrix>da una trasformazione , ovvero <xref:System.Double> un insieme di tre righe con tre colonne di valori.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF I vettori sono espressi come vettori di riga anziché come vettori di colonna.  
  
 La tabella seguente illustra la struttura di una matrice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2d-transformation-matrix"></a>Matrice di trasformazione 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valore predefinito: 1,0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valore predefinito: 0,0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valore predefinito: 1,0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valore predefinito: 0,0|1.0|  
  
 Modificando i valori della matrice, è possibile ruotare, ridimensionare, inclinare e spostare (traslare) un oggetto. Ad esempio, se si modifica il valore nella prima <xref:System.Windows.Media.Matrix.OffsetX%2A> colonna della terza riga (il valore) in 100, è possibile utilizzarlo per spostare un oggetto di 100 unità lungo l'asse x. Se si imposta il valore nella seconda colonna della seconda riga su 3, è possibile usarlo per allungare un oggetto fino a un'altezza tre volte superiore a quella corrente. Se si modificano entrambi i valori, si sposta l'oggetto di 100 unità lungo l'asse x e se ne aumenta l'altezza di un fattore di 3. Poiché Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) supporta solo le trasformazioni affini, i valori nella colonna di destra sono sempre 0, 0, 1.Because Windows Presentation Foundation (WPF) only supports affine transforms, the values in the right column are always 0, 0, 1.  
  
 Anche se Windows Presentation Foundation (WPF)Windows Presentation Foundation <xref:System.Windows.Media.Transform> (WPF) consente di modificare direttamente i valori della matrice, fornisce anche diverse classi che consentono di trasformare un oggetto senza sapere come è configurata la struttura della matrice sottostante. Ad esempio, <xref:System.Windows.Media.ScaleTransform> la classe consente di ridimensionare <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> un oggetto impostandone le proprietà e, anziché modificare una matrice di trasformazione. Analogamente, <xref:System.Windows.Media.RotateTransform> la classe consente di ruotare <xref:System.Windows.Media.RotateTransform.Angle%2A> un oggetto impostandone semplicemente la proprietà.  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>Classi Transform  
 Windows Presentation Foundation (WPF)Windows <xref:System.Windows.Media.Transform> Presentation Foundation (WPF)Windows Presentation Foundation (WPF) fornisce le classi 2D seguenti per le operazioni di trasformazione comuni:Windows Presentation Foundation (WPF) provides the following 2D classes for common transformation operations:  
  
|Classe|Descrizione|Esempio|Illustrazione|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Ruota un elemento in <xref:System.Windows.Media.RotateTransform.Angle%2A>base all'oggetto specificato.|[Ruotare un oggetto](how-to-rotate-an-object.md)|![Illustrazione di Rotate](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Ridimensiona un elemento in <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> base ai valori e specificati.|[Ridimensionare un elemento](how-to-scale-an-element.md)|![Illustrazione di Scale](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Inclina un elemento in <xref:System.Windows.Media.SkewTransform.AngleX%2A> <xref:System.Windows.Media.SkewTransform.AngleY%2A> base agli importi e specificati.|[Inclinare un elemento](how-to-skew-an-element.md)|![Illustrazione di Skew](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Sposta (traduce) un elemento <xref:System.Windows.Media.TranslateTransform.X%2A> in <xref:System.Windows.Media.TranslateTransform.Y%2A> base agli importi e specificati.|[Convertire un elemento](how-to-translate-an-element.md)|![Illustrazione di Translate](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Per la creazione di trasformazioni più complesse, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) fornisce le due classi seguenti:For creating more complex transformations, Windows Presentation Foundation (WPF) provides the following two classes:  
  
|Classe|Descrizione|Esempio|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Raggruppa <xref:System.Windows.Media.TransformGroup> più oggetti <xref:System.Windows.Media.Transform> in un unico che è quindi possibile applicare alle proprietà di trasformazione.|[Applicare più trasformazioni a un oggetto](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea trasformazioni personalizzate non fornite <xref:System.Windows.Media.Transform> dalle altre classi. Quando si <xref:System.Windows.Media.MatrixTransform>utilizza un oggetto , si modifica direttamente una matrice.|[Utilizzare un MatrixTransform per creare trasformazioni personalizzate](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) fornisce anche trasformazioni 3D. Per altre informazioni, vedere la classe <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>Proprietà di trasformazione comuni  
 Un modo per trasformare un oggetto <xref:System.Windows.Media.Transform> consiste nel dichiarare il tipo appropriato e applicarlo alla proprietà transformation dell'oggetto. Tipi diversi di oggetti hanno tipi diversi di proprietà di trasformazione. Nella tabella seguente sono elencati diversi tipi Windows Presentation Foundation (WPF) di uso comune e le relative proprietà di trasformazione.  
  
|Type|Proprietà di trasformazione|  
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
 Quando si trasforma un oggetto, non si trasforma solo l'oggetto, ma anche lo spazio di coordinate in cui esiste. Per impostazione predefinita, una trasformazione è allineata al centro in corrispondenza dell'origine del sistema di coordinate dell'oggetto di destinazione: (0,0). L'unica <xref:System.Windows.Media.TranslateTransform>eccezione è ; a <xref:System.Windows.Media.TranslateTransform> non ha proprietà del centro da impostare perché l'effetto di traslazione è lo stesso indipendentemente da dove è centrato.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.RotateTransform> oggetto per ruotare un <xref:System.Windows.Shapes.Rectangle> elemento, un tipo di <xref:System.Windows.FrameworkElement>, di 45 gradi sul centro predefinito (0, 0). L'immagine seguente illustra l'effetto della rotazione.  
  
 ![A FrameworkElement rotated 45 degrees about &#40;0,0&#41;](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 Per impostazione predefinita, l'elemento ruota intorno al relativo angolo superiore sinistro, (0, 0). Le <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ScaleTransform>classi <xref:System.Windows.Media.SkewTransform> , e forniscono proprietà CenterX e CenterY che consentono di specificare il punto in cui viene applicata la trasformazione.  
  
 L'esempio successivo <xref:System.Windows.Media.RotateTransform> usa anche <xref:System.Windows.Shapes.Rectangle> un per ruotare un elemento di 45 gradi; tuttavia, questa <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> volta le proprietà <xref:System.Windows.Media.RotateTransform> e sono impostate in modo che il ha un centro di (25, 25). L'immagine seguente illustra l'effetto della rotazione.  
  
 ![Oggetto Geometry ruotato di 45 gradi rispetto a &#40;25, 25&#41;](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>Trasformazione di FrameworkElement  
 Per applicare trasformazioni <xref:System.Windows.FrameworkElement>a <xref:System.Windows.Media.Transform> un oggetto , creare e applicarlo a una delle due proprietà fornite dalla <xref:System.Windows.FrameworkElement> classe:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– Una trasformazione che viene applicata prima del passaggio di layout. Dopo l'applicazione della trasformazione, il sistema di layout elabora le dimensioni e la posizione trasformate dell'elemento.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>– Una trasformazione che modifica l'aspetto dell'elemento ma viene applicata al termine del passaggio di layout. Utilizzando la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà anziché la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà, è possibile ottenere vantaggi in termini di prestazioni.  
  
 Quale proprietà usare? A causa dei vantaggi in termini <xref:System.Windows.UIElement.RenderTransform%2A> di prestazioni che fornisce, <xref:System.Windows.Media.Transform> utilizzare la proprietà quando possibile, soprattutto quando si utilizzano oggetti animati. Utilizzare <xref:System.Windows.FrameworkElement.LayoutTransform%2A> la proprietà durante il ridimensionamento, la rotazione o l'inclinazione ed è necessario che l'elemento padre dell'elemento si adatti alle dimensioni trasformate dell'elemento. Si noti che, quando <xref:System.Windows.FrameworkElement.LayoutTransform%2A> vengono <xref:System.Windows.Media.TranslateTransform> utilizzati con la proprietà , gli oggetti sembrano non avere alcun effetto sugli elementi. Ciò è dovuto al fatto che il sistema di layout riporta l'elemento traslato nella posizione originale come parte dell'elaborazione.  
  
 Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere la panoramica sul [Layout](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Esempio: rotazione di un oggetto FrameworkElement di 45 gradi  
 Nell'esempio seguente <xref:System.Windows.Media.RotateTransform> viene utilizzato un per ruotare un pulsante in senso orario di 45 gradi. Il pulsante è <xref:System.Windows.Controls.StackPanel> contenuto in un che dispone di altri due pulsanti.  
  
 Per impostazione <xref:System.Windows.Media.RotateTransform> predefinita, un ruota intorno al punto (0, 0). Poiché l'esempio non specifica un valore relativo al centro, il pulsante ruota intorno al punto (0, 0), che corrisponde all'angolo superiore sinistro. L'oggetto <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.UIElement.RenderTransform%2A> applicato alla proprietà . L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione di 45 gradi in senso orario rispetto all'angolo superiore sinistro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 L'esempio successivo <xref:System.Windows.Media.RotateTransform> usa anche un per ruotare un pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> di 45 gradi in senso orario, ma imposta anche il pulsante del pulsante su (0,5, 0,5). Il valore <xref:System.Windows.UIElement.RenderTransformOrigin%2A> della proprietà è relativo alle dimensioni del pulsante. La rotazione viene quindi applicata al centro del pulsante anziché nell'angolo superiore sinistro. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato rispetto al proprio centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi in senso orario intorno al centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Nell'esempio seguente <xref:System.Windows.FrameworkElement.LayoutTransform%2A> viene utilizzata <xref:System.Windows.UIElement.RenderTransform%2A> la proprietà anziché la proprietà per ruotare il pulsante.  In questo caso la trasformazione influisce sul layout del pulsante e provoca l'attivazione di un passaggio completo da parte del sistema di layout. Il pulsante viene quindi ruotato e riposizionato perché le relative dimensioni sono state modificate. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Uso di LayoutTransform per ruotare il pulsante  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>Animazione delle trasformazioni  
 Poiché ereditano <xref:System.Windows.Media.Animation.Animatable> dalla <xref:System.Windows.Media.Transform> classe, le classi possono essere animate. Per animare un <xref:System.Windows.Media.Transform>oggetto , applicare un'animazione di un tipo compatibile alla proprietà che si desidera animare.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> vengono <xref:System.Windows.Media.Animation.DoubleAnimation> utilizzati a e a con a <xref:System.Windows.Media.RotateTransform> per creare un <xref:System.Windows.Controls.Button> giro sul posto quando si fa clic su di esso.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Per l'esempio completo, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms). Per altre informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla <xref:System.Windows.Freezable> classe <xref:System.Windows.Media.Transform> , la classe <xref:System.Windows.Media.Transform> fornisce diverse funzionalità speciali: gli oggetti possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità <xref:System.Windows.Freezable> fornite dagli oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Procedure relative](transformations-how-to-topics.md)
- [Esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
