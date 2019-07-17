---
title: Cenni sul disegno con colori a tinta unita e sfumature
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- painting with gradients [WPF]
- gradients [WPF], painting with
- brushes [WPF], painting with solid colors
- brushes [WPF], painting with gradients
- painting with solid colors [WPF]
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
ms.openlocfilehash: 5ba8127d5be24a9fdcccf0bebcc08e5699d98033
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238394"
---
# <a name="painting-with-solid-colors-and-gradients-overview"></a>Cenni sul disegno con colori a tinta unita e sfumature
In questo argomento viene descritto come utilizzare <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush>, e <xref:System.Windows.Media.RadialGradientBrush> oggetti da disegnare con colori a tinta unita, sfumature lineari e radiali.  

<a name="solidcolor"></a>   
## <a name="painting-an-area-with-a-solid-color"></a>Disegno di un'area con un colore a tinta unita  
 Una delle operazioni più comuni in qualsiasi piattaforma consiste nel disegnare un'area con un solido <xref:System.Windows.Media.Color>. A tale scopo, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il <xref:System.Windows.Media.SolidColorBrush> classe. Le sezioni seguenti descrivono i diversi modi con cui disegnare un <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="solidcolorinxaml"></a>   
### <a name="using-a-solidcolorbrush-in-xaml"></a>Uso di una classe SolidColorBrush in "XAML"  
 Per disegnare un'area con un colore a tinta unita in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare una delle opzioni seguenti.  
  
- Selezionare un pennello tinta unita predefinito in base al nome.  Ad esempio, è possibile impostare un pulsante <xref:System.Windows.Controls.Control.Background%2A> "Red" o "MediumBlue".  Per un elenco di altri predefinite pennelli a tinta unita, vedere le proprietà statiche del <xref:System.Windows.Media.Brushes> classe. Di seguito è riportato un esempio.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
- Scegliere un colore dalla tavolozza dei colori a 32 bit specificando la quantità di rosso, verde e blu da combinare in un solo colore a tinta unita.  Il formato per specificare un colore dalla tavolozza a 32 bit è " *#rrggbb*", dove *rr* è un numero esadecimale a due cifre che specifica la quantità relativa di rosso, *gg* specifica la quantità di colore verde e *bb* specifica la quantità di blu.  Il colore può essere specificato anche come "#*aarrggbb*" in cui *aa* specifica il valore *alpha* o la trasparenza del colore. Questo approccio consente di creare colori parzialmente trasparenti.  Nell'esempio seguente, il <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button> è impostata su un rosso completamente opaco tramite notazione esadecimale.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
- Usare la sintassi di tag di proprietà per descrivere un <xref:System.Windows.Media.SolidColorBrush>. Questa sintassi è più dettagliata ma consente di specificare impostazioni aggiuntive, ad esempio l'opacità del pennello. Nell'esempio seguente, il <xref:System.Windows.Controls.Control.Background%2A> delle proprietà di due <xref:System.Windows.Controls.Button> elementi vengono impostati su un rosso completamente opaco. Il colore del primo pennello viene descritto usando un nome di colore predefinito. Il colore del secondo pennello viene descritto tramite notazione esadecimale.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### <a name="painting-with-a-solidcolorbrush-in-code"></a>Disegno con una classe SolidColorBrush nel codice  
 Per disegnare un'area con un colore a tinta unita nel codice, usare una delle opzioni seguenti.  
  
- Usare uno dei pennelli predefiniti offerti dal <xref:System.Windows.Media.Brushes> classe. Nell'esempio seguente, il <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button> è impostata su <xref:System.Windows.Media.Brushes.Red%2A>.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
- Creare un <xref:System.Windows.Media.SolidColorBrush> e impostare relativi <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà usando un <xref:System.Windows.Media.Color> struttura. È possibile usare un colore predefinito nella <xref:System.Windows.Media.Colors> classe oppure è possibile creare un <xref:System.Windows.Media.Color> usando il metodo statico <xref:System.Windows.Media.Color.FromArgb%2A> (metodo).  
  
     Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush> usando un colore predefinito.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 Il metodo statico <xref:System.Windows.Media.Color.FromArgb%2A> consente di specificare i valori del colore alfa, rosso, verde e blu. L'intervallo tipico per ognuno di questi valori è 0-255. Un valore alfa ad esempio pari a 0 indica che un colore è completamente trasparente e un valore pari a 255 indica che il colore è completamente opaco. Analogamente, un valore 0 relativo al colore rosso indica la totale assenza di rosso nel colore mentre un valore 255 indica la quantità di rosso massima possibile.  Nell'esempio seguente viene descritto il colore di un pennello specificando i valori alfa, rosso, verde e blu.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Per altri modi specificare colori, vedere il <xref:System.Windows.Media.Color> argomento di riferimento.  
  
<a name="gradient"></a>   
## <a name="painting-an-area-with-a-gradient"></a>Disegno di un'area con una sfumatura  
 Un pennello sfumato consente di disegnare un'area con più colori che si fondono tra loro lungo un asse. È possibile usarlo per creare luci e ombre offrendo ai controlli un effetto tridimensionale. È anche possibile usarlo per simulare l'effetto cristallo, cromato, acqua e altre superfici uniformi.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono disponibili due tipi di pennelli sfumati: <xref:System.Windows.Media.LinearGradientBrush> e <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## <a name="linear-gradients"></a>Sfumature lineari  
 Oggetto <xref:System.Windows.Media.LinearGradientBrush> disegna un'area con una sfumatura definita lungo una linea, il *asse delle sfumature*.  Specificare i colori delle sfumature e le relative posizioni lungo l'asse delle sfumature usando <xref:System.Windows.Media.GradientStop> oggetti.  È anche possibile modificare l'asse delle sfumature, che consente di creare sfumature orizzontali e verticali e di invertire la direzione della sfumatura. L'asse delle sfumature viene descritto nella sezione successiva. Per impostazione predefinita, viene creata una sfumatura diagonale.  
  
 L'esempio seguente illustra il codice che crea una sfumatura lineare con quattro colori.  
  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Il codice produce la sfumatura seguente:  
  
 ![Una sfumatura lineare diagonale](./media/wcpsdk-graphicsmm-diaglgradient-nolabel.jpg "wcpsdk_graphicsmm_diaglgradient_nolabel")  
  
 **Nota:** Gli esempi di sfumature in questo argomento usano il sistema di coordinate predefinito per l'impostazione di punti iniziali e quelli finali. Il sistema di coordinate è relativo a un rettangolo: 0 indica 0% del rettangolo di selezione e 1 indica il 100% del rettangolo. È possibile modificare il sistema di coordinate impostando il <xref:System.Windows.Media.GradientBrush.MappingMode%2A> il valore della proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Il <xref:System.Windows.Media.GradientStop> è il blocco predefinito di base di un pennello sfumato.  Un cursore sfumatura specifica un <xref:System.Windows.Media.GradientStop.Color%2A> in un <xref:System.Windows.Media.GradientStop.Offset%2A> lungo l'asse delle sfumature.  
  
- Lo sfumatura <xref:System.Windows.Media.GradientStop.Color%2A> proprietà specifica il colore del cursore sfumatura. È possibile impostare il colore usando un colore predefinito (fornito dal <xref:System.Windows.Media.Colors> classe) oppure specificando i valori ScRGB o ARGB. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile usare la notazione esadecimale per descrivere un colore. Per altre informazioni, vedere il <xref:System.Windows.Media.Color> struttura.  
  
- Lo sfumatura <xref:System.Windows.Media.GradientStop.Offset%2A> proprietà specifica la posizione del colore del cursore sfumatura sull'asse delle sfumature. L'offset è un <xref:System.Double> compreso nell'intervallo da 0 a 1. Più il valore offset del cursore sfumatura si avvicina a 0, più il colore è vicino all'inizio della sfumatura. Più il valore offset della sfumatura si avvicina a 1, più il colore è vicino alla fine della sfumatura.  
  
 Il colore di ogni punto tra i cursori sfumatura è interpolato linearmente come combinazione del colore specificato dai due cursori sfumatura di delimitazione. L'immagine seguente illustra i cursori sfumatura dell'esempio precedente. I cerchi indicano la posizione dei cursori sfumatura e la linea tratteggiata indica l'asse delle sfumature.  
  
 ![Cursori sfumatura in una sfumatura lineare](./media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk_graphicsmm_4gradientstops")  
  
 Il primo cursore sfumatura specifica il colore giallo in un offset di `0.0`.  Il secondo cursore sfumatura specifica il colore rosso in un offset di `0.25`.  I punti tra questi due cursori cambiano gradualmente da giallo a rosso quando ci si sposta da sinistra a destra lungo l'asse delle sfumature.  Il terzo cursore sfumatura specifica il colore blu in un offset di `0.75`.  I punti tra il secondo e il terzo cursore sfumatura cambiano gradualmente da rosso a blu. Il quarto cursore sfumatura specifica il colore verde lime in un offset di `1.0`. I punti tra il terzo e il quarto cursore sfumatura cambiano gradualmente da blu a verde lime.  
  
<a name="gradientaxis"></a>   
### <a name="the-gradient-axis"></a>Asse delle sfumature  
 Come accennato in precedenza, i cursori sfumatura di un pennello sfumato lineare sono posizionati lungo una riga, l'asse delle sfumature. È possibile modificare l'orientamento e dimensioni della riga usando la proprietà del pennello <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> proprietà. Mediante la modifica del pennello <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, è possibile creare orizzontale e verticale sfumature, invertire la direzione della sfumatura, ridurre la sfumatura e altro ancora.  
  
 Per del impostazione predefinita, il pennello sfumato lineare <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> riguardano l'area da disegnare. Il punto (0,0) rappresenta l'angolo superiore sinistro dell'area da disegnare e (1,1) rappresenta l'angolo inferiore destro dell'area da disegnare. Il valore predefinito <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> di un <xref:System.Windows.Media.LinearGradientBrush> è (0,0) e il valore predefinito <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> è (1,1), che consente di creare una sfumatura diagonale partendo dall'angolo superiore sinistro all'angolo inferiore destro dell'area da disegnare. La figura seguente mostra l'asse delle sfumature del pennello sfumato lineare con impostazione predefinita <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>.  
  
 ![Asse delle sfumature per una sfumatura lineare diagonale](./media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk_graphicsmm_diagonalgradientaxis")  
  
 Nell'esempio seguente viene illustrato come creare un oggetto orizzontale della sfumatura, specificando il pennello <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>. Si noti che i cursori sfumatura è le stesse degli esempi precedenti. modificando semplicemente il <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, la sfumatura è cambiata da diagonale in orizzontale.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 La figura seguente illustra la sfumatura che è stata creata. L'asse delle sfumature è contrassegnato con una linea tratteggiata e i cursori sfumatura sono contrassegnati con cerchi.  
  
 ![Asse delle sfumature per una sfumatura lineare orizzontale](./media/wcpsdk-graphicsmm-horizontalgradient.jpg "wcpsdk_graphicsmm_horizontalgradient")  
  
 L'esempio seguente illustra come creare una sfumatura verticale.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 La figura seguente illustra la sfumatura che è stata creata. L'asse delle sfumature è contrassegnato con una linea tratteggiata e i cursori sfumatura sono contrassegnati con cerchi.  
  
 ![Asse delle sfumature per una sfumatura verticale](./media/wcpsdk-graphicsmm-verticalgradient.jpg "wcpsdk_graphicsmm_verticalgradient")  
  
<a name="radialgradients"></a>   
## <a name="radial-gradients"></a>Sfumature radiali  
 Ad esempio un <xref:System.Windows.Media.LinearGradientBrush>, un <xref:System.Windows.Media.RadialGradientBrush> disegna un'area con colori che si fondono lungo un asse. Negli esempi precedenti è stato illustrato come l'asse di un pennello sfumato lineare sia una linea retta. Un asse del pennello sfumato radiale è definito da un cerchio. I relativi colori di "radiate" irradiano verso l'esterno partendo dall'origine.  
  
 Nell'esempio seguente viene usato un pennello sfumato radiale per disegnare l'area interna di un rettangolo.  
  
 [!code-xaml[GradientBrushExamples_snip#RadialGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 La figura seguente illustra la sfumatura creata nell'esempio precedente. I cursori sfumatura del pennello sono stati evidenziati. Si noti che, anche se i risultati sono diversi, i cursori sfumatura in questo esempio sono identici a quelli degli esempi precedenti del pennello sfumato lineare.  
  
 ![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
 Il <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> specifica la posizione iniziale dell'asse delle sfumature del pennello sfumato radiale. L'asse delle sfumature si irradia dall'origine della sfumatura fino al cerchio della sfumatura. Cerchio della sfumatura del pennello è definito dal relativo <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, e <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> proprietà.  
  
 La figura seguente illustra numerose sfumature radiali con diversi <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, e <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> impostazioni.  
  
 ![RadialGradientBrush settings](./media/wcpsdk-graphicsmm-originscirclesandradii.gif "wcpsdk_graphicsmm_originscirclesandradii")  
Oggetto RadialGradientBrushes con impostazioni GradientOrigin, Center, RadiusX e RadiusY diverse.  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-transparent-or-partially-transparent-gradient-stops"></a>Specifica dei cursori sfumatura trasparenti o parzialmente trasparenti  
 Poiché i cursori sfumatura non si specifica una proprietà di opacità, è necessario specificare il canale alfa dei colori usando la notazione esadecimale ARGB nel markup oppure usando il <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> metodo per creare cursori sfumatura trasparenti o parzialmente trasparenti. Le sezioni seguenti illustrano come creare cursori sfumatura parzialmente trasparenti in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e nel codice.  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>Specifica dell'opacità di colore in "XAML"  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], si usa la notazione esadecimale ARGB per specificare l'opacità di colori singoli. La notazione esadecimale ARGB Usa la sintassi seguente:  
  
 `#` **aa** *rrggbb*  
  
 *aa* nella riga precedente rappresenta un valore esadecimale a due cifre usato per specificare l'opacità del colore. *rr*, *gg* e *bb* rappresentano un valore esadecimale a due cifre usato per specificare la quantità di rosso, verde e blu nel colore. Ogni cifra esadecimale può avere un valore compreso tra 0 e 9 o tra A e F. 0 è il valore più basso, mentre F è il più elevato. Un valore alfa pari a 00 indica un colore completamente trasparente, mentre un valore alfa pari a FF indica un colore completamente opaco.  Nell'esempio seguente, la notazione esadecimale ARGB consente di specificare due colori. Il primo è parzialmente trasparente (con valore alfa pari a x20), mentre il secondo è completamente opaco.  
  
 [!code-xaml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### <a name="specifying-color-opacity-in-code"></a>Specifica dell'opacità di colore nel codice  
 Quando si usa codice, il metodo statico <xref:System.Windows.Media.Color.FromArgb%2A> metodo consente di specificare un valore alfa quando si crea un colore. Il metodo accetta quattro parametri di tipo <xref:System.Byte>. Il primo parametro specifica il canale alfa del colore. Gli altri tre parametri specificano i valori rosso, verde e blu del colore. Ogni valore deve essere compreso tra 0 e 255 inclusi. Un valore alfa pari a 0 indica che un colore è completamente trasparente e un valore alfa pari a 255 indica che il colore è completamente opaco. Nell'esempio seguente, il <xref:System.Windows.Media.Color.FromArgb%2A> metodo viene utilizzato per produrre due colori. Il primo colore è parzialmente trasparente (con valore alfa pari a 32), mentre il secondo è completamente opaco.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 In alternativa, è possibile usare il <xref:System.Windows.Media.Color.FromScRgb%2A> metodo, che consente di usare i valori ScRGB per creare un colore.  
  
<a name="otherbrushes"></a>   
## <a name="painting-with-images-drawings-visuals-and-patterns"></a>Disegno con oggetti Images, Drawings, Visuals e Patterns  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, e <xref:System.Windows.Media.VisualBrush> classi consentono di disegnare un'area con immagini, disegni o gli oggetti visivi. Per informazioni sul disegno con immagini, disegni e modelli, vedere [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Panoramica sulle proprietà di trasformazione Brush](brush-transformation-overview.md)
- [Livelli di rendering della grafica](../advanced/graphics-rendering-tiers.md)
