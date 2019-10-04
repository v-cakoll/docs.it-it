---
title: Cenni preliminari sulla creazione dell'immagine
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: f8686a189883bed782cdde80e56c87ab6dbe404a
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835019"
---
# <a name="imaging-overview"></a>Cenni preliminari sulla creazione dell'immagine
Questo argomento offre un'introduzione a [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] consente agli sviluppatori di visualizzare, trasformare e formattare le immagini.  

## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] offre miglioramenti significativi nelle funzionalità di creazione delle immagini all'interno di [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Le funzionalità di creazione di immagini, ad esempio la visualizzazione di una bitmap o l'uso di un'immagine in un controllo comune, dipendono in precedenza dalle librerie Microsoft Windows Graphics Device Interface (GDI) o GDI+ di Microsoft Windows. Queste API offrono funzionalità di imaging di base, ma non dispongono di funzionalità come il supporto per l'estendibilità dei codec e il supporto per immagini ad alta fedeltà. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] è progettato per superare le carenze di GDI e GDI+ e offrire un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Esistono due modi per accedere all' [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] API, un componente gestito e un componente non gestito. Il componente non gestito fornisce le funzionalità riportate di seguito.  
  
- Modello di estendibilità per formati di immagine nuovi o proprietari.  
  
- Miglioramento delle prestazioni e della sicurezza nei formati di immagini native, tra cui bitmap (BMP), gruppo di esperti di fotografica (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], Graphics Interchange Format (GIF) e icona (. ico).  
  
- Conservazione dei dati di immagini con intensità fino a 8 bit per canale (32 bit per pixel).  
  
- Ridimensionamento, ritaglio e rotazione delle immagini non distruttivi.  
  
- Gestione dei colori semplificata.  
  
- Supporto per i metadati proprietari all'interno dei file.  
  
- Il componente gestito usa l'infrastruttura non gestita per fornire l'integrazione di immagini con altre funzionalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ad esempio [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animazione e grafica. Il componente gestito trae anche vantaggio dal modello di estendibilità del codec di imaging Windows Presentation Foundation (WPF), che consente il riconoscimento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] automatico dei nuovi formati di immagini nelle applicazioni.  
  
 La maggior parte dell'API [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] gestita risiede <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> nello spazio dei nomi, anche se molti tipi <xref:System.Windows.Media.ImageBrush> importanti, ad esempio <xref:System.Windows.Media.ImageDrawing> e si trovano nello <xref:System.Windows.Media?displayProperty=nameWithType> spazio dei <xref:System.Windows.Controls.Image> nomi e si trovano nel <xref:System.Windows.Controls?displayProperty=nameWithType> namespace.  
  
 Questo argomento include informazioni aggiuntive sul componente gestito. Per ulteriori informazioni sull'API non gestita, vedere la documentazione relativa ai componenti per la [creazione di immagini WPF non gestite](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formati di immagini WPF  
 Viene usato un codec per decodificare o codificare un formato multimediale specifico. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] include un codec per i formati di immagine BMP, JPEG, PNG, TIFF, [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], GIF e ICON. Ognuno di questi codec consente alle applicazioni di decodificare e, ad eccezione di ICON, codificare i rispettivi formati di immagine.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>è una classe importante utilizzata per la decodifica e la codifica delle immagini. Si tratta del blocco predefinito di base della pipeline di [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] e rappresenta un set unico e costante di pixel a una specifica dimensione e risoluzione. Un <xref:System.Windows.Media.Imaging.BitmapSource> può essere un singolo frame di un'immagine a più frame oppure il risultato di una trasformazione eseguita su un oggetto <xref:System.Windows.Media.Imaging.BitmapSource>. È l'elemento padre di molte delle classi primarie utilizzate nella [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] creazione di immagini <xref:System.Windows.Media.Imaging.BitmapFrame>, ad esempio.  
  
 Un <xref:System.Windows.Media.Imaging.BitmapFrame> oggetto viene utilizzato per archiviare i dati bitmap effettivi di un formato di immagine. Molti formati di immagine supportano solo un singolo <xref:System.Windows.Media.Imaging.BitmapFrame>, anche se i formati quali GIF e TIFF supportano più frame per ogni immagine. I fotogrammi vengono usati dai decodificatori come dati di input e vengono passati ai codificatori per creare file di immagine.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Imaging.BitmapFrame> da un <xref:System.Windows.Media.Imaging.BitmapSource> e quindi aggiungerlo a un'immagine TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodifica dei formati di immagine  
 La decodifica delle immagini è la conversione di un formato di immagine in dati di immagine che possono essere usati dal sistema. I dati dell'immagine possono quindi essere usati per visualizzare, elaborare o eseguire la codifica in un formato diverso. La scelta del decodificatore varia a seconda del formato di immagine. La selezione del codec è automatica, a meno che non si indichi un decodificatore specifico. Gli esempi nella sezione [Visualizzazione di immagini in WPF](#_displayingimages) illustrano la decodifica automatica. I decodificatori di formati personalizzati sviluppati usando le interfacce [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] non gestite e registrati con il sistema influiscono automaticamente sulla selezione del decodificatore. In questo modo i formati personalizzati vengono visualizzati automaticamente nelle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Nell'esempio seguente viene illustrato l'utilizzo di un decodificatore bitmap per decodificare un'immagine in formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codifica dei formati di immagine  
 La codifica delle immagini è la conversione di dati di immagine in un formato di immagine specifico. I dati di immagine codificati possono quindi essere usati per creare nuovi file di immagine. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] fornisce codificatori per ciascun formato di immagine descritto in precedenza.  
  
 L'esempio seguente illustra l'uso di un codificatore per salvare un'immagine bitmap appena creata.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Visualizzazione di immagini in WPF  
 Esistono diversi modi per visualizzare un'immagine in un'applicazione Windows Presentation Foundation (WPF). Le immagini possono essere visualizzate utilizzando <xref:System.Windows.Controls.Image> un controllo, dipinte su un oggetto <xref:System.Windows.Media.ImageBrush>visivo utilizzando un oggetto o <xref:System.Windows.Media.ImageDrawing>disegnate utilizzando un oggetto.  
  
### <a name="using-the-image-control"></a>Uso del controllo Image  
 <xref:System.Windows.Controls.Image>è un elemento del Framework e il modo principale per visualizzare le immagini nelle applicazioni. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> può essere usato in due modi, ovvero la sintassi dell'attributo o la sintassi delle proprietà. L'esempio seguente mostra come eseguire il rendering di un'immagine con una larghezza di 200 pixel mediante la sintassi di attributo e la sintassi di tag di proprietà. Per altre informazioni sulla sintassi di attributo e di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Molti esempi usano un <xref:System.Windows.Media.Imaging.BitmapImage> oggetto per fare riferimento a un file di immagine. <xref:System.Windows.Media.Imaging.BitmapImage>è un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> specializzato ottimizzato per [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] il caricamento ed è un modo semplice per visualizzare le <xref:System.Windows.Controls.Image.Source%2A> immagini come di <xref:System.Windows.Controls.Image> un controllo.  
  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>implementa l' <xref:System.ComponentModel.ISupportInitialize> interfaccia per ottimizzare l'inizializzazione su più proprietà. Le proprietà possono essere modificate solo durante l'inizializzazione degli oggetti. Chiamare <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> per segnalare che l'inizializzazione è <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> iniziata e per segnalare che l'inizializzazione è stata completata. Dopo aver eseguito l'inizializzazione, le modifiche alle proprietà verranno ignorate.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Rotazione, conversione e ritaglio di immagini  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]consente agli utenti di trasformare le immagini usando le <xref:System.Windows.Media.Imaging.BitmapImage> proprietà di o usando <xref:System.Windows.Media.Imaging.BitmapSource> oggetti aggiuntivi, <xref:System.Windows.Media.Imaging.CroppedBitmap> ad <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>esempio o. Queste trasformazioni di immagini possono ridimensionare, ruotare, modificare il formato dei pixel o ritagliare un'immagine.  
  
 Le rotazioni delle immagini vengono eseguite <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> utilizzando la <xref:System.Windows.Media.Imaging.BitmapImage>proprietà di. Le rotazioni possono essere eseguite solo in incrementi di 90 gradi. Nell'esempio seguente un'immagine viene ruotata di 90 gradi.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversione di un'immagine in un formato pixel diverso, ad esempio le <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>gradazioni di grigio, viene eseguita utilizzando. Negli esempi seguenti viene convertita <xref:System.Windows.Media.PixelFormats.Gray4%2A>un'immagine in.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Per ritagliare un'immagine, è <xref:System.Windows.UIElement.Clip%2A> possibile usare <xref:System.Windows.Controls.Image> la <xref:System.Windows.Media.Imaging.CroppedBitmap> proprietà di o. In genere, se si desidera visualizzare solo una parte di un'immagine, <xref:System.Windows.UIElement.Clip%2A> è necessario utilizzare. Se è necessario codificare e salvare un'immagine ritagliata <xref:System.Windows.Media.Imaging.CroppedBitmap> , è necessario usare. Nell'esempio seguente un'immagine viene ritagliata utilizzando la proprietà clip utilizzando un <xref:System.Windows.Media.EllipseGeometry>oggetto.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Adattamento delle immagini  
 La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà controlla il modo in cui un'immagine viene allungata per riempire il relativo contenitore. La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà accetta i valori seguenti, definiti <xref:System.Windows.Media.Stretch> dall'enumerazione:  
  
- <xref:System.Windows.Media.Stretch.None>: L'immagine non viene adattata per riempire l'area di output. Se l'immagine è più grande dell'area di output, viene disegnata al suo interno, escludendo gli elementi in eccesso.  
  
- <xref:System.Windows.Media.Stretch.Fill>: L'immagine viene ridimensionata in base all'area di output. Poiché l'altezza e la larghezza dell'immagine vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali dell'immagine. In altre parole, l'immagine potrebbe essere distorta per adattarsi completamente al contenitore dell'output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: L'immagine viene ridimensionata in modo da adattarla completamente all'area di output. Vengono mantenute le proporzioni dell'immagine.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: L'immagine viene ridimensionata in modo da riempire completamente l'area di output mantenendo le proporzioni originali dell'immagine.  
  
 Nell'esempio seguente viene applicata ogni enumerazione disponibile <xref:System.Windows.Media.Stretch> a un oggetto. <xref:System.Windows.Controls.Image>  
  
 La figura seguente mostra l'output dell'esempio e illustra l'effetto delle diverse <xref:System.Windows.Controls.Image.Stretch%2A> impostazioni quando vengono applicate a un'immagine.  
  
 ![Different TileBrush Stretch settings](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Impostazioni Stretch diverse  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Disegnare con immagini  
 Le immagini possono essere visualizzate anche in un'applicazione mediante disegno con <xref:System.Windows.Media.Brush>un. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini. Per disegnare con immagini, usare un <xref:System.Windows.Media.ImageBrush>oggetto. Un <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush> che definisce il contenuto come immagine bitmap. Un <xref:System.Windows.Media.ImageBrush> oggetto Visualizza una singola immagine, specificata dalla relativa <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà. È possibile controllare il modo in cui l'immagine viene adattata, allineata e affiancata, consentendo di evitare distorsioni e produrre motivi e altri effetti. Nella figura seguente vengono illustrati alcuni effetti che è possibile ottenere <xref:System.Windows.Media.ImageBrush>con un.  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
I pennelli immagine possono riempire forme, controlli, testo e altro ancora  
  
 Nell'esempio seguente viene illustrato come disegnare lo sfondo di un pulsante con un'immagine utilizzando un <xref:System.Windows.Media.ImageBrush>oggetto.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Per altre informazioni sulle <xref:System.Windows.Media.ImageBrush> immagini e sul disegno, vedere [disegnare con immagini, disegni e](painting-with-images-drawings-and-visuals.md)oggetti visivi.  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadati delle immagini  
 Alcuni file di immagine contengono metadati che descrivono il contenuto o le caratteristiche del file. La maggior parte delle fotocamere digitali, ad esempio, crea immagini che contengono i metadati relativi a marca e modello della fotocamera usata per acquisire l'immagine. Ogni formato di immagine gestisce i metadati in modo diverso, ma [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] offre un metodo uniforme per archiviare e recuperare i metadati per ogni formato di immagine supportato.  
  
 L'accesso ai metadati viene fornito tramite <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> la proprietà di <xref:System.Windows.Media.Imaging.BitmapSource> un oggetto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>Restituisce un <xref:System.Windows.Media.Imaging.BitmapMetadata> oggetto che include tutti i metadati contenuti nell'immagine. Questi dati possono essere in uno schema di metadati o in una combinazione di schemi diversi. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] supporta gli schemi dei metadati delle immagini seguenti: File di immagine scambiabile (EXIF), testo (dati testuali PNG), directory file di immagine (IFD), International Press Telecommunications Council (IPTC) e [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Per semplificare il processo di lettura dei metadati, <xref:System.Windows.Media.Imaging.BitmapMetadata> fornisce diverse proprietà denominate a cui è possibile accedere facilmente, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>ad esempio <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>, e. Molte di queste proprietà denominate consentono anche di scrivere metadati. Il lettore di query dei metadati fornisce supporto aggiuntivo per la lettura dei metadati. Il <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> metodo viene utilizzato per recuperare un lettore di query di metadati fornendo una query di tipo stringa, ad esempio *"/app1/exif/"* . Nell'esempio <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> seguente viene usato per ottenere il testo archiviato nel percorso *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Per scrivere i metadati viene usato il relativo writer di query. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>Ottiene il writer di query e imposta il valore desiderato. Nell'esempio <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> seguente viene usato per scrivere il testo archiviato nel percorso *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Estendibilità dei codec  
 Il modello di estendibilità per i nuovi codec di immagini è una funzionalità fondamentale di [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]. Queste interfacce non gestite consentono agli sviluppatori di codec di integrare i codec con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], per consentire l'uso automatico di nuovi formati di immagine da parte delle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Per un esempio di API di estendibilità, vedere il [codec di esempio Win32](https://go.microsoft.com/fwlink/?LinkID=160052). Questo esempio spiega come creare un decodificatore e un codificatore per un formato di immagine personalizzato.  
  
> [!NOTE]
> Il codec deve essere firmato digitalmente per il sistema affinché venga riconosciuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Codec di esempio di Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
