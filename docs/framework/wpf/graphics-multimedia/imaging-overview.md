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
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186686"
---
# <a name="imaging-overview"></a>Cenni preliminari sulla creazione dell'immagine
In questo argomento viene fornita un'introduzione al componente di microsoft Windows Presentation Foundation Imaging. WPF ImagingWPF consente agli sviluppatori di visualizzare, trasformare e formattare le immagini.  

## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 WPF Imaging fornisce miglioramenti significativi nelle funzionalità di creazione di immagini all'interno di Microsoft Windows. Le funzionalità di creazione di immagini, ad esempio la visualizzazione di una bitmap o l'utilizzo di un'immagine in un controllo comune, in precedenza si basavano sulle librerie GDI (Graphics Device Interface) di Microsoft Windows o Microsoft Windows. Queste API forniscono funzionalità di imaging di base, ma non dispongono di funzionalità quali il supporto per l'estendibilità dei codec e il supporto delle immagini ad alta fedeltà. WPF Imaging è progettato per superare le carenze di GDI e GDI e fornire un nuovo set di API per visualizzare e utilizzare le immagini all'interno delle applicazioni.  
  
 Esistono due modi per accedere all'API WPF Imaging, un componente gestito e un componente non gestito. Il componente non gestito fornisce le funzionalità riportate di seguito.  
  
- Modello di estendibilità per formati di immagine nuovi o proprietari.  
  
- Miglioramento delle prestazioni e della sicurezza sui formati di immagine nativi, tra cui bitmap (BMP), Joint Photographics Experts Group (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), e l'icona (.ico).  
  
- Conservazione dei dati di immagini con intensità fino a 8 bit per canale (32 bit per pixel).  
  
- Ridimensionamento, ritaglio e rotazione delle immagini non distruttivi.  
  
- Gestione dei colori semplificata.  
  
- Supporto per i metadati proprietari all'interno dei file.  
  
- Il componente gestito utilizza l'infrastruttura non gestita per fornire [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]una perfetta integrazione delle immagini con altre funzionalità WPFWPF, ad esempio, animazione e grafica. Il componente gestito trae vantaggio anche dal modello di estendibilità del codec di imaging di Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation  
  
 La maggior parte dell'API WPF <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> Imaging gestita risiede nello <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.ImageDrawing> spazio dei <xref:System.Windows.Media?displayProperty=nameWithType> nomi, anche se diversi tipi importanti, ad esempio e risiedono nello spazio dei nomi e <xref:System.Windows.Controls.Image> risiedono nello <xref:System.Windows.Controls?displayProperty=nameWithType> spazio dei nomi.  
  
 Questo argomento include informazioni aggiuntive sul componente gestito. Per altre informazioni sull'API non gestita, vedere la documentazione relativa al [componente di imaging WPF non gestito.](/windows/desktop/wic/-wic-lh)  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>Formati di immagini WPF  

 Viene usato un codec per decodificare o codificare un formato multimediale specifico. WPF Imaging include un codec per i formati di immagine BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF e ICON. Ognuno di questi codec consente alle applicazioni di decodificare e, ad eccezione di ICON, codificare i rispettivi formati di immagine.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>è una classe importante utilizzata nella decodifica e codifica delle immagini. È il blocco predefinito di base della pipeline di WPF Imaging WPF e rappresenta un singolo set costante di pixel a una determinata dimensione e risoluzione. Un <xref:System.Windows.Media.Imaging.BitmapSource> oggetto può essere un singolo fotogramma di un'immagine a più <xref:System.Windows.Media.Imaging.BitmapSource>fotogrammi oppure può essere il risultato di una trasformazione eseguita su un oggetto . È l'elemento padre di molte delle classi <xref:System.Windows.Media.Imaging.BitmapFrame>principali utilizzate nell'imaging WPF, ad esempio .  
  
 Oggetto <xref:System.Windows.Media.Imaging.BitmapFrame> viene utilizzato per archiviare i dati bitmap effettivi di un formato immagine. Molti formati di immagine <xref:System.Windows.Media.Imaging.BitmapFrame>supportano solo un singolo , anche se formati come GIF e TIFF supportano più fotogrammi per immagine. I fotogrammi vengono usati dai decodificatori come dati di input e vengono passati ai codificatori per creare file di immagine.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapFrame> viene illustrato <xref:System.Windows.Media.Imaging.BitmapSource> come un viene creato da un e quindi aggiunto a un'immagine TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodifica dei formati di immagine  
 La decodifica delle immagini è la conversione di un formato di immagine in dati di immagine che possono essere usati dal sistema. I dati dell'immagine possono quindi essere usati per visualizzare, elaborare o eseguire la codifica in un formato diverso. La scelta del decodificatore varia a seconda del formato di immagine. La selezione del codec è automatica, a meno che non si indichi un decodificatore specifico. Gli esempi nella sezione [Visualizzazione di immagini in WPF](#_displayingimages) illustrano la decodifica automatica. I decodificatori di formato personalizzati sviluppati utilizzando le interfacce WPF Imaging non gestite e registrati con il sistema partecipano automaticamente alla selezione del decodificatore. In questo modo i formati personalizzati da visualizzare automaticamente nelle applicazioni WPFWPF.  
  
 Nell'esempio seguente viene illustrato l'utilizzo di un decodificatore bitmap per decodificare un'immagine in formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codifica dei formati di immagine  
 La codifica delle immagini è la conversione di dati di immagine in un formato di immagine specifico. I dati di immagine codificati possono quindi essere usati per creare nuovi file di immagine. L'imaging WPFWPF fornisce codificatori per ognuno dei formati di immagine descritti in precedenza.  
  
 L'esempio seguente illustra l'uso di un codificatore per salvare un'immagine bitmap appena creata.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>Visualizzazione di immagini in WPF  
 Esistono diversi modi per visualizzare un'immagine in un'applicazione Windows Presentation Foundation (WPF). Le immagini possono essere <xref:System.Windows.Controls.Image> visualizzate utilizzando un controllo <xref:System.Windows.Media.ImageBrush>, disegnate <xref:System.Windows.Media.ImageDrawing>su un oggetto visivo utilizzando un oggetto , oppure disegnate utilizzando un oggetto .  
  
### <a name="using-the-image-control"></a>Uso del controllo Image  
 <xref:System.Windows.Controls.Image>è un elemento del framework e il modo principale per visualizzare le immagini nelle applicazioni. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Image> , può essere utilizzato in due modi; sintassi degli attributi o sintassi delle proprietà. L'esempio seguente mostra come eseguire il rendering di un'immagine con una larghezza di 200 pixel mediante la sintassi di attributo e la sintassi di tag di proprietà. Per altre informazioni sulla sintassi degli attributi e la sintassi di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Molti degli esempi <xref:System.Windows.Media.Imaging.BitmapImage> utilizzano un oggetto per fare riferimento a un file di immagine. <xref:System.Windows.Media.Imaging.BitmapImage>è un <xref:System.Windows.Media.Imaging.BitmapSource> specializzato che [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] è ottimizzato per il caricamento <xref:System.Windows.Controls.Image.Source%2A> ed <xref:System.Windows.Controls.Image> è un modo semplice per visualizzare le immagini come il di un controllo.  
  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>implementa <xref:System.ComponentModel.ISupportInitialize> l'interfaccia per ottimizzare l'inizializzazione su più proprietà. Le proprietà possono essere modificate solo durante l'inizializzazione degli oggetti. Chiamata <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> per segnalare che <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> l'inizializzazione è iniziata e per segnalare che l'inizializzazione è stata completata. Dopo aver eseguito l'inizializzazione, le modifiche alle proprietà verranno ignorate.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Rotazione, conversione e ritaglio di immagini  
 WPFWPF consente agli utenti di <xref:System.Windows.Media.Imaging.BitmapImage> trasformare le <xref:System.Windows.Media.Imaging.BitmapSource> immagini <xref:System.Windows.Media.Imaging.CroppedBitmap> utilizzando <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>le proprietà di o utilizzando oggetti aggiuntivi, ad esempio o . Queste trasformazioni di immagini possono ridimensionare, ruotare, modificare il formato dei pixel o ritagliare un'immagine.  
  
 Le rotazioni dell'immagine vengono eseguite utilizzando la <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> proprietà di <xref:System.Windows.Media.Imaging.BitmapImage>. Le rotazioni possono essere eseguite solo in incrementi di 90 gradi. Nell'esempio seguente un'immagine viene ruotata di 90 gradi.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversione di un'immagine in un formato <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>pixel diverso, ad esempio la scala di grigi, viene eseguita utilizzando . Negli esempi seguenti, un'immagine <xref:System.Windows.Media.PixelFormats.Gray4%2A>viene convertita in .  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Per ritagliare un'immagine, <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.Imaging.CroppedBitmap> è possibile utilizzare la <xref:System.Windows.UIElement.Clip%2A> proprietà o . In genere, se si desidera solo visualizzare <xref:System.Windows.UIElement.Clip%2A> una parte di un'immagine, deve essere utilizzato. Se è necessario codificare e salvare un'immagine ritagliata, è necessario utilizzare l'oggetto <xref:System.Windows.Media.Imaging.CroppedBitmap> deve essere utilizzato. Nell'esempio seguente, un'immagine viene ritagliata <xref:System.Windows.Media.EllipseGeometry>utilizzando la proprietà Clip utilizzando un oggetto .  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Adattamento delle immagini  
 La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà controlla il modo in cui un'immagine viene estesa per riempire il relativo contenitore. La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà accetta i valori seguenti, definiti dall'enumerazione <xref:System.Windows.Media.Stretch> :  
  
- <xref:System.Windows.Media.Stretch.None>: l'immagine non viene allungata per riempire l'area di output. Se l'immagine è più grande dell'area di output, viene disegnata al suo interno, escludendo gli elementi in eccesso.  
  
- <xref:System.Windows.Media.Stretch.Fill>: l'immagine viene ridimensionata per adattarsi all'area di output. Poiché l'altezza e la larghezza dell'immagine vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali dell'immagine. In altre parole, l'immagine potrebbe essere distorta per adattarsi completamente al contenitore dell'output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: l'immagine viene ridimensionata in modo da adattarsi completamente all'area di output. Vengono mantenute le proporzioni dell'immagine.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: l'immagine viene ridimensionata in modo da riempire completamente l'area di output mantenendo le proporzioni originali dell'immagine.  
  
 Nell'esempio riportato di <xref:System.Windows.Media.Stretch> seguito vengono <xref:System.Windows.Controls.Image>tutte le enumerazioni disponibili a un oggetto .  
  
 L'immagine seguente mostra l'output dell'esempio <xref:System.Windows.Controls.Image.Stretch%2A> e dimostra l'effetto delle diverse impostazioni quando vengono applicate a un'immagine.  
  
 ![TileBrush con impostazioni Stretch diverse](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Impostazioni Stretch diverse  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Disegnare con immagini  
 Le immagini possono anche essere visualizzate in <xref:System.Windows.Media.Brush>un'applicazione disegnando con un . I pennelli consentono di disegnare oggetti [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini. Per disegnare con le <xref:System.Windows.Media.ImageBrush>immagini, utilizzare un file . Un <xref:System.Windows.Media.ImageBrush> è un <xref:System.Windows.Media.TileBrush> tipo di che definisce il contenuto come immagine bitmap. Un <xref:System.Windows.Media.ImageBrush> visualizza una singola immagine, <xref:System.Windows.Media.ImageBrush.ImageSource%2A> specificata dalla relativa proprietà. È possibile controllare il modo in cui l'immagine viene adattata, allineata e affiancata, consentendo di evitare distorsioni e produrre motivi e altri effetti. Nella figura seguente vengono illustrati alcuni <xref:System.Windows.Media.ImageBrush>effetti che è possibile ottenere con un oggetto .  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
I pennelli immagine possono riempire forme, controlli, testo e altro ancora  
  
 Nell'esempio riportato di seguito viene illustrato come <xref:System.Windows.Media.ImageBrush>disegnare lo sfondo di un pulsante con un'immagine utilizzando un oggetto .  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Per ulteriori <xref:System.Windows.Media.ImageBrush> informazioni e disegno di immagini, consultate [Disegno con immagini, disegni e oggetti visivi.](painting-with-images-drawings-and-visuals.md)  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>Metadati delle immagini  
 Alcuni file di immagine contengono metadati che descrivono il contenuto o le caratteristiche del file. La maggior parte delle fotocamere digitali, ad esempio, crea immagini che contengono i metadati relativi a marca e modello della fotocamera usata per acquisire l'immagine. Ogni formato di immagine gestisce i metadati in modo diverso, ma WPF Imaging offre un modo uniforme di archiviare e recuperare i metadati per ogni formato di immagine supportato.  
  
 L'accesso ai <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> metadati <xref:System.Windows.Media.Imaging.BitmapSource> viene fornito tramite la proprietà di un oggetto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>restituisce <xref:System.Windows.Media.Imaging.BitmapMetadata> un oggetto che include tutti i metadati contenuti nell'immagine. Questi dati possono essere in uno schema di metadati o in una combinazione di schemi diversi. WPF Imaging supporta i seguenti schemi di metadati di immagine: file di immagine scambiabili (Exif), tEXt (dati testuali PNG), directory dei file di immagine (IFD), International Press Telecommunications Council (IPTC) e Extensible Metadata Platform (XMP).  
  
 Per semplificare il processo di <xref:System.Windows.Media.Imaging.BitmapMetadata> lettura dei metadati, fornisce <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>diverse <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>proprietà <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>denominate facilmente accessibili, ad esempio , e . Molte di queste proprietà denominate consentono anche di scrivere metadati. Il lettore di query dei metadati fornisce supporto aggiuntivo per la lettura dei metadati. Il <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> metodo viene utilizzato per recuperare un lettore di query di metadati fornendo una query di stringa, ad esempio *"/app1/exif/".* Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> viene utilizzato per ottenere il testo memorizzato nel percorso *"/Text/Description".*  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Per scrivere i metadati viene usato il relativo writer di query. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>ottiene il writer di query e imposta il valore desiderato. Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> viene utilizzato per scrivere il testo archiviato nel percorso *"/Text/Description".*  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>Estendibilità dei codec  
 Una funzionalità di base di WPF Imaging è il modello di estensibilità per i nuovi codec di immagine. Queste interfacce non gestite consentono agli sviluppatori di codec di integrare i codec con WPFWPF in modo che i nuovi formati di immagine possano essere usati automaticamente dalle applicazioni WPFWPF.  
  
 Per un esempio dell'API di estensibilità, vedere il [codec di esempio Win32](https://go.microsoft.com/fwlink/?LinkID=160052). Questo esempio spiega come creare un decodificatore e un codificatore per un formato di immagine personalizzato.  
  
> [!NOTE]
> Il codec deve essere firmato digitalmente per il sistema affinché venga riconosciuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Codec di esempio di Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
