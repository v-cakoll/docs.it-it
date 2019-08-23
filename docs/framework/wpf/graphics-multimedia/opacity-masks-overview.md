---
title: Cenni preliminari sulle maschere di opacità
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: d0fea1aac4efb17811404ce45769615bb2e7234f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929667"
---
# <a name="opacity-masks-overview"></a>Cenni preliminari sulle maschere di opacità
Le maschere di opacità consentono di rendere trasparenti o parzialmente trasparenti parti di un elemento o di un oggetto visivo. Per creare una maschera di opacità, applicare <xref:System.Windows.Media.Brush> un oggetto <xref:System.Windows.UIElement.OpacityMask%2A> alla proprietà di un elemento <xref:System.Windows.Media.Visual>o.  Viene eseguito il mapping del pennello all'elemento o oggetto visivo e il valore di opacità di ogni pixel del pennello viene usato per determinare l'opacità risultante di ogni pixel corrispondente dell'elemento o dell'oggetto visivo.  
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questa panoramica si presuppone che l'utente <xref:System.Windows.Media.Brush> abbia familiarità con gli oggetti. Per un'introduzione all'uso dei pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md). Per informazioni su <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.DrawingBrush>, vedere [disegnare con immagini, disegni e](painting-with-images-drawings-and-visuals.md)oggetti visivi.  
  
<a name="opacitymasks"></a>   
## <a name="creating-visual-effects-with-opacity-masks"></a>Creazione di effetti visivi con maschere di opacità  
 Il funzionamento delle maschere di opacità è basato sul mapping del suo contenuto all'elemento o oggetto visivo. Il canale alfa di ogni pixel del pennello viene usato per determinare l'opacità risultante dei pixel corrispondenti dell'elemento o oggetto visivo. Il colore effettivo del pennello viene ignorato. Se una parte del pennello è trasparente, la parte corrispondente dell'elemento o oggetto visivo diventa trasparente. Se una parte del pennello è opaca, l'opacità della parte corrispondente dell'elemento o oggetto visivo rimane inalterata. L'opacità specificata dalla maschera di opacità viene combinata a qualsiasi impostazione di opacità dell'elemento o oggetto visivo. Se ad esempio un elemento è opaco al 25 percento e viene applicata una maschera di opacità che crea una transizione da opacità totale a trasparenza totale, il risultato è un elemento che passa dal 25 percento di opacità a una trasparenza totale.  
  
> [!NOTE]
> Sebbene gli esempi in questa panoramica dimostrino l'uso di maschere di opacità sugli elementi immagine, una maschera di opacità può <xref:System.Windows.Media.Visual>essere applicata a qualsiasi elemento o, inclusi i pannelli e i controlli.  
  
 Le maschere di opacità vengono usate per creare effetti visivi interessanti, ad esempio dissolvenze per immagini o pulsanti, aggiunta di trame agli elementi o combinazione di sfumature per ottenere il cosiddetto effetto cristallo. La figura seguente illustra l'uso di una maschera di opacità. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità LinearGradientBrush](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
Esempio di maschera di opacità  
  
<a name="creatingopacitymasks"></a>   
## <a name="creating-an-opacity-mask"></a>Creazione di una maschera di opacità  
 Per creare una maschera di opacità, creare <xref:System.Windows.Media.Brush> un oggetto e applicarlo <xref:System.Windows.UIElement.OpacityMask%2A> alla proprietà di un elemento o di un oggetto visivo. È possibile utilizzare qualsiasi tipo di <xref:System.Windows.Media.Brush> come maschera di opacità.  
  
- <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Utilizzato per rendere un elemento o una dissolvenza visiva dalla visualizzazione.  
  
     Nell'immagine seguente viene illustrato <xref:System.Windows.Media.LinearGradientBrush> un oggetto utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità LinearGradientBrush](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
Esempio di maschera di opacità LinearGradientBrush  
  
- <xref:System.Windows.Media.ImageBrush>: Utilizzato per creare la trama e gli effetti di bordi morbidi o danneggiati.  
  
     Nell'immagine seguente viene illustrato <xref:System.Windows.Media.ImageBrush> un oggetto utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità ImageBrush](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
Esempio di maschera di opacità LinearGradientBrush  
  
- <xref:System.Windows.Media.DrawingBrush>: Utilizzato per creare maschere di opacità complesse da modelli di forme, immagini e sfumature.  
  
     Nell'immagine seguente viene illustrato <xref:System.Windows.Media.DrawingBrush> un oggetto utilizzato come maschera di opacità.  
  
     ![Oggetto con maschera di opacità DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
Esempio di maschera di opacità DrawingBrush  
  
 I pennelli sfumatura <xref:System.Windows.Media.RadialGradientBrush>(<xref:System.Windows.Media.LinearGradientBrush> e) sono particolarmente adatti per essere utilizzati come maschera di opacità. Poiché un <xref:System.Windows.Media.SolidColorBrush> oggetto riempie un'area con un colore uniforme, rendono le maschere di opacità insufficienti. l'utilizzo di un oggetto <xref:System.Windows.Media.SolidColorBrush> equivale a impostare <xref:System.Windows.UIElement.OpacityMask%2A> la proprietà dell'elemento o dell'oggetto visivo.  
  
<a name="creatingopacitymaskswithgradients"></a>   
## <a name="using-a-gradient-as-an-opacity-mask"></a>Uso di una sfumatura come maschera di opacità  
 Per creare un riempimento sfumato, specificare due o più cursori sfumatura. Ogni cursore sfumatura descrive un colore e una posizione. Per altre informazioni sulla creazione e l'uso di sfumature, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md). Il processo equivale a quello relativo all'uso di una sfumatura come maschera di opacità, ma, anziché miscelare i colori, la maschera di opacità miscela i valori del canale alfa. Pertanto, ciò che è importante non è il colore effettivo del contenuto della sfumatura, bensì il canale alfa, o opacità, di ogni colore. Di seguito è riportato un esempio.  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>Definizione di cursori sfumatura per una maschera di opacità  
 Nell'esempio precedente, il colore <xref:System.Windows.Media.Colors.Black%2A> definito dal sistema viene utilizzato come colore iniziale della sfumatura. Poiché tutti i colori <xref:System.Windows.Media.Colors> della classe, ad eccezione <xref:System.Windows.Media.Colors.Transparent%2A>di, sono completamente opachi, possono essere usati per definire semplicemente un colore iniziale per una maschera di opacità della sfumatura.  
  
 Per un controllo aggiuntivo sui valori alfa durante la definizione di una maschera di opacità, è possibile specificare il canale alfa dei colori usando la notazione esadecimale ARGB nel markup o usando il <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> metodo.  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>Specifica dell'opacità di colore in "XAML"  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]è possibile usare la notazione esadecimale ARGB per specificare l'opacità dei singoli colori. La notazione esadecimale ARGB usa la sintassi seguente:  
  
 `#` **aa** *rrggbb*  
  
 *aa* nella riga precedente rappresenta un valore esadecimale a due cifre usato per specificare l'opacità del colore. *rr*, *gg* e *bb* rappresentano un valore esadecimale a due cifre usato per specificare la quantità di rosso, verde e blu nel colore. Ogni cifra esadecimale può avere un valore compreso tra 0 e 9 o tra A e F. 0 è il valore più basso, mentre F è il più elevato. Un valore alfa pari a 00 indica un colore completamente trasparente, mentre un valore alfa pari a FF indica un colore completamente opaco.  Nell'esempio seguente viene usata la notazione ARGB esadecimale per specificare due colori. Il primo è completamente opaco, mentre il secondo è completamente trasparente.  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>   
## <a name="using-an-image-as-an-opacity-mask"></a>Uso di un'immagine come maschera di opacità  
 È anche possibile usare le immagini come maschere di opacità. L'immagine seguente illustra un esempio. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità ImageBrush](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
Esempio di maschera di opacità  
  
 Per usare un'immagine come maschera di opacità, usare <xref:System.Windows.Media.ImageBrush> un oggetto per contenere l'immagine. Quando si crea un'immagine da usare come maschera di opacità, salvare l'immagine in un formato che supporta più livelli di trasparenza, ad esempio Portable Network Graphics (PNG). L'esempio seguente illustra il codice usato per creare la precedente illustrazione.  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>   
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>Uso di un'immagine affiancata come maschera di opacità  
 Nell'esempio seguente, la stessa immagine viene usata con un'altra <xref:System.Windows.Media.ImageBrush>, ma le funzionalità di affiancamento del pennello vengono usate per produrre riquadri del quadrato immagine 50 pixel.  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>   
## <a name="creating-an-opacity-mask-from-a-drawing"></a>Creazione di una maschera di opacità da un disegno  
 È possibile usare i disegni per creare maschere di opacità. Le forme contenute nel disegno possono essere riempite con sfumature, tinte unite, immagini o anche gli altri disegni. L'immagine seguente illustra un esempio di disegno usato come maschera di opacità. Per visualizzare le parti trasparenti della maschera viene usato uno sfondo a scacchi.  
  
 ![Oggetto con maschera di opacità DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
Esempio di maschera di opacità DrawingBrush  
  
 Per usare un disegno come maschera di opacità, usare <xref:System.Windows.Media.DrawingBrush> un oggetto per contenere il disegno. L'esempio seguente illustra il codice usato per creare la precedente illustrazione:  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>   
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>Uso di un disegno affiancato come maschera di opacità  
 Analogamente a <xref:System.Windows.Media.DrawingBrush> ,èpossibilefareinmodocheilrelativodisegno<xref:System.Windows.Media.ImageBrush>venga affiancato. Nell'esempio seguente viene usato un pennello da disegno per creare una maschera di opacità affiancata.  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
