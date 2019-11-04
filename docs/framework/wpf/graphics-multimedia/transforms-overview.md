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
ms.openlocfilehash: ead1d114f773cba88e8b3e20f395019fbde3ee15
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458588"
---
# <a name="transforms-overview"></a>Cenni preliminari sulle trasformazioni
Questo argomento descrive come usare le classi di <xref:System.Windows.Media.Transform> 2D per ruotare, ridimensionare, spostare (tradurre) e inclinare <xref:System.Windows.FrameworkElement> oggetti.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Che cos'è un oggetto Transform?  
 Una <xref:System.Windows.Media.Transform> definisce la modalità di mapping, o trasformazione, di punti da uno spazio delle coordinate a un altro spazio delle coordinate. Questo mapping è descritto da una trasformazione <xref:System.Windows.Media.Matrix>, ovvero una raccolta di tre righe con tre colonne di valori <xref:System.Double>.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF) USA matrici row-major. I vettori sono espressi come vettori di riga anziché come vettori di colonna.  
  
 La tabella seguente illustra la struttura di una matrice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Matrice di trasformazione 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valore predefinito: 1,0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valore predefinito: 0,0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valore predefinito: 1,0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valore predefinito: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valore predefinito: 0,0|1.0|  
  
 Modificando i valori della matrice, è possibile ruotare, ridimensionare, inclinare e spostare (traslare) un oggetto. Se ad esempio si modifica il valore nella prima colonna della terza riga (il valore <xref:System.Windows.Media.Matrix.OffsetX%2A>) su 100, è possibile usarlo per spostare un oggetto 100 unità lungo l'asse x. Se si imposta il valore nella seconda colonna della seconda riga su 3, è possibile usarlo per allungare un oggetto fino a un'altezza tre volte superiore a quella corrente. Se si modificano entrambi i valori, si sposta l'oggetto di 100 unità lungo l'asse x e se ne aumenta l'altezza di un fattore di 3. Poiché Windows Presentation Foundation (WPF) supporta solo le trasformazioni affini, i valori nella colonna a destra sono sempre 0, 0, 1.  
  
 Sebbene Windows Presentation Foundation (WPF) consenta di modificare direttamente i valori della matrice, fornisce inoltre diverse classi <xref:System.Windows.Media.Transform> che consentono di trasformare un oggetto senza conoscere il modo in cui viene configurata la struttura della matrice sottostante. La classe <xref:System.Windows.Media.ScaleTransform>, ad esempio, consente di ridimensionare un oggetto impostando le relative proprietà <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>, anziché modificare una matrice di trasformazione. Analogamente, la classe <xref:System.Windows.Media.RotateTransform> consente di ruotare un oggetto impostando semplicemente la relativa proprietà <xref:System.Windows.Media.RotateTransform.Angle%2A>.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Classi Transform  
 Windows Presentation Foundation (WPF) fornisce le seguenti classi di <xref:System.Windows.Media.Transform> 2D per le operazioni di trasformazione comuni:  
  
|Class|Descrizione|Esempio|Illustrazione|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Ruota un elemento in base al <xref:System.Windows.Media.RotateTransform.Angle%2A>specificato.|[Ruotare un oggetto](how-to-rotate-an-object.md)|![Ruota illustrazione](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Ridimensiona un elemento in base al <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e agli importi di <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> specificati.|[Ridimensionare un elemento](how-to-scale-an-element.md)|![Illustrazione della scala](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Inclina un elemento in base al <xref:System.Windows.Media.SkewTransform.AngleX%2A> e agli importi di <xref:System.Windows.Media.SkewTransform.AngleY%2A> specificati.|[Inclinare un elemento](how-to-skew-an-element.md)|![Illustrazione di inclinazione](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Sposta (converte) un elemento in base al <xref:System.Windows.Media.TranslateTransform.X%2A> specificato e <xref:System.Windows.Media.TranslateTransform.Y%2A> Imports.|[Convertire un elemento](how-to-translate-an-element.md)|![Illustrazione della traduzione](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Per la creazione di trasformazioni più complesse, Windows Presentation Foundation (WPF) fornisce le due classi seguenti:  
  
|Class|Descrizione|Esempio|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Raggruppa più oggetti <xref:System.Windows.Media.TransformGroup> in un singolo <xref:System.Windows.Media.Transform> che è quindi possibile applicare alle proprietà di trasformazione.|[Applicare più trasformazioni a un oggetto](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea trasformazioni personalizzate che non sono fornite dalle altre classi <xref:System.Windows.Media.Transform>. Quando si utilizza una <xref:System.Windows.Media.MatrixTransform>, è possibile modificare direttamente una matrice.|[Utilizzare un MatrixTransform per creare trasformazioni personalizzate](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) fornisce anche le trasformazioni 3D. Per altre informazioni, vedere la classe <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Proprietà di trasformazione comuni  
 Un modo per trasformare un oggetto consiste nel dichiarare il tipo di <xref:System.Windows.Media.Transform> appropriato e applicarlo alla proprietà Transformation dell'oggetto. Tipi diversi di oggetti hanno tipi diversi di proprietà di trasformazione. Nella tabella seguente sono elencati diversi tipi di Windows Presentation Foundation (WPF) comunemente utilizzati e le relative proprietà di trasformazione.  
  
|Digitare|Proprietà di trasformazione|  
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
 Quando si trasforma un oggetto, non si trasforma solo l'oggetto, ma anche lo spazio di coordinate in cui esiste. Per impostazione predefinita, una trasformazione è allineata al centro in corrispondenza dell'origine del sistema di coordinate dell'oggetto di destinazione: (0,0). L'unica eccezione è <xref:System.Windows.Media.TranslateTransform>; un <xref:System.Windows.Media.TranslateTransform> non dispone di proprietà del centro da impostare perché l'effetto di traduzione è lo stesso indipendentemente dal punto in cui è centrato.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.RotateTransform> per ruotare un elemento <xref:System.Windows.Shapes.Rectangle>, un tipo di <xref:System.Windows.FrameworkElement>, di 45 gradi rispetto al centro predefinito, ovvero 0, 0. L'immagine seguente illustra l'effetto della rotazione.  
  
 ![A FrameworkElement rotated 45 degrees about &#40;0,0&#41;](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 Per impostazione predefinita, l'elemento ruota intorno al relativo angolo superiore sinistro, (0, 0). Le classi <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>e <xref:System.Windows.Media.SkewTransform> forniscono le proprietà CenterX e CenterY che consentono di specificare il punto in cui viene applicata la trasformazione.  
  
 Nell'esempio seguente viene anche usato un <xref:System.Windows.Media.RotateTransform> per ruotare un elemento <xref:System.Windows.Shapes.Rectangle> di 45 gradi; Questa volta, tuttavia, le proprietà <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> sono impostate in modo che il <xref:System.Windows.Media.RotateTransform> disponga di un centro (25, 25). L'immagine seguente illustra l'effetto della rotazione.  
  
 ![Oggetto Geometry ruotato di 45 gradi rispetto a &#40;25, 25&#41;](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle ruotato di 45 gradi intorno al punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Trasformazione di FrameworkElement  
 Per applicare le trasformazioni a una <xref:System.Windows.FrameworkElement>, creare una <xref:System.Windows.Media.Transform> e applicarla a una delle due proprietà fornite dalla classe <xref:System.Windows.FrameworkElement>:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>: una trasformazione applicata prima del passaggio del layout. Dopo l'applicazione della trasformazione, il sistema di layout elabora le dimensioni e la posizione trasformate dell'elemento.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>: una trasformazione che modifica l'aspetto dell'elemento, ma viene applicata dopo il completamento del passaggio di layout. Utilizzando la proprietà <xref:System.Windows.UIElement.RenderTransform%2A> invece della proprietà <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, è possibile ottenere vantaggi in merito alle prestazioni.  
  
 Quale proprietà usare? A causa dei vantaggi offerti dalle prestazioni, utilizzare la proprietà <xref:System.Windows.UIElement.RenderTransform%2A> laddove possibile, soprattutto quando si utilizzano oggetti <xref:System.Windows.Media.Transform> animati. Utilizzare la proprietà <xref:System.Windows.FrameworkElement.LayoutTransform%2A> durante la scala, la rotazione o la distorsione ed è necessario che l'elemento padre dell'elemento venga modificato in modo da adattarsi alle dimensioni trasformate dell'elemento. Si noti che, quando vengono usati con la proprietà <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, <xref:System.Windows.Media.TranslateTransform> oggetti sembrano non avere alcun effetto sugli elementi. Ciò è dovuto al fatto che il sistema di layout riporta l'elemento traslato nella posizione originale come parte dell'elaborazione.  
  
 Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vedere la panoramica sul [Layout](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Esempio: rotazione di un oggetto FrameworkElement di 45 gradi  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.RotateTransform> per ruotare un pulsante in senso orario di 45 gradi. Il pulsante è contenuto in un <xref:System.Windows.Controls.StackPanel> che dispone di altri due pulsanti.  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.RotateTransform> ruota intorno al punto (0, 0). Poiché l'esempio non specifica un valore relativo al centro, il pulsante ruota intorno al punto (0, 0), che corrisponde all'angolo superiore sinistro. Il <xref:System.Windows.Media.RotateTransform> viene applicato alla proprietà <xref:System.Windows.UIElement.RenderTransform%2A>. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione di 45 gradi in senso orario rispetto all'angolo superiore sinistro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 L'esempio seguente usa anche un <xref:System.Windows.Media.RotateTransform> per ruotare un pulsante di 45 gradi in senso orario, ma imposta anche la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante su (0,5, 0,5). Il valore della proprietà <xref:System.Windows.UIElement.RenderTransformOrigin%2A> è relativo alle dimensioni del pulsante. La rotazione viene quindi applicata al centro del pulsante anziché nell'angolo superiore sinistro. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato rispetto al proprio centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi in senso orario intorno al centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Nell'esempio seguente viene usata la proprietà <xref:System.Windows.FrameworkElement.LayoutTransform%2A> invece della proprietà <xref:System.Windows.UIElement.RenderTransform%2A> per ruotare il pulsante.  In questo caso la trasformazione influisce sul layout del pulsante e provoca l'attivazione di un passaggio completo da parte del sistema di layout. Il pulsante viene quindi ruotato e riposizionato perché le relative dimensioni sono state modificate. L'immagine seguente illustra il risultato della trasformazione.  
  
 ![Pulsante trasformato usando LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Uso di LayoutTransform per ruotare il pulsante  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animazione delle trasformazioni  
 Poiché ereditano dalla classe <xref:System.Windows.Media.Animation.Animatable>, le classi <xref:System.Windows.Media.Transform> possono essere animate. Per animare una <xref:System.Windows.Media.Transform>, applicare un'animazione di un tipo compatibile alla proprietà a cui si desidera aggiungere un'animazione.  
  
 Nell'esempio seguente vengono utilizzati un <xref:System.Windows.Media.Animation.Storyboard> e una <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.RotateTransform> per fare in modo che un <xref:System.Windows.Controls.Button> Spin sul posto quando viene selezionato.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252). Per altre informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla classe <xref:System.Windows.Freezable>, la classe <xref:System.Windows.Media.Transform> fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Transform> oggetti possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Procedure relative alle proprietà](transformations-how-to-topics.md)
- [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252)
