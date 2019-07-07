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
ms.openlocfilehash: b84a2e4c3cf4126a6efa7edaf868080dbc48b859
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610383"
---
# <a name="imaging-overview"></a>Cenni preliminari sulla creazione dell'immagine
Questo argomento offre un'introduzione a [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] consente agli sviluppatori di visualizzare, trasformare e formattare le immagini.  

<a name="_wpfImaging"></a>   
## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] offre miglioramenti significativi nelle funzionalità di creazione delle immagini all'interno di [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Le funzionalità di creazione delle immagini, ad esempio la visualizzazione di una bitmap o l'uso di un'immagine in un controllo comune, si basavano in precedenza sulle librerie [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] o [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)]. Queste API forniscono funzionalità, ma la mancanza di funzionalità, ad esempio il supporto per l'estendibilità dei codec e supporto per le immagini ad alta fedeltà di creazione dell'immagine di base. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] è progettato per colmare le carenze di [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] e [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] e fornire un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Esistono due modi per accedere la [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] API, un componente gestito e un componente non gestito. Il componente non gestito fornisce le funzionalità riportate di seguito.  
  
- Modello di estendibilità per formati di immagine nuovi o proprietari.  
  
- Miglioramento di prestazioni e sicurezza nei formati di immagine nativi, tra cui [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] e ICON (.ico).  
  
- Conservazione dei dati di immagini con intensità fino a 8 bit per canale (32 bit per pixel).  
  
- Ridimensionamento, ritaglio e rotazione delle immagini non distruttivi.  
  
- Gestione dei colori semplificata.  
  
- Supporto per i metadati proprietari all'interno dei file.  
  
- Il componente gestito usa l'infrastruttura non gestita per fornire l'integrazione di immagini con altre funzionalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ad esempio [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animazione e grafica. Il componente gestito sfrutta inoltre da di Windows Presentation Foundation (WPF) imaging codec modello di estendibilità che consente il riconoscimento automatico dei nuovi formati di immagine in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni.  
  
 La maggior parte delle managed [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] API si trovano nel <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> dello spazio dei nomi, anche se diverse importanti tipi, ad esempio <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.ImageDrawing> si trovano nel <xref:System.Windows.Media?displayProperty=nameWithType> dello spazio dei nomi e <xref:System.Windows.Controls.Image> risiede nel <xref:System.Windows.Controls?displayProperty=nameWithType> spazio dei nomi.  
  
 Questo argomento include informazioni aggiuntive sul componente gestito. Per altre informazioni sul, vedere API non gestite di [Unmanaged WPF Imaging Component](/windows/desktop/wic/-wic-lh) documentazione.  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formati di immagini WPF  
 Viene usato un codec per decodificare o codificare un formato multimediale specifico. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] include un codec per i formati di immagine [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] e ICON. Ognuno di questi codec consente alle applicazioni di decodificare e, ad eccezione di ICON, codificare i rispettivi formati di immagine.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> è una classe importante usata nella decodifica e codifica di immagini. Si tratta del blocco predefinito di base della pipeline di [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] e rappresenta un set unico e costante di pixel a una specifica dimensione e risoluzione. Oggetto <xref:System.Windows.Media.Imaging.BitmapSource> può essere un singolo frame di un'immagine a più fotogrammi o può essere il risultato di una trasformazione eseguita su un <xref:System.Windows.Media.Imaging.BitmapSource>. È il padre di molte delle classi principali usate nella [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] imaging, ad esempio <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Oggetto <xref:System.Windows.Media.Imaging.BitmapFrame> viene usato per archiviare i dati bitmap effettivi di un formato di immagine. Molti formati di immagine supportano un solo <xref:System.Windows.Media.Imaging.BitmapFrame>, anche se, ad esempio formatta [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] e [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] supportino più fotogrammi per immagine. I fotogrammi vengono usati dai decodificatori come dati di input e vengono passati ai codificatori per creare file di immagine.  
  
 Nell'esempio seguente viene illustrato come un <xref:System.Windows.Media.Imaging.BitmapFrame> creata da un <xref:System.Windows.Media.Imaging.BitmapSource> e quindi aggiunto a un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] immagine.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodifica dei formati di immagine  
 La decodifica delle immagini è la conversione di un formato di immagine in dati di immagine che possono essere usati dal sistema. I dati dell'immagine possono quindi essere usati per visualizzare, elaborare o eseguire la codifica in un formato diverso. La scelta del decodificatore varia a seconda del formato di immagine. La selezione del codec è automatica, a meno che non si indichi un decodificatore specifico. Gli esempi nella sezione [Visualizzazione di immagini in WPF](#_displayingimages) illustrano la decodifica automatica. I decodificatori di formati personalizzati sviluppati usando le interfacce [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] non gestite e registrati con il sistema influiscono automaticamente sulla selezione del decodificatore. In questo modo i formati personalizzati vengono visualizzati automaticamente nelle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 L'esempio seguente illustra l'uso di un decodificatore di bitmap per decodificare un'immagine con formato [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)].  
  
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
 Esistono diversi modi per visualizzare un'immagine in un'applicazione Windows Presentation Foundation (WPF). È possibile visualizzare immagini usando un <xref:System.Windows.Controls.Image> controllo, disegnate su un oggetto visivo usando un' <xref:System.Windows.Media.ImageBrush>, oppure disegnate tramite un <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Uso del controllo Image  
 <xref:System.Windows.Controls.Image> è un elemento del framework e il modo principale per visualizzare le immagini nelle applicazioni. Nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> può essere usato in due modi; la sintassi di attributo o proprietà. L'esempio seguente mostra come eseguire il rendering di un'immagine con una larghezza di 200 pixel mediante la sintassi di attributo e la sintassi di tag di proprietà. Per altre informazioni sulla sintassi di attributo e di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Molti degli esempi usano un <xref:System.Windows.Media.Imaging.BitmapImage> oggetto per fare riferimento a un file di immagine. <xref:System.Windows.Media.Imaging.BitmapImage> è un oggetto specializzato <xref:System.Windows.Media.Imaging.BitmapSource> che è ottimizzato per [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] caricamento ed è un modo semplice per visualizzare le immagini come il <xref:System.Windows.Controls.Image.Source%2A> di un <xref:System.Windows.Controls.Image> controllo.  
  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> implementa il <xref:System.ComponentModel.ISupportInitialize> interfaccia per ottimizzare l'inizializzazione su più proprietà. Le proprietà possono essere modificate solo durante l'inizializzazione degli oggetti. Chiamare <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> per segnalare che l'inizializzazione è stata avviata e <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> per segnalare che l'inizializzazione è stata completata. Dopo aver eseguito l'inizializzazione, le modifiche alle proprietà verranno ignorate.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Rotazione, conversione e ritaglio di immagini  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente agli utenti di trasformare le immagini usando proprietà del <xref:System.Windows.Media.Imaging.BitmapImage> o usando altri <xref:System.Windows.Media.Imaging.BitmapSource> oggetti, ad esempio <xref:System.Windows.Media.Imaging.CroppedBitmap> o <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Queste trasformazioni di immagini possono ridimensionare, ruotare, modificare il formato dei pixel o ritagliare un'immagine.  
  
 La rotazione delle immagini vengono eseguita usando il <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> proprietà di <xref:System.Windows.Media.Imaging.BitmapImage>. Le rotazioni possono essere eseguite solo in incrementi di 90 gradi. Nell'esempio seguente un'immagine viene ruotata di 90 gradi.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Conversione di un'immagine in un formato di pixel diversa, ad esempio viene eseguita in scala di grigi usando <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Negli esempi seguenti, un'immagine viene convertita in <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Ritagliare un'immagine, ovvero il <xref:System.Windows.UIElement.Clip%2A> proprietà di <xref:System.Windows.Controls.Image> o <xref:System.Windows.Media.Imaging.CroppedBitmap> può essere utilizzato. In genere, se si desidera visualizzare una parte di un'immagine, <xref:System.Windows.UIElement.Clip%2A> deve essere utilizzato. Se è necessario codificare e salvare un'immagine ritagliata, il <xref:System.Windows.Media.Imaging.CroppedBitmap> deve essere utilizzato. Nell'esempio seguente, un'immagine viene ritagliata con la proprietà Clip usando un <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Adattamento delle immagini  
 Il <xref:System.Windows.Controls.Image.Stretch%2A> proprietà controlla il modo in cui un'immagine viene adattata per riempire il contenitore. Il <xref:System.Windows.Controls.Image.Stretch%2A> proprietà accetta i valori seguenti, definiti dal <xref:System.Windows.Media.Stretch> enumerazione:  
  
- <xref:System.Windows.Media.Stretch.None>: L'immagine non viene adattata per riempire l'area di output. Se l'immagine è più grande dell'area di output, viene disegnata al suo interno, escludendo gli elementi in eccesso.  
  
- <xref:System.Windows.Media.Stretch.Fill>: L'immagine viene adattata all'area di output. Poiché l'altezza e la larghezza dell'immagine vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali dell'immagine. In altre parole, l'immagine potrebbe essere distorta per adattarsi completamente al contenitore dell'output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: L'immagine viene ridimensionata in modo da adattarsi completamente all'interno dell'area di output. Vengono mantenute le proporzioni dell'immagine.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: L'immagine viene ridimensionata in modo da riempire completamente l'area di output, mantenendo le proporzioni originali dell'immagine.  
  
 Nell'esempio seguente applica ogni disponibili <xref:System.Windows.Media.Stretch> enumerazioni per un <xref:System.Windows.Controls.Image>.  
  
 L'immagine seguente mostra l'output dell'esempio e illustra l'effetto di diversi <xref:System.Windows.Controls.Image.Stretch%2A> impostazioni applicate a un'immagine.  
  
 ![Different TileBrush Stretch settings](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Impostazioni Stretch diverse  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Disegnare con immagini  
 Le immagini possono essere visualizzate anche in un'applicazione tramite il disegno con un <xref:System.Windows.Media.Brush>. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini. Per disegnare con immagini, usare un <xref:System.Windows.Media.ImageBrush>. Un' <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush> che definisce il proprio contenuto come un'immagine bitmap. Un' <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine specificata dal relativo <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà. È possibile controllare il modo in cui l'immagine viene adattata, allineata e affiancata, consentendo di evitare distorsioni e produrre motivi e altri effetti. La figura seguente mostra alcuni effetti che possono essere ottenute con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
I pennelli immagine possono riempire forme, controlli, testo e altro ancora  
  
 L'esempio seguente illustra come disegnare lo sfondo di un pulsante con un'immagine utilizzando un' <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Per ulteriori informazioni sul <xref:System.Windows.Media.ImageBrush> e vedere le immagini di disegno [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadati delle immagini  
 Alcuni file di immagine contengono metadati che descrivono il contenuto o le caratteristiche del file. La maggior parte delle fotocamere digitali, ad esempio, crea immagini che contengono i metadati relativi a marca e modello della fotocamera usata per acquisire l'immagine. Ogni formato di immagine gestisce i metadati in modo diverso, ma [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] offre un metodo uniforme per archiviare e recuperare i metadati per ogni formato di immagine supportato.  
  
 Accesso ai metadati viene fornito tramite il <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> proprietà di un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> Restituisce un <xref:System.Windows.Media.Imaging.BitmapMetadata> oggetto che include tutti i metadati contenuti nell'immagine. Questi dati possono essere in uno schema di metadati o in una combinazione di schemi diversi. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] supporta gli schemi di metadati di immagini seguenti: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt (PNG Textual Data), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] e [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Per semplificare il processo di lettura dei metadati, <xref:System.Windows.Media.Imaging.BitmapMetadata> include diverse proprietà denominate facilmente accessibili, ad esempio <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, e <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Molte di queste proprietà denominate consentono anche di scrivere metadati. Il lettore di query dei metadati fornisce supporto aggiuntivo per la lettura dei metadati. Il <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> metodo viene utilizzato per recuperare un lettore di query dei metadati fornendo una stringa di query, ad esempio *"/ app1/app1/exif/"* . Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> viene usato per ottenere il testo archiviato nel *"/Text/Description"* posizione.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Per scrivere i metadati viene usato il relativo writer di query. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> Ottiene il writer di query e imposta il valore desiderato. Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> utilizzato per scrivere il testo archiviato nel *"/Text/Description"* posizione.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Estendibilità dei codec  
 Il modello di estendibilità per i nuovi codec di immagini è una funzionalità fondamentale di [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]. Queste interfacce non gestite consentono agli sviluppatori di codec di integrare i codec con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], per consentire l'uso automatico di nuovi formati di immagine da parte delle applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Per un esempio di API di estensibilità, vedere la [Codec di esempio di Win32](https://go.microsoft.com/fwlink/?LinkID=160052). Questo esempio spiega come creare un decodificatore e un codificatore per un formato di immagine personalizzato.  
  
> [!NOTE]
>  Il codec deve essere firmato digitalmente per il sistema affinché venga riconosciuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Codec di esempio di Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
